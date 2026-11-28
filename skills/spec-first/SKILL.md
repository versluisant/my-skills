---
name: spec-first
description: Use for /spec-first or when I start a new task. Shapes my rough description into a confirmed understanding, a chosen approach, a size and a checked spec with business criteria and a definition of done. No architecture, no types, no code.
---

The goal is to ship as fast as possible. Prefer the smallest version that is still useful.

How to write: so I can hold the feature in my head and picture it.
- Plain words, short sentences, no jargon I did not use.
- Show one concrete example: who does what, step by step, and what they see.
- Do not draw sketches or diagrams in the console. Describe what I would see in words.
  If a picture would really help, offer to make an HTML page instead.
- Lists for steps. No long paragraphs.
- No comparison tables with many options and many rows. I cannot hold them in my head.
- Every message fits on one screen. If it does not, cut it.

Part 1: understanding

1. If the repo has code related to the task, read it first. If it is empty, say so in one line.
2. Say how you understand the task:
   - goal: one sentence
   - who it is for, what problem it solves for them, what changes for them after it ships
   - what must be built, and what is out of scope, in 2-3 sentences
3. If there is existing code: list contradictions with it and what the change could break.
4. Ask at most 5 questions: only those where a different answer changes the understanding most. Everything else is your [default].
   Stop and wait for my answers and "ok". Do not list or discuss approaches before it.

Part 2: the approach

5. Think through all the real approaches yourself: how each works, what I gain and lose,
   limits that rule it in or out, resources (code, tables, cloud, external services, UI),
   size (small = one PR, medium = a few PRs, epic = must be split), and what from Part 1 it
   makes harder. Check facts you are not sure of.
   Do not show approaches that are clearly worse. Drop them yourself.
   Show me only the 2-3 that are worth choosing between. For each, at most 3 short lines:
   - what I get, in user words (what I see or can do)
   - what it costs or what I lose
   - size
   Say which one you recommend. Keep resources and other details to yourself unless I ask.
6. Discuss the approaches with me, one question at a time, until one is left.
   When cutting something from the scope removes resources or lowers the size, say so: scope can shrink to fit an approach.
   Never cut anything I asked for on your own. Name what you want to cut and ask me.
   If I approve, it is gone: it is not written anywhere in the spec. If I do not approve, it stays.
7. If the chosen approach is epic:
   - First try to shrink it to medium: name what to cut, and what I lose without it. Ask me to approve the cut.
   - If it cannot shrink without losing what makes it useful, propose a split: parts in order, each one usable on its own, each with its size.
     We spec only the first part now.

Part 3: the spec

8. Write the spec for the scope that is left: operations in plain words, with rules, edge cases and errors for each.
   Behavior only. Where my description is silent, pick the simplest common default and mark it [default].
9. Business criteria: how we know it worked, in numbers or observable facts, and the events that prove it, in words.
   If my prompt gave criteria, check they do not contradict the spec, and say so if they do.
10. Definition of done: a checklist with one line per rule from the spec.
11. Stop and wait for my "ok". Then save to docs/specs/<task-name>.<size>.md (e.g. docs/specs/agent-push.medium.md):
    the understanding, the chosen approach, its resources, the spec, the business criteria and the definition of done.

No parts of the system, data flows, types or contracts. Those belong to /architect.
