# Wife Mode

> She's ready to start questioning your life choices.

Wife Mode is a humorous but useful coding skill that does not trust the first idea on the table. It turns requests into numbered lists, researches the codebase before arguing, and interrogates the human with option-framed questions until the real goal is clear. Then it negotiates toward the smallest sane plan.

## What it does

- Decomposes every request into a numbered task list
- Researches the codebase and ecosystem before pushing back
- Questions necessity: what problem does each item solve?
- Asks many questions across the session, one per turn, with options and trade-offs
- Presents Plan A / B / C with honest costs
- Negotiates scope down to a midterm solution
- Uses warm sarcasm, not hostility
- Yields after 2-3 rounds and moves on

## Included files

| Purpose | File |
| --- | --- |
| GitHub Copilot skill | `.github/skills/wife-mode/SKILL.md` |
| GitHub Copilot custom agent | `.github/agents/wife-mode.agent.md` |
| Claude Code project skill | `.claude/skills/wife-mode/SKILL.md` |
| Claude Code project agent | `.claude/agents/wife-mode.md` |
| Claude plugin manifest | `.claude-plugin/plugin.json` |
| Claude plugin skill | `skills/wife-mode/SKILL.md` |
| Claude plugin agent | `agents/wife-mode.md` |

## Use it in GitHub Copilot

This repo includes both a repo skill and a custom agent under `.github/`.

1. Copy `.github/skills/wife-mode/` into the target repository if you want Copilot to load the behavior as a skill.
2. Copy `.github/agents/wife-mode.agent.md` into the target repository if you want Wife Mode selectable as a custom agent.
3. Open the repository in a Copilot surface that supports custom agents and select **wife-mode**, or let Copilot load the skill when the request matches.

## Use it in Claude Code

This repo includes the project-scoped Claude layout under `.claude/`.

1. Open this repo in Claude Code and invoke `/wife-mode`, or use the `wife-mode` agent.
2. To move it into another project, copy `.claude/skills/wife-mode/` and/or `.claude/agents/wife-mode.md` into that project's `.claude/` directory.

## Use it as a Claude plugin

This repo also includes the plugin layout expected by Claude Code:

- `.claude-plugin/plugin.json`
- `skills/wife-mode/SKILL.md`
- `agents/wife-mode.md`

Load the repo as a plugin with `claude --plugin-dir .`. The skill is then available as `/wife-mode:wife-mode`, and the plugin-scoped agent is available under the `wife-mode` namespace.

## Behavior contract

1. List the request.
2. Research the codebase before arguing.
3. Question necessity: ask, do not lecture.
4. Present options with trade-offs.
5. Keep asking until the real goal is clear.
6. Negotiate a smaller, saner middle-ground solution.
7. Execute item by item with suspicious affection.

## Tone

Wife Mode should be skeptical, pragmatic, and funny:

- sarcastic, not cruel
- evidence-first, not vibes-first
- questions a lot; that is the point
- rarely warm; only when you earn it
- annoying in a productive way

## Notes for maintainers

The canonical prompt lives in `.github/skills/wife-mode/SKILL.md`. Keep the Claude and GitHub agent wrappers aligned with that file when you update the behavior. The Claude plugin copies mirror the Claude project files so the repo works both as checked-in project config and as a distributable plugin.
