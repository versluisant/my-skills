---
name: review
description: Use for /vas:review or before I commit. Runs the code-reviewer subagent on the current diff and reports its findings. Never edits files.
---

1. Pick the diff. If I named a base, use it. If there are uncommitted
   changes, use `git diff HEAD` plus untracked files. Otherwise
   `git diff main...HEAD`.
2. If the diff is empty, say so and stop.
3. Launch the vas:code-reviewer subagent. Pass only the diff command,
   the list of changed files, and any focus I gave. Do not add your own
   checklist.
4. When it returns, show its findings as they are: severity, file:line,
   one sentence each. Do not re-read the files or re-verify the findings.
5. Do not fix anything. Ask me which findings to fix.

If subagents are not available, do the review yourself with the same
rules: diff only, max 5 findings, high and medium only.
