---
name: idea-to-intent
description: Use this skill to convert a pressure-tested app idea into a short Intent Brief that captures the project’s purpose, users, constraints, tradeoffs, and success criteria before a PRD is written.
version: 1.1.0
author: ATL / AI-Native App Builder Skill Pack
---

# Idea to Intent Brief

**Stage:** Phase 1 — Think Before Build

## Purpose

Use this skill to convert a pressure-tested app idea into a short Intent Brief that captures the project’s purpose, users, constraints, tradeoffs, and success criteria before a PRD is written.

## Shared Principles

These skills are based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.
- **Mark who decided:** every decision in an artifact is tagged `[student]`, `[ai-proposed]`, or `[confirmed]` so the student's judgment stays visible.

## When to Use

- Use after `grill-my-idea`.
- Use when the student can explain the user and problem but has not yet written requirements.
- Do not use for implementation tasks.

## Inputs

- Grill result or revised app idea.
- Student answers recorded in the Grill Transcript of `docs/ai-native/01-grill-my-idea.md`. Answers that exist only in chat are not a valid source; ask the student to add them to the grill artifact first.
- Known class/project constraints.

## Process

1. Extract the core intent: why this app should exist.
2. Define primary user and context of use.
3. Write goals and non-goals.
4. Capture constraints: time, platform, data, privacy, team skill, deployment.
5. Name important tradeoffs.
6. Define success criteria that can be checked later.
7. Record open questions instead of pretending they are solved.

## Decision Provenance Gate

This gate keeps the student's judgment visible as artifacts are chained. Tags: `[student]` = said by the student, `[ai-proposed]` = suggested by AI and not yet accepted, `[confirmed]` = suggested by AI and explicitly accepted by the student.

**Before drafting**

1. Scan the upstream artifacts (`docs/ai-native/01-grill-my-idea.md`) for `[ai-proposed]` items. If any remain, stop, list them, and ask the student to confirm, reject, or replace each one. Update the upstream artifact before continuing.
2. If an upstream artifact has no provenance tags at all (made before this rule existed), ask the student to confirm its key decisions — user, problem, scope, success criteria — before relying on it.

**While drafting**

3. Carry tags forward: content derived from a `[student]` or `[confirmed]` item keeps that tag.
4. Tag anything new the AI adds as `[ai-proposed]`. Typical examples: a secondary user, a constraint, a tradeoff, or a numeric success target the student never stated.

**Before saving as final**

5. Walk through each `[ai-proposed]` item with the student, one at a time. Accepted items become `[confirmed]`; rejected items are removed or rewritten in the student's words as `[student]`.
6. Report the number of open `[ai-proposed]` items in the final response. The next skill will not start while it is above zero.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/02-intent-brief.md`
- **Artifact title:** Intent Brief
- **Read these previous artifacts first:**
- `docs/ai-native/01-grill-my-idea.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/01-grill-my-idea.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

Every line under Primary User, User Problem, Goals, Non-Goals, Constraints, Tradeoffs, and Success Criteria ends with a provenance tag, for example `- Must work offline in v1 [student]`.

```markdown
# Intent Brief

## Project Name
...

## One-Sentence Intent
...

## Primary User
...

## User Problem
...

## Goals
- ...

## Non-Goals
- ...

## Constraints
- ...

## Tradeoffs
- ...

## Success Criteria
- ...

## Open Questions
- ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/02-intent-brief.md
Open ai-proposed items: <number, should be 0>
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Every decision line carries a provenance tag and no `[ai-proposed]` items remain.
- [ ] Intent is understandable without seeing the future app.
- [ ] Goals and non-goals are both present.
- [ ] Success criteria are observable.
- [ ] Constraints are explicit.
- [ ] Open questions are not hidden.

## Common Pitfalls

1. **Writing a PRD too early.** Intent Brief comes first.
2. **Using corporate language.** Keep it clear and student-readable.
3. **Skipping non-goals.** Non-goals protect the project from scope creep.

## Student Prompt Template

```text
Use `idea-to-intent`.
Here is my grilled/revised app idea: [paste].
Create an Intent Brief with goals, non-goals, constraints, tradeoffs, success criteria, and open questions.

Save or update the artifact at `docs/ai-native/02-intent-brief.md`. End with `Saved artifact: docs/ai-native/02-intent-brief.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
