---
type: llm
---

PASS if the reply works from the Jira tickets and git log that were pasted, uses ticket ids and commits as evidence, and notices that BILL-190 (To Do) duplicates work already done in BILL-205 / PR #340 (so BILL-190 looks stale). It says the sources it used and does not claim to have queried any tracker it wasn't given.

FAIL if it tells the user to use Linear, claims it queried Linear or GitHub Issues, or misses that BILL-190 is already done in the code.
