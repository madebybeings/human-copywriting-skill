# Human Copywriting skill

A skill for Claude, Claude Code, Cursor and ChatGPT that writes and edits prose so it reads as if
a person chose every sentence, without changing a single fact.

Most "humanizer" prompts start with a banned-word list. This one starts where the 2026 research
says the difference actually is: what the writing chooses to say, how much it explains and what it
leaves for the reader. Word choice comes nearly last.

Written up in [AI vs Human Copywriting: What the Research Actually Shows](https://madebybeings.com/blog/ai-vs-human-copywriting).

## What's inside

| Path | What it is |
|---|---|
| `skills/human-copywriting/SKILL.md` | The skill: editing order, non-negotiables, modes, depth, workflow |
| `skills/human-copywriting/references/full-guide.md` | Registers and the 18 editing passes, for published work |
| `skills/human-copywriting/references/ai-tells.md` | AI tells ranked by strength, with before and after pairs |
| `skills/human-copywriting/references/research.md` | The studies behind it, with the numbers |
| `skills/human-copywriting/scripts/prose_check.py` | Flags dashes, Oxford commas, stock phrases, contrast formulas and flat rhythm |
| `chatgpt/HUMAN_COPYWRITING.md` | Single-file version for a ChatGPT Project |

## Install

**Claude Code (plugin):**

```
/plugin marketplace add madebybeings/human-copywriting-skill
/plugin install human-copywriting@human-copywriting-skill
```

**Claude Code or Cursor (copy the folder):** copy `skills/human-copywriting/` into
`.claude/skills/` in your project (Cursor reads that path too) or into `~/.claude/skills/`.

**Claude apps:** zip the `skills/human-copywriting/` folder and upload it as a custom skill in
Claude's settings.

**ChatGPT:** upload `chatgpt/HUMAN_COPYWRITING.md` to a Project and add this line to the
Project Instructions: "Follow HUMAN_COPYWRITING.md for all drafting and rewriting."

## Use it

Ask for writing as you normally would ("rewrite this landing page", "draft a post about X"). For a
published piece, ask for full depth. To check a draft mechanically:

```
python3 skills/human-copywriting/scripts/prose_check.py draft.md
```

It exits non-zero if it finds an em or en dash, and lists everything else as advice.

## Make it yours

Edit the "House defaults" section of `SKILL.md`: dialect, dashes and the Oxford comma are our
choices, not rules. Add your own style guide as a second layer. The skill is built to sit under
one.

## What it won't do

It won't invent facts, fake typos or promise to beat AI detectors. It aims at the reader, not the
detector.

## Credits

Built by [Made By Beings](https://madebybeings.com). It stands on
[human-voice](https://github.com/stephenoffer/human-voice) by Stephen Offer (MIT) and
[humanizer](https://github.com/blader/humanizer) by Siqi Chen (MIT), and on the community guide
[Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
(paraphrased, CC BY-SA 4.0). Research sources are listed in `references/research.md`.

MIT licensed. See `LICENSE` and `NOTICE`.
