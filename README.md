<div align="center">

# BADESIGN

Design judgment for AI models that design badly.

<a href="https://x.com/uxKero"><img alt="Made by @uxKero" src="https://img.shields.io/badge/MADE%20BY-%40uxKero-000000.svg?style=for-the-badge&logo=x&labelColor=000000"></a> <a href="LICENSE"><img alt="MIT license" src="https://img.shields.io/badge/LICENSE-MIT-000000.svg?style=for-the-badge&labelColor=000000"></a> <a href="badesign-skill/SKILL.md"><img alt="Agent Skills format" src="https://img.shields.io/badge/FORMAT-AGENT%20SKILLS-000000.svg?style=for-the-badge&labelColor=000000"></a>

</div>

<br>

Ask a model for a dashboard or a landing page and it returns the average of every one it has seen: purple gradients, a card around everything, rows of stat tiles, tiny grey text. BADESIGN is a single skill that gives the model the judgment to design instead. It works in Codex, Claude Code, Cursor and any model through an API.

## What is inside

- **Priority order.** One declared order for resolving tensions, so the model commits to a decision.
- **Hard limits.** Measurable rules that always hold: contrast, text size, hit areas, nothing clipped, centered content inside controls, complete code.
- **Understanding.** The job, the content, the whole product, and one visual idea taken from the subject itself.
- **Principles.** Composition, craft, expression, grouping, typography, color, data, behavior, motion and copy.
- **Habits.** The patterns that make AI interfaces look generated, and when each one is justified.

## Install

```bash
npx skills add uxKero/badesign-skill
```

Or copy the `badesign-skill` folder where your agent reads skills, then restart the agent.

| Agent | Personal | Per project |
|:--|:--|:--|
| Codex | `~/.agents/skills/` | `.agents/skills/` |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Cursor | `~/.cursor/skills/` | `.cursor/skills/` |

```bash
git clone https://github.com/uxKero/badesign-skill.git
cp -r badesign-skill/badesign-skill ~/.agents/skills/
```

## Self-improvement

Your agent can get better at design with every project. [SELF-IMPROVEMENT.md](SELF-IMPROVEMENT.md) turns 41 papers on why AI interfaces fail and how models learn from mistakes into rules the agent keeps, and adds a new rule each time one of its designs is corrected.

| Learn | Distill | Keep | Record |
|:--|:--|:--|:--|
| The agent reads the guide and the papers that fit the project. | It writes rules that name each failure and what to do instead. | It saves them in `AGENTS.md`, `CLAUDE.md` or `DESIGN.md`. | Every corrected design adds a new rule. |

The skill never loads it, so BADESIGN stays fast and focused.

## Pairs well with

BADESIGN decides how an interface should look and behave. These skills go deeper where it stays brief.

| Skill | Use it for |
|:--|:--|
| [anydesign](https://github.com/uxKero/anydesign) | Reading an image, a website or a Figma file and turning it into a design.md with tokens, components and reconstruction notes, so an existing design can be reproduced faithfully. By [@uxKero](https://x.com/uxKero). |
| [Design&nbsp;Engineering](https://github.com/emilkowalski/skills) | Animation and interaction craft from a design engineer at Linear: when to animate, easing, springs, gestures and animation reviews. By [@emilkowalski](https://x.com/emilkowalski). |
| [Impeccable](https://github.com/pbakaus/impeccable) | Critiquing and polishing an existing interface with focused design commands. By [@pbakaus](https://x.com/pbakaus). |

<br>

<div align="center">

Made by [@uxKero](https://x.com/uxKero) under the [MIT License](LICENSE).

</div>
