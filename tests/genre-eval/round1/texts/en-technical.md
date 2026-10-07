# How the Alder search index refresh works

Alder uses the document store as its source of truth and builds a separate index for search. Saving a document does not make it immediately searchable: the refresh worker must first include it in a new index. If a refresh fails, search can use the active index only while its data is no more than 20 minutes old.

## Building and switching the index

Every five minutes, the worker takes a snapshot of published documents and builds a new index generation. It leaves the generation handling current requests unchanged. Each generation has an identifier such as `gen_204`, a `snapshot_at` timestamp, and a status.

`snapshot_at` is when the document snapshot was taken, not when the build finished. If a build takes three minutes, its data is already three minutes old when it starts serving requests.

Before switching to the new generation, the worker checks that:

- The generation can be opened.
- Every indexed document has a document ID.
- The document count differs from the previous generation by no more than 15%.

A larger count difference requires human review; it does not necessarily mean the data is wrong. If any check fails, the worker keeps the active generation and records a failed refresh. If all checks pass, it switches the active-generation pointer in one atomic operation. Requests already using the old generation may finish against it; new requests use the new pointer.

## Serving results after a failed refresh

At the start of each request, the server calculates the active generation's age as `request_started_at - snapshot_at`, using the server clock. A generation exactly 20 minutes old is still eligible to serve results. At 20 minutes and one second, it is too old. Even a successful refresh does not reset the age to zero: the snapshot timestamp still determines the age.

If the latest refresh failed and the active generation is eligible, the API returns its ordinary results with `stale: true`. The interface displays "Results may be up to 20 minutes old." It uses that same notice even if the actual age is only seven minutes, so readers get a stable upper bound rather than a changing estimate.

An empty list from that generation is still a valid result. The client must not treat it as a reason to retry against another generation.

If the active generation is too old or none exists, the API returns HTTP 503 with code `SEARCH_TEMPORARILY_UNAVAILABLE` and no result items. The interface displays "Search is temporarily unavailable. Please try again shortly."

There is no fallback to an unrestricted database query. That query would apply permissions differently and could put a large load on the document store, so adding one would change the behavior of the fallback.

## Testing the age limit

Use a fixed clock to test both sides of the 20-minute boundary. Also check that a failed document-count check leaves the active pointer unchanged.

Generation age and failed-refresh count are recorded separately. Repeated worker failures are concerning, but the age rule determines whether a particular request can receive results. A retry may recover the refresh process; it must never extend the serving deadline of an existing snapshot.
