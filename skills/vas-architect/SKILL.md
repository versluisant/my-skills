---
name: vas-architect
description: Use for /vas-architect after a spec is approved. Turns the spec into architecture options, an ADR, a contract and a test skeleton. No implementation.
---

1. Propose 2 structurally different architectures for the main decision. For each: how it works, pros, cons, how it handles the non-functional points from the spec.
   Stop and wait for my choice.

2. Write an ADR for the choice: context, decision, alternatives, consequences.
3. Write the contract: types, function signatures, error codes. Every error and edge case from the spec must be visible in it.
4. Write the test skeleton: one test.todo per rule from the spec, named as the rule.
   Stop and wait for my "ok". Do not implement.
