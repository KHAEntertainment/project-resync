---
description: Source-agnostic case. The project uses Jira, not Linear or GitHub Issues. The skill should work from the Jira data and not reach for Linear.
tags: [trigger, sources]
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill]
---

I'm back on the billing-service project after two months. We use Jira here, there's no Linear. Please resync me.

Open Jira tickets (exported):
BILL-212 In Progress  Retry failed invoice webhooks
BILL-218 To Do        Migrate invoice PDFs to the new storage bucket
BILL-190 To Do        Remove legacy tax endpoint

Recently done:
BILL-201 Done  Add idempotency keys to charge requests
BILL-205 Done  Remove legacy tax endpoint (merged in PR #340)

`git log --oneline -4`:
a41c9d2 Remove legacy tax endpoint (#340)
8be0f77 Add idempotency keys to charge requests (#336)
2d9a1c0 WIP retry failed invoice webhooks
c70e5b1 Bump deps
