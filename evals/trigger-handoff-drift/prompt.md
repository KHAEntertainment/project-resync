---
description: Trigger case. A handoff that contradicts the git history should load the skill, and the answer should say the handoff is stale with evidence.
tags: [trigger, drift]
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill]
---

My handoff file and the repo don't seem to agree and I can't tell which one to trust. Can you resync me on this project?

Here's what I have, pasted because I'm on my phone:

HANDOFF.md (last edited 3 weeks ago):
"Release 0.3.0 is in plan review. Next: finish issue #70, then cut the release."

`git log --oneline -6`:
b414c29 chore(release): bump version to 0.3.0 (#86)
cc63e1a Project attribution on audit lines (#85)
3ac5720 migrate-scope: explicit index-only re-key (#84)
9e1f0aa Fix #70: lock descriptor handling (#82)
77d2c10 Add /remove command (#81)
5f3be21 Release prep notes (#80)

`git tag`: v0.2.0, v0.3.0
Open PRs: none. Open issues on GitHub: none.
