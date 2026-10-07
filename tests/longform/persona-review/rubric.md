# Reader assessment instructions

Read only this rubric and ../korean-edited.md / ../english-edited.md. The recorded run used byte-identical isolated snapshots named text-ko.md and text-en.md. These are fictional internal documents. Do not read repository skills, originals, previous evaluations, or other reviewers. Evaluate the two current documents independently as the assigned persona. Do not rewrite them or claim to know their authorship. Respond in Korean, quoting the text's actual language for evidence.

Rate five dimensions from 0 to 10, integers, equally weighted. Total = sum * 2, out of 100. These are subjective reader-quality ratings, not AI probability, measured comprehension rates, or model benchmarks.

- comprehension: How easily the reader can explain the point and understand the important constraints.
- flow: Logical sequence of sections, sentence/paragraph connections, and arrival of context when needed.
- wording: Familiar and precise vocabulary, manageable syntax, referent clarity, no needless effort.
- voice: Natural cadence and consistent register, credible personal voice, no distracting formulaic repetition. Formal writing can score highly; do not demand slang or fake personal anecdotes.
- usefulness: Can this intended reader see what is observed, uncertain, proposed, required, or still undecided, and what happens next?

Common anchors: 10 = clear throughout for this reader with no meaningful friction; 8 = works well with minor identifiable friction; 6 = understandable but repeatedly requires rereading or inference; 4 = major ambiguity/structure obscures key meaning; 2 = most key points hard to recover; 0 = unusable. Odd scores interpolate. Do not start from a presumed high score or force criticism. Quote supporting evidence for each score, including high scores. Respect genre; this is not marketing copy.

After reading each document, answer the five comprehension questions in your own words WITHOUT reading any fact sheet. The root will check accuracy separately; do not invent certainty to fill an ambiguity.

Korean:
K1. What was tried, for whom, during which times, and what was excluded?
K2. What can and cannot be concluded from the meeting-hour comparison and survey?
K3. What burden did operations experience, and what does the 17/5 evidence establish or fail to establish?
K4. What two future options remain, which does the author favor, and under what conditions can it proceed?
K5. Has a decision been made, and how does the author's personal experience affect the argument?

English:
E1. Which machines/sessions are in scope, and what remains excluded?
E2. How do booking limits, arrival-day access, and safety authorization work?
E3. What does the observed waiting evidence establish or fail to establish?
E4. What must be ready to start, who has committed to which work, and what are the deadlines? Explicitly note ambiguity if present.
E5. How and when will the trial be evaluated, and would fewer waits alone establish success?

Save a JSON object to the assigned output path, with model (exact requested model), persona, and documents object with keys ko/en. Each document contains:
- scores: object of five dimension names, each {score: integer, reason: Korean text, evidence: exact short quote}
- total: sum of five scores times 2
- comprehension_answers: object K1..K5 or E1..E5
- strongest_feature: concrete observation
- friction: array of up to 3 actual issues, each {quote, impact, suggested_direction}; empty if warranted
- ready_to_share: reasoned judgment, distinguish readability from unresolved factual decisions.
Keep the report under about 1,500 Korean words. Do not modify the text. Return output path and score summary.
