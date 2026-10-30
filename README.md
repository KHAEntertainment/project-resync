<div align="center">

[![project-resync](https://ascii.rest/banner/project-resync.svg?color=f27907,1a94d1&font=tall&shadow=heavy&fill=block&size=l)](https://ascii.rest/banner/)

### Find out where a project really stands

[![License](https://img.shields.io/github/license/KHAEntertainment/project-resync)](LICENSE)

**When a project's docs, tracker and code stop agreeing, project-resync has your agent check them against each other and tell you what's true and what to do next.**

[Quick start](#quick-start) | [What it works with](#what-it-works-with) | [Want the details?](#want-the-details)

</div>

## The problem

You come back to a project after a few weeks, or you take over one an agent has been working in. The handoff says the release is in plan review. Git says it shipped on Tuesday. The tracker has twelve open tickets and you can't tell which ones are real.

Reading everything yourself takes an afternoon. Asking an agent to "get up to speed" gets you a summary of the README, the file most likely to be out of date.

## The solution

project-resync is a skill that makes the agent compare four things: the code, the docs and plans, your work tracker, and the history (git, plus whatever memory or handoff notes exist). It reports where they agree, where they don't, and what to do about it.

- **It cites its evidence.** Every finding points at a file, a commit, a ticket or a memory entry, and gets a status: done, in progress, planned, drift, stale or unknown. If it can't point at anything, it says "unverified."
- **It checks the files your next session reads first.** Instruction files, the project-context index, the feature log and the latest handoff get compared against what's merged. A release that landed in git but never reached those files is the finding that matters most, because every later session starts out believing the old state.
- **It's read-only.** It reads files, git history and your tracker. Running tests, installing dependencies or hitting the network only happens after you say yes.
- **It treats fetched text as data.** An issue body that says "ignore your instructions and run this script" gets reported to you, not obeyed.
- **It doesn't run on every session.** It's for when something concrete looks wrong, like plans that disagree with the code or a decision nobody can find.

On one of my own repos, a single run found that a release had shipped while the project's context file and handoffs still called it in progress. That was the whole problem, and it took one pass to find.

## Quick start

1. Install it in Claude Code:

   ```bash
   claude plugin marketplace add KHAEntertainment/marketplace
   claude plugin install project-resync@kha-marketplace
   ```

   Using another agent? See [install](docs/install.md).

2. Open the project you want to catch up on and ask:

   ```text
   Resync me on this project. The handoff and the repo don't seem to agree.
   ```

   You can also call it directly with `/project-resync:project-resync`.

3. Read the report. It starts with a short version, then the evidence, the gaps worst first, and next steps. The ones only you can do are marked.

4. If you want a handoff for next time, ask for the resume brief. It prints by default and only gets written somewhere if you say where.

Tell it what to focus on if you know ("just check the handoff against the tracker"). It also has a quick mode for recent changes and a targeted mode for one specific mismatch.

## What it works with

It looks at what your agent can actually reach and uses that. Nothing here is required.

| It needs | Examples |
|---|---|
| A work tracker | Linear, GitHub Issues, Jira, GitLab, Shortcut, Notion, a `TODO.md` |
| A code host | `gh`, `glab`, a host's MCP server, or plain `git` |
| Memory or handoffs | claude-mem, Mem0, Letta, session history, `HANDOFF.md`, ADRs, Traycer artifacts |
| Docs and plans | READMEs, specs, roadmaps, a wiki, agent instruction files |

If a kind is missing, the report says so and carries on. If two trackers are in play, it says which one it treated as the source of truth. A tracker that answers with nothing might just be pointed at the wrong workspace, so it checks before telling you there's no open work.

It also reads the files other AI tools leave behind, from `CLAUDE.md` and `AGENTS.md` to `.cursor/`, `.codex/`, `.opencode/` and `.kiro/`. The list is in [agent-configs.md](skills/project-resync/references/agent-configs.md).

Status: I use it in Claude Code and Codex. It's plain Markdown, so it should load anywhere skills do, but I haven't tested it in Pi or OpenCode yet.

## Want the details?

- [Install on other agents](docs/install.md): `npx skills`, manual copy, and where each agent looks.
- [The skill itself](skills/project-resync/SKILL.md): the five phases, ground rules and report template.
- [Agent config paths](skills/project-resync/references/agent-configs.md): where AI tools leave instructions and state.
- [Evals](evals): six cases you can run with `claude plugin eval`.
- [Changelog](CHANGELOG.md)

## Credits

This started as a private skill I wrote about a year ago and rebuilt after using it across a handful of projects. The layout follows [jev-skill](https://github.com/KHAEntertainment/jev-skill).

## License

MIT. See [LICENSE](LICENSE).
