---
name: architecture-to-issues
description: Use this skill to break a PRD and architecture plan into small, ordered implementation issues that AI agents or students can work on one at a time.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Architecture to Issues

**Stage:** Phase 2 — Design the System

## Purpose

Use this skill to break a PRD and architecture plan into small, ordered implementation issues that AI agents or students can work on one at a time.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after `prd-to-architecture`.
- Use before coding.
- Use when students need a backlog with clear acceptance criteria.
- Do not create giant issues like “build the whole app”.

## Inputs

- PRD.
- Architecture Plan.
- Deadline or project milestone, if known.

## Process

1. Identify implementation layers: setup, data model, UI shell, core flows, validation, tests, deployment.
2. Split work into small issues.
3. Order issues by dependency.
4. For each issue, define goal, context, likely files, acceptance criteria, verification steps, and risk level.
5. Mark what AI may implement and what the student must judge.
6. Keep each issue reviewable in one sitting.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/05-issues.md`
- **Artifact title:** Implementation Issues
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/03-prd.md`
   - `docs/ai-native/04-architecture.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Implementation Issues

## Issue 1: ...
**Goal:** ...
**Depends on:** none / Issue X
**Likely Files:** ...
**Acceptance Criteria:**
- ...
**Verification:**
- ...
**AI Can Help With:** ...
**Student Must Judge:** ...
**Risk Level:** Low / Medium / High

## Issue 2: ...
...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/05-issues.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Each issue has one main goal.
- [ ] Issues are ordered.
- [ ] Acceptance criteria are checkable.
- [ ] Verification steps are included.
- [ ] Human judgment is separated from AI work.

## Common Pitfalls

1. **Making issues too large.** If it cannot be reviewed clearly, split it.
2. **No verification step.** Every issue needs evidence.
3. **Letting AI own judgment.** Student decides if the issue satisfies intent.

## Student Prompt Template

```text
Use `architecture-to-issues`.
Here is my PRD and Architecture Plan: [paste].
Create ordered implementation issues. Each issue must include goal, dependencies, likely files, acceptance criteria, verification steps, AI-can-help-with, student-must-judge, and risk level.

Save or update the artifact at `docs/ai-native/05-issues.md`. End with `Saved artifact: docs/ai-native/05-issues.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
