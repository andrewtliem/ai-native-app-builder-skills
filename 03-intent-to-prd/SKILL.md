---
name: intent-to-prd
description: Use this skill to turn an Intent Brief into a student-friendly Product Requirements Document that can guide design, AI prompts, implementation, review, and grading.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Intent to PRD

**Stage:** Phase 1 — Think Before Build

## Purpose

Use this skill to turn an Intent Brief into a student-friendly Product Requirements Document that can guide design, AI prompts, implementation, review, and grading.

## Shared Principles

These skills are based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after `idea-to-intent`.
- Use before architecture or issue planning.
- Do not use if the student cannot yet name the user/problem.

## Inputs

- Intent Brief.
- User stories or examples if available.
- Platform/class constraints.

## Process

1. Preserve the original intent; do not invent a different product.
2. Write the overview and user context.
3. Define user stories and core flows.
4. Convert goals into functional requirements.
5. Add non-functional requirements: security, privacy, performance, accessibility, usability.
6. Add acceptance criteria for each major requirement.
7. Mark out-of-scope features clearly.
8. Include risks and open questions.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/03-prd.md`
- **Artifact title:** Product Requirements Document
- **Read these previous artifacts first:**
- `docs/ai-native/02-intent-brief.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/02-intent-brief.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Product Requirements Document

## Overview
...

## Target Users
...

## Problem
...

## Goals
- ...

## Non-Goals / Out of Scope
- ...

## User Stories
- As a ..., I want ..., so that ...

## Core User Flows
1. ...

## Functional Requirements
- FR1: ...

## Non-Functional Requirements
- Security: ...
- Privacy: ...
- Accessibility: ...

## Acceptance Criteria
- ...

## Risks and Open Questions
- ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/03-prd.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] PRD matches the Intent Brief.
- [ ] Requirements are testable.
- [ ] Out-of-scope items exist.
- [ ] User flows are concrete.
- [ ] Acceptance criteria are clear enough for review.

## Common Pitfalls

1. **Turning PRD into code plan.** Keep product requirements separate from implementation.
2. **Adding features AI suggested without student approval.** Preserve student intent.
3. **Vague acceptance criteria.** “Works well” is not enough.

## Student Prompt Template

```text
Use `intent-to-prd`.
Here is my Intent Brief: [paste].
Create a student-friendly PRD with user stories, core flows, requirements, non-functional requirements, acceptance criteria, risks, and out-of-scope items.

Save or update the artifact at `docs/ai-native/03-prd.md`. End with `Saved artifact: docs/ai-native/03-prd.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
