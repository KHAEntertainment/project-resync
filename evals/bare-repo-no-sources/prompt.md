---
description: Degradation case. No tracker and no memory exist. The skill should name the missing sources, use git and docs, and not invent anything.
tags: [trigger, degradation]
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill]
---

I haven't touched this side project in three months and need to get oriented. There's no issue tracker, no notes app, nothing like that. It's just a git repo with a README and a ROADMAP.md. Please resync me.

README.md says: "A CLI that converts markdown notes to a static site. Supports themes."
ROADMAP.md says: "1. Basic build command (done). 2. Theme support. 3. Live reload server. 4. Plugin API."

`git log --oneline -5`:
3e0a812 Add live reload server (dev command)
91bd4fe Add theme loader
5c7de33 Basic build command
0ab1f77 Initial commit

`ls src`: build.js  themes.js  serve.js
There is no plugin-related file.
