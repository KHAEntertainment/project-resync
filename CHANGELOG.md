# Changelog

## 0.1.0 (2026-10-30)

First public version. It started as a private skill from about a year ago and was rebuilt
in October 2026.

- One skill, `project-resync`, with five phases: find the sources, pull external
  context, read local docs, check the code and history, compare and report.
- Works with whatever tracker, code host, memory and docs the project has. Linear, GitHub
  Issues, claude-mem and Traycer artifacts are examples, not requirements. A missing
  source is reported, not invented.
- Modes: Full, Quick and Targeted (one named discrepancy).
- Read-only by default. Tests, installs and audits run only after you say yes.
- Findings carry a status and cite their evidence. Text pulled from issues, PRs and
  memory is treated as data, not instructions.
- Optional resume brief, printed by default.
- `references/agent-configs.md`: where AI coding tools leave instructions and state.
- Six `claude plugin eval` cases: handoff drift, non-Linear tracker, no sources at all,
  heavy-check consent, prompt injection in an issue, and a non-trigger. All six pass,
  2 runs each, as of 2026-10-28.

Changes from the private version:

- Removed the Linear, GitHub and Claude-Mem hard-wiring and the leftover Core Memory
  references.
- Triggers on evidence of stale state, not on every session start.
- Works from pasted facts when the project isn't in the working directory, marking
  findings unverified. Won't start an install or test run in the background to save you
  the wait.
- Added the read-only rule, the empty-result check, and the check on files that restore
  context.
