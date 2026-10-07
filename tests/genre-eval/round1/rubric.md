# Cross-genre reader assessment

Read index.json and all ten documents listed there. No other files, skills, originals, prior evaluations, fact inventories, or model reports. Texts are fictional; judge the writing for the stated audience and genre rather than verifying external product claims. Use your assigned reader persona as a lens, respecting the specified audience. Do not rewrite sources.

The user specifically wants familiar everyday vocabulary and a flow a person can follow easily, without inflated/empty AI-style phrasing. Do NOT reward a polished official tone merely for sounding professional. Equally, do not penalize necessary technical terms, standard precise vocabulary, genuine personal voice, meaningful uncertainty, valid lists, or a condition that is honestly undecided.

Score five dimensions, integers 0–10 each. Total = sum * 2 /100:
- plain_words: familiar words for the reader; needed specialist terms handled clearly; no unnecessary abstraction or lofty replacement words.
- flow: each sentence/paragraph follows from context; prerequisites arrive when needed; no clipped disconnected fragments or mechanical template.
- clarity: main point, actor, referent, conditions, and distinctions easy to recover accurately.
- no_slop: absence of empty praise, generic setup, inflated emphasis, repeated faux contrasts, ornamental metaphor, redundant recap, formulaic cadence. Evaluate the passage, not token matches. This is a style rating, not authorship probability.
- genre_fit: appropriate length, formality, voice and organization; a Slack recipient can act, a report reader can distinguish findings/limits, a personal article retains its voice.

Anchors: 10 no meaningful friction, 8 works with a minor concrete issue, 6 repeated rereading or inflated/awkward phrasing, 4 a material point is obscured, 2 most of the text is hard to use, 0 unusable. Odd scores interpolate. Use the full scale when justified, but do not invent issues or force low scores. A high average cannot compensate for a misunderstood critical condition.

For EACH case output JSON:
{id, scores:{plain_words,flow,clarity,no_slop,genre_fit}, total, verdict:'ready'|'minor_edit'|'needs_revision', strongest_feature:{quote,reason}, issues:[{quote,problem,reader_effect,suggested_direction,severity:'minor'|'material'}], answers:[answer to question1, answer to question2]}.
Use exact short quotes for evidence. At most 2 issues per case. No speculative task requirements missing from a source you have not seen. Do not assume every unresolved decision is a writing flaw. Answers must reflect only what you read, preserving limits/conditions.

Save {model: exact model,persona: assigned role,cases:[all ten cases]} as JSON at your assigned output path. Write reasons/answers in Korean (English quotations remain English). Aim for concise evidence, about 100–180 Korean words per case. Return score range and any material issue, with output path. Do not read other reviewers or modify any text.
