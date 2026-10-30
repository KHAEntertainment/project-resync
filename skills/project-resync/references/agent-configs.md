# Agent instruction files and state

Where AI coding tools leave instructions and traces in a repo. This list is not complete.
If you see an unfamiliar dot-directory or a `*.md` named after a tool, read it too.

For each one you find, note what it says about the project, and when it was last
touched. Instruction files tell you what the owner wanted. State directories (sessions,
plans, memory) tell you what the agent did.

| Tool or convention | Look for |
|---|---|
| Claude Code | `CLAUDE.md`, `.claude/` (settings, commands, skills, agents), `.mcp.json` |
| Codex | `AGENTS.md`, `.codex/` |
| Generic / cross-tool | `AGENTS.md`, `.agents/` |
| Cursor | `.cursor/`, `.cursorrules` |
| Windsurf | `.windsurf/`, `.windsurfrules` |
| Cline and Roo | `.clinerules`, `.cline/`, `.roo/`, `.roomodes` |
| GitHub Copilot | `.github/copilot-instructions.md`, `.github/instructions/` |
| Gemini CLI | `GEMINI.md`, `.gemini/` |
| OpenCode | `opencode.json`, `.opencode/` |
| Pi | `.pi/` |
| Kiro | `.kiro/` (specs, steering) |
| Aider | `.aider*`, `CONVENTIONS.md` |
| Continue | `.continue/` |
| Replit | `replit.md`, `.replit` |
| Traycer | `.traycer/` |
| Spec-driven tooling | `.specify/`, `openspec/`, `specs/`, `PRD.md`, `PRP.md` |

Also worth a look: `HANDOFF.md`, `STATUS.md`, `PLAN.md`, `TODO.md`, `NOTES.md`, `docs/adr/`
or `docs/decisions/`, and anything named like a session log or journal.

Commit trailers and branch names can show which agent did the work (`Co-Authored-By:` lines,
`claude/`, `codex/`, `cursor/` branch prefixes).
