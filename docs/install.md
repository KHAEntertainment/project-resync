# Install

project-resync is one skill: `skills/project-resync/SKILL.md`, plus a reference file next to
it. Any agent that loads skills from a folder can use it.

## Claude Code (plugin marketplace)

```bash
claude plugin marketplace add KHAEntertainment/marketplace
claude plugin install project-resync@kha-marketplace
```

Or inside a session:

```text
/plugin marketplace add KHAEntertainment/marketplace
/plugin install project-resync@kha-marketplace
```

The skill loads when a task calls for it. To run it yourself, use
`/project-resync:project-resync`.

## Any agent (`npx skills`)

```bash
npx skills add KHAEntertainment/project-resync                  # interactive: pick agents
npx skills add KHAEntertainment/project-resync -a codex -a pi
npx skills add KHAEntertainment/project-resync -g               # global install
```

The CLI finds `skills/project-resync/SKILL.md` and links it into each agent's skills
folder. Update with `npx skills update`.

## Manual

Copy the `skills/project-resync` folder (keep `references/` with it) into your agent's skills
folder:

| Agent | Folder |
|---|---|
| Claude Code | `~/.claude/skills/` (global) or `.claude/skills/` (one project) |
| Codex | `~/.codex/skills/` or `~/.agents/skills/` |
| Others | check the agent's docs for its skills folder; `~/.agents/skills/` is a common shared one |

Then ask the agent to resync you on the project. An agent that loads skills by description will pick
it up from the wording in `SKILL.md`.

## Check it works

Ask: "My handoff and the repo don't agree. Resync me." The agent should name the sources it
found, compare them, and cite evidence for each finding. If it just summarizes the README, the skill didn't load.

## Run the evals (optional)

```bash
claude plugin eval .
```

This runs six cases from `evals/` against the plugin and uses model calls, so it takes a few
minutes and costs a little. The cases don't run shell commands or touch your files.
