# Long-form editing evaluation

These are fictional development fixtures, not real workplace reports or evidence of human authorship. A separate writer produced the sources without reading the skill, its examples, or existing tests. The editor then used no-ai-slop on the full drafts. Two other reviewers compared neutrally labelled versions without seeing the skill or knowing which was the edit. Label order differed by language.

## Read the pairs

| Case | Source | Final edit | Length |
| --- | --- | --- | --- |
| Korean internal retrospective | [Source](korean-source.md) | [Edit](korean-edited.md) | 3,645 → 3,492 characters including whitespace |
| English decision memo | [Source](english-source.md) | [Edit](english-edited.md) | 1,291 → 1,255 whitespace-delimited words |

[Fact inventory](facts.md) records many of the constraints. It is incomplete: the source remains authoritative. Lengths include headings and metadata and are descriptive, not editing targets.

## Outcome observed on 2026-10-07

Both reviewers preferred the edited version. The Korean review found that moving the exception rules ahead of the observed effects made the waiting burden easier to understand. The English review preferred the earlier launch conditions and safety requirements, and the simpler exception-handling paragraph. The English improvement was modest: the source was already a credible memo.

Both edits kept concrete personal material. The Korean retrospective retains the author's cold coffee, preference for the experiment, and concern about confusing personal benefit with team benefit. The English memo retains travel costs, spontaneous mending help, and the closing concern that a tidier calendar can make a worse afternoon. Neither required a uniform paragraph template or removal of every rhetorical sentence.

The first pass and final audits exposed three fidelity issues:

1. The Korean edit reduced a sentence reporting competing team opinions to a statement that a decision remained open. A blind reviewer initially endorsed this because the separate fact inventory did not mention the opinions. The complete source did, so the final edit restores the original sentence. The reviewer corrected that judgment after a full-source audit.
2. The English edit moved a quoted approval phrase and changed its closing period to a comma. A literal comparison caught this; the reviewer had missed the punctuation change while reporting that the quotations matched. The final edit restores `“approved to operate.”` exactly and splits the surrounding sentence. “Staff coverage” was also made more precise as “coordinator coverage.”

3. The source requests coordinator hours “before October 20” but describes overall readiness “by October 20.” The first edit used only “by,” silently harmonizing the dates. The final edit restores the earlier staffing sentence verbatim and retains the overall readiness date. An editorial note is still needed: confirm whether staffing must be arranged before that date or may be arranged on it. This synthetic evaluation does not resolve the author's intended deadline.

These findings led to a short long-draft section in SKILL.md and matching eval.md checks: inspect section dependencies, preserve differing views and supporting detail, and compare the whole source after restructuring. An outline or fact list cannot replace that comparison. Protected quotations benefit from literal checks rather than reviewer confidence alone.

The final Korean and English versions were rechecked against their complete sources. The English deadline ambiguity is preserved and flagged here rather than silently resolved; factual approval of that deadline remains separate from the readability judgment. Curly-quoted spans are retained exactly (one Korean, three English), and the sets of numeric tokens match. These mechanical checks do not establish that numbers retain their meaning; the final editorial audits also checked their subjects, scope, caveats, responsibilities, and conditions.

## Re-run the evaluation

Give a fresh editor SKILL.md and one source, with the matching task:

- Korean: “팀 내부에 공유할 긴 회고문이야. 의미와 필자의 합니다체를 유지하면서 어휘와 문단 흐름을 다듬어줘. 요약하지 말고, 수정한 본문만 반환해줘.”
- English: “Edit this long memo for the workshop steering group. Improve readability and flow while preserving its facts, qualifications, authorial voice, and decision conditions. Do not summarize. Return only the edited memo.”

Save the actual output separately. Do not give the editor the existing edit or review outcome as an expected answer. A different edit can be equally successful.

Have a fresh reviewer compare the full source and result. Check the exact numbers, quotation spans, roles, and conditions, plus these document-level questions:

- Does the reader get the rule or prerequisite before needing it to interpret a result?
- Do moved paragraphs still connect naturally, without an invented causal bridge?
- Are different people's views and unresolved choices still distinguishable?
- Do the examples and personal details still support the argument?
- Does the ending follow from the evidence rather than add a slogan or a new claim?
- Has an edit preserved meaningful repetition where an opening recommendation and closing conditions serve different purposes?

For a preference comparison, hide which version is edited and vary the ordering. For the final fidelity audit, identify the source explicitly and treat the inventory only as an aid. A smooth result with a material omission does not pass.

## Limits

This is a qualitative check of two generated sources in two internal-document genres, using model reviewers. It is not a human-reader study, an AI-authorship test, or a measured improvement rate. The sources were reasonably well written, so the exercise mainly tests restraint, organization, and fidelity rather than recovery of a severely incoherent draft. The updated long-form guidance was used for the final corrective pass; it has not yet been tested in a fresh independent edit of unseen long documents. Real user drafts, public essays, and English-to-Korean translation remain useful next cases.

## Persona ratings

A later user-requested [three-model persona review](persona-review/README.md) scores the final drafts and checks comprehension answers separately. It records subjective scores, concrete reading friction, and limitations; these are not AI-authorship probabilities.
