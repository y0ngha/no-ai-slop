# No AI Slop

Make English and Korean drafts clearer and more natural without flattening your personal voice.

https://github.com/user-attachments/assets/f3055450-78eb-4672-880a-88a4fa54bde9

## Problem

AI makes it easy to generate clean writing that all sounds the same. Even the best models keep producing lines like:

- “It’s not X. It’s Y.”
- “What nobody tells you is…”
- “The future isn’t coming. It’s already here.”

When you use AI to edit, it can also smooth away the vocabulary, cadence, humor, and imperfections that make the writing sound like you.

## How to install No AI Slop

The easiest way to install the skill is to paste this into ChatGPT, Claude Code, Codex, or your favorite coding agent:

```text
Install the /no-ai-slop skill globally from https://github.com/petergyang/no-ai-slop
```

You can also install it with `npx`:

```sh
npx skills add petergyang/no-ai-slop --skill no-ai-slop --global --yes
```

## How to use No AI Slop

### Edit your writing

```text
/no-ai-slop (your writing)
```

The skill edits for the reader, context, and your voice, then briefly explains substantive changes. Ask for “only the edited text” to skip the change note. Clear passages can stay unchanged.

### Detect slop

```text
/no-ai-slop is this slop? (your writing)
```

The skill quotes every slop pattern it found without guessing whether AI wrote the text.

### Edit writing in another language

```text
/no-ai-slop (your Korean draft)
```

The skill edits in the language you wrote in. English and Korean have separate guidance; mixed drafts keep intentional language switches and technical terms.

Korean editing covers 번역투, 호응, 명사 나열, 이중 피동, 사물존칭, and paragraph flow while preserving 합니다체, 해요체, or the original register.

```text
/no-ai-slop 사내 안내문이야. 해요체는 유지하고, 과장된 표현과 어색한 흐름만 고쳐줘. 수정한 본문만 줘. (초안)
```

```text
/no-ai-slop Lightly edit this technical update for engineers. Keep the terminology, uncertainty, and my tone. Return only the edited text. (draft)
```

Patterns are contextual signals, not a blacklist. The skill preserves useful contrasts, passive voice, summaries, and familiar technical vocabulary. It does not invent facts, metrics, or anecdotes to make writing sound more human. It can also write from supplied notes when asked, without adding unsupported content.

### Generate slop for fun

```text
Draft an AI slop post about (topic)
```

Use it to generate the most cringe AI slop possible as satire.

## The slop that this skill catches

No AI Slop inspects recurring patterns in context, including:

1. **Binary contrasts.** “It’s not X. It’s Y.”
2. **Throat-clearing openers.** “Here’s the thing,” “Let me be clear”
3. **Faux-insight setups.** “What nobody tells you,” “The part everyone misses”
4. **Colon reveals.** “The best part: it learns.”
5. **Dramatic fragments.** “That’s it. That’s the whole thing.”
6. **Superficial analysis.** “highlighting the team’s commitment to innovation”
7. **Importance puffery.** “marks a pivotal moment,” “a testament to”
8. **Weasel attribution.** “experts agree,” “studies show”
9. **Synonym cycling.** “The agent handles your email. The assistant drafts replies.”
10. **Fake-profound endings.** “The future isn’t coming. It’s already here.”

It also checks the fundamentals: Lead with the point when that helps, use active voice, untangle hard-to-follow sentences, and prefer concrete details over abstractions.

## What’s inside

- [`SKILL.md`](skills/no-ai-slop/SKILL.md) contains the editing rules and workflow.
- [`eval.md`](skills/no-ai-slop/eval.md) contains the checks the skill runs on its work.
- [`references/english.md`](skills/no-ai-slop/references/english.md) covers English diction, sentence structure, and rhetorical patterns.
- [`references/korean.md`](skills/no-ai-slop/references/korean.md) covers Korean register, syntax, vocabulary, and flow.
- [`tests/behavioral-cases.md`](tests/behavioral-cases.md) contains 15 manual evaluation cases, including text that should remain unchanged. These development fixtures are not shipped in the plugin.
- [`tests/longform/README.md`](tests/longform/README.md) records a long-form evaluation with full English and Korean source/edit pairs, observed failures, and final checks.
- [`tests/genre-eval/README.md`](tests/genre-eval/README.md) records 12 cross-genre cases, three-model reader ratings, revisions, comprehension checks, and unresolved source questions.
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) contains the ChatGPT and Codex plugin metadata.
- [`build_plugin.py`](scripts/build_plugin.py) builds and validates the plugin package.

No AI Slop is also available as a plugin in ChatGPT.

## Want more great AI skills?

Check out [Behind the Craft](https://behindthecraft.com), my personal AI system with over a dozen other quality skills and courses.

Subscribe to my [YouTube channel](https://www.youtube.com/@PeterYangYT?sub_confirmation=1) and [newsletter](https://creatoreconomy.so) for practical AI tutorials and interviews.

## License

MIT
