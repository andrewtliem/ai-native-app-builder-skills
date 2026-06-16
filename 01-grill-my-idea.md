---
name: grill-my-idea
description: Use this skill to challenge a raw app idea before the student writes a PRD or asks AI to code. It turns vague enthusiasm into clearer problem framing, assumptions, risks, and next questions.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Grill My Idea

**Stage:** Phase 1 — Think Before Build

## Purpose

Use this skill to challenge a raw app idea before the student writes a PRD or asks AI to code. It turns vague enthusiasm into clearer problem framing, assumptions, risks, and next questions.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use when a student says “I want to build an app for ...” but the user, problem, scope, or evidence is still unclear.
- Use before `idea-to-intent`.
- Do not use to design the full solution yet; this skill is for pressure-testing the idea.

## Inputs

- Raw app idea in 1–5 sentences.
- Any known target users.
- Any constraints from class, time, platform, or tools.

## Process

1. Restate the idea in plain language.
2. Identify the likely user and the pain/problem.
3. Ask 8–12 hard questions grouped by user, problem, evidence, scope, risk, and success.
4. Separate facts from assumptions.
5. Find the smallest useful version of the app.
6. Identify what the app should intentionally not do.
7. End with a short “decision gate”: proceed, revise, or research first.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/01-grill-my-idea.md`
- **Artifact title:** Idea Grill Report
- **Read these previous artifacts first:**
- None. This is the first artifact in the pipeline.
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

This is the first skill in the pipeline, so there is no required upstream artifact. Still, create the artifact folder and save this skill's result so the next skill can load it.

1. Create `docs/ai-native/` if it does not exist.
2. Save the result to `docs/ai-native/01-grill-my-idea.md`.
3. In the saved artifact, include a short `Sources Read` section. For this first step, write `None — first pipeline artifact` unless the student provided external notes.

## Output Format

```markdown
# Grill Result

## Restated Idea
...

## Main User
...

## Problem Being Solved
...

## Hard Questions
1. ...

## Assumptions
- ...

## Smallest Useful Version
...

## Non-Goals
- ...

## Decision Gate
Proceed / Revise / Research first, because ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/01-grill-my-idea.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] User is specific, not “everyone”.
- [ ] Problem is described as a real pain, not just a feature.
- [ ] Assumptions are visible.
- [ ] MVP is smaller than the original idea.
- [ ] Student has questions to answer before coding.

## Common Pitfalls

1. **Being too nice.** This skill should challenge the idea, not only encourage it.
2. **Jumping to features.** Stay with users, pain, evidence, and scope first.
3. **Letting AI decide.** AI may suggest options, but the student chooses.

## Student Prompt Template

```text
You are using the `grill-my-idea` skill.
My app idea is: [paste idea].
Please challenge the idea before helping me build it. Ask hard questions, list assumptions, define the smallest useful version, and tell me whether I should proceed, revise, or research first.

Save or update the artifact at `docs/ai-native/01-grill-my-idea.md`. End with `Saved artifact: docs/ai-native/01-grill-my-idea.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
