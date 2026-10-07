---
name: no-ai-slop
description: Edit or review English and Korean drafts for clear, natural writing that fits the audience and preserves the writer's voice. Use when the user asks to remove AI-sounding prose, simplify inflated wording, improve flow, or flag awkward writing without rewriting. Supports other languages with shared principles; does not determine AI authorship.
---

# No AI slop

Make the draft easy to follow and natural for its reader. Preserve the writer's meaning, voice, and useful detail. Natural writing can be formal, technical, conversational, or understated; it does not need extra personality or a punchier opinion.

## Choose the job and context

**Edit (default).** Make the minimum effective changes. Return the edited draft and a short account of substantive changes in the user's language. If the user wants only the text, return only the text. If the draft already works, leave it intact and say so when commentary is allowed.

**Detect or review.** When asked to flag problems without rewriting, quote each problematic passage, name the pattern, explain its effect, and suggest a local fix. Do not return a full rewrite. Report no findings when none are warranted. Do not infer authorship or assign an AI probability or a naturalness score from stylistic features.

Read the full draft first. Infer the audience, purpose, genre, destination, and level of formality from the request and text. Ask one focused question only when an unresolved choice would materially change the edit. If no draft is provided for an editing request, ask for it. If asked to write from supplied notes, use those notes as the source and apply the same principles; ask for essential missing content rather than inventing it.

Edit in the draft's language unless translation is requested. Read [English guidance](references/english.md) for English prose and [한국어 지침](references/korean.md) for Korean prose. For mixed prose, use both as relevant, preserving intentional language switches, identifiers, and established terms. For another language, use the shared principles without imposing English syntax.

## What takes priority

1. The user's explicit instructions and applicable house style.
2. Meaning and fidelity: facts, names, numbers, attribution, uncertainty, obligations, conditions, and exceptions.
3. The audience's needs, the genre, and the writer's recognizable voice.
4. The patterns and examples in this skill.

Patterns are reasons to inspect a sentence, not banned tokens. Change a passage when you can explain what the edit improves: clarity, precision, flow, or fit. A matching word or punctuation mark alone is not a defect.

Keep verbatim quotations, code, URLs, identifiers, and quoted UI labels or error messages intact unless explicitly asked to edit them. Distinguish quoted UI text from UI copy the user actually wants rewritten.

## Edit for meaning and flow

- **Keep the claim the same.** Never add a plausible number, source, mechanism, actor, or personal experience to make prose concrete. Keep possibility distinct from certainty, recommendation from requirement, and correlation from cause. When supporting detail is absent, simplify only as far as the source allows. Flag a consequential gap briefly; do not turn every vague adjective into a blocking question.
- **Use familiar, precise words.** Prefer words the reader uses in ordinary work or conversation. A professional document does not need more formal vocabulary. When a broad term hides a specific action already described in the source, name that action. Keep technical terms that carry an exact meaning; explain them briefly for an unfamiliar audience if the source supports the explanation. Check replacements too: changing one grand phrase into another has not made the sentence easier. If explaining a term creates a tangled sentence, split the explanation or use a clear nearby reference.
- **Let verbs carry actions.** Unpack noun piles and padded verb phrases when they slow reading. Use active voice when it clarifies responsibility. Keep passive voice when the actor is unknown or irrelevant, and keep ordinary system subjects such as “The server rejects expired tokens.”
- **Give each paragraph a purpose.** Check how each sentence advances the previous one and how each paragraph leads to the next. Group scattered repetitions when restructuring is allowed. Retain the context needed to understand a finding; do not force every opening into a conclusion, anecdote, or dramatic hook.
- **Make relationships explicit enough.** Preserve useful transitions that express cause, contrast, sequence, or an exception. Remove transitions that merely announce another paragraph. Name a referent when it is ambiguous; keep a clear pronoun or an understood subject when repetition would make the prose heavier.
- **Tie actions and times to their owners.** In requests and plans with several milestones, make clear who reviews, who sends the result, and when each acts. A review appointment is not automatically a completion deadline; a deadline is not proof that its prerequisite has been met. Separate easily confused steps with a sentence or a short list when useful. Preserve fallback triggers exactly, and flag a missing decision rule instead of supplying one.
- **Cut repetition without losing the argument.** Remove restatements that add nothing. Keep a summary when a long document needs synthesis, a decision, or a next action. Keep necessary scope limits and contrasts that correct a likely misunderstanding.
- **Preserve cadence and voice.** Split genuinely tangled sentences, especially when the reader loses the subject or condition. Keep clear long sentences, fragments, humor, contractions, and personal asides that fit the writer. Do not manufacture variety, deliberate errors, slang, or anecdotes to sound human.
- **Replace empty emphasis with supported substance.** Inspect generic praise, dramatic reveals, faux insight, and slogans. Keep earned judgments and explanations of why something matters. If a line could fit any product or topic, check whether it contributes needed context before cutting it.
- **End where the job is done.** Remove a stock aphorism, repeated recap, or abrupt sales pitch that changes the purpose of the piece. Keep a requested call to action or an ending that helps the reader decide what to do.

## Long drafts

For a multi-section article or memo, check the whole argument as well as individual sentences. Silently identify what each section contributes and which earlier context it depends on. Move a late definition, exception, or prerequisite when the reader needs it sooner; then reread the affected transitions and references. Keep meaningful narrative order when delayed information serves the story.

An edit is not a summary unless requested. Preserve supporting examples, distinct stakeholder views, unresolved disagreements, and personal moments that carry the argument or voice. Distinguish redundant wording from a necessary return to a point: an opening recommendation and a closing account of its conditions can both earn their place.

After restructuring, compare the complete result with the complete source, not just a fact list or outline. Check the scope attached to numbers, who holds each view or responsibility, qualifications, decision status, and exact quoted spans. A checklist can omit a fact that the source still requires you to preserve. When files or comparison tools are available, use a diff or literal comparison for protected text; matching numbers alone does not establish fidelity.

## Source documents and summaries

Adapt explanations to the target reader while retaining official terminology, distinctions, and useful domain vocabulary. Avoid carrying over the source's organization when it causes duplicate explanations. Do not require all source words to disappear.

When reorganizing supplied material, check that categories still mean the same thing and that any count you change matches its list. Flag inconsistencies rather than silently choosing a factual correction. A style edit is not independent fact-checking.

Replace fragile references such as “the fourth row” when items may move or be read separately. Keep valid heading links, stable section references, and clear nearby references. Use names only where they help the reader locate the subject.

## Fit the destination

Follow the requested template and the destination's formatting conventions. These are defaults, not sentence limits or permission to publish or send anything.

- **Notion or a shared document:** Use coherent paragraphs and meaningful headings. Add bold leads only when they help scan comparable items. Keep useful comparison tables and links; prefer heading names when section numbers will not survive a move.
- **Slack or chat:** Lead with the ask, answer, or update. Keep enough context to act, but remove a repeated explanation that only says a review is needed because something needs checking. State the actual dependency when supplied. Fold useful process history into the request instead of repeating it as an abstract justification. If review, delivery, and advance notice have different times, label those actions clearly. Use a short list when it is easier to scan; suggest a thread only when length warrants one. Match the requested syntax (`*bold*` for Slack mrkdwn, for example).
- **Repository Markdown:** Preserve useful structure, wrapping conventions, code paths, and links. Check references affected by edits; line numbers may move. Follow repository writing rules.
- **Email or a direct message:** Make the purpose clear early. Preserve a greeting, tact, and context where the relationship calls for them.

Use headings, bullets, tables, bold, and punctuation for navigation or meaning. Avoid decorative emphasis and needless fragmentation; do not impose a quota or flatten a useful template. A technical spec can repeat a structure for comparison without sounding wrong.

## Final pass

Read the result as a whole, then compare it with the source using [eval.md](eval.md). Check meaning before style. Briefly restate the main point and, where relevant, the actor, action, condition, and next step from the edited text, then compare that understanding with the source. Fluent phrasing alone does not establish that the reader can recover the right meaning. Correct any actual problem, leaving passages that already work alone. Keep the checklist internal unless the user requests it. Mention material restructuring or unresolved gaps in the short change note; do not add a routine editing report to a request for text only.
