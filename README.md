# Skills

My agent skills. Each skill is a plain folder with a `SKILL.md` and works on its own.

## Skills

| Skill | Use it for |
|---|---|
| [`handbook-writer`](skills/handbook-writer/SKILL.md) | A practical subject handbook as one Markdown document: cover, 20 chapters, closing checklist |
| [`socratic-concept`](skills/socratic-concept/SKILL.md) | Understanding a concept, mechanism or idea by being questioned ("I want to understand X") |
| [`socratic-source`](skills/socratic-source/SKILL.md) | Working through a paper, document, codebase or exam topic ("quiz me on this paper") |
| [`socratic-practice`](skills/socratic-practice/SKILL.md) | Learning by doing: a small exercise you solve yourself, run for real |
| [`socratic-debug`](skills/socratic-debug/SKILL.md) | Practicing bug hunting: observe, hypothesise, test, fix |
| [`socratic-exam`](skills/socratic-exam/SKILL.md) | An exam simulation with no hints, graded honestly afterwards |
| [`socratic-review`](skills/socratic-review/SKILL.md) | 5 to 15 minutes of repetition on the weak spots that are due |

The socratic skills come from [renepanke/socratic-learning](https://github.com/renepanke/socratic-learning).

## Installation

Like [mattpocock/skills](https://github.com/mattpocock/skills), via the
[skills.sh](https://skills.sh) CLI. It asks which agents and skills you want:

```bash
npx skills@latest add renepanke/skills
```

All skills, for Claude Code and Codex, without questions:

```bash
npx skills@latest add renepanke/skills -g -a claude-code -a codex -s '*' -y
```

Only some skills:

```bash
npx skills@latest add renepanke/skills -s handbook-writer -s socratic-concept
```

Update with `npx skills@latest update`, remove with `npx skills@latest remove`.
Re-run `add` to pick up new skills. Needs Node.js. The CLI records an install
event for skills.sh.

### Manually

Copy the folders from `skills/` to where your agent looks for skills:

| Agent | Folder |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.agents/skills/` |

## Repository layout

```
skills/
  <skill-name>/
    SKILL.md        loaded when the skill triggers; name in the frontmatter = folder name
    references/     details the skill reads on demand
    assets/         templates
    scripts/        helper scripts
    agents/         Codex metadata (openai.yaml)
```

To add a skill, create `skills/<skill-name>/SKILL.md` with `name` and
`description` in the frontmatter. The CLI finds it automatically.

## Credits

`scripts/ste-lint.py` and the writing rules in the socratic skills'
`references/writing.md` are adapted from
[ste-writing](https://github.com/1fc0nfig/ste-writing) by Ege Çelebi and Matyas
Cerny (MIT), with the license notice at the top of the script.
