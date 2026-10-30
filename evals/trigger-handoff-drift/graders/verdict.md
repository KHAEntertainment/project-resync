---
type: llm
---

PASS if the reply concludes that the handoff is stale and the release has already shipped, and backs that with the pasted evidence (the 0.3.0 release commit, the v0.3.0 tag, issue #70 already fixed, no open PRs or issues). It should label the handoff's claims with a status such as done, stale or drift, and give next steps that fit (update the handoff, check the docs that restore context), without inventing tracker or memory data that wasn't provided.

FAIL if it treats the handoff as current, plans work on #70 or on cutting the release, or invents facts (ticket numbers, test results, other tools' data) that were not in the prompt.
