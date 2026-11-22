---
name: vas-spec
description: Use for /vas-spec or when I start a new task. Shapes my rough description into a checked spec. No types, no code.
---

1. If the repo has code related to the task, read it first. If it is empty, say so in one line.
2. Restate the task in 2-3 sentences.
3. If there is existing code: list contradictions with it and what the change could break.
4. Write the spec: operations in plain words, with rules, edge cases and errors for each. Then what is out of scope.
   Behavior only. No architecture, storage, language or scale decisions.
   Where my description is silent, pick the simplest common default and mark it [default].
5. Ask at most 5 questions: only those where a different answer changes the behavior most. Everything else stays a [default].
6. List non-functional points (scale, latency) separately in 2-3 lines. They do not block the spec.
   Stop and wait for my answers and "ok". Then save the spec to docs/specs/<task-name>.md.
