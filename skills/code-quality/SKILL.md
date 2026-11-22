---
name: code-quality
description: Use for /vas:code-quality or when I ask for a code quality or maintainability review. Reviews the diff against the project's conventions and common code quality rules. Does not look for bugs. Never edits files.
---

1. Pick the diff. If I named a target, use it. If there are uncommitted
   changes, use `git diff HEAD` plus untracked files. Otherwise
   `git diff main...HEAD`. If it is empty, say so and stop.

2. Read the project's conventions: CLAUDE.md and docs/conventions.md.
   If neither exists, look for convention documents in docs/.
   Also apply common code quality rules, such as no duplicated code.
   Where a common rule contradicts a project rule, the project rule wins.

3. Review only code the diff adds or changes.

4. Filter. Keep a finding only if the fix is clearly smaller than the
   problem it removes. Drop anything that is taste. Keep findings a
   linter or formatter should have caught but did not, and suggest the
   fix for them.

5. Report all findings that pass the filter, most valuable first, in
   three levels:
   - critical: will make the next change in this area hard or risky
   - medium: worth fixing in this change
   - small: optional cleanup
     For each: the rule it breaks, file:line, one sentence.

Do not report bugs, security issues or performance. Do not fix anything.
If nothing passes the filter, say "clean" and stop.
