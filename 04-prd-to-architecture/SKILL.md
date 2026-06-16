---
name: prd-to-architecture
description: Use this skill to convert a PRD into a simple architecture plan before coding, so students understand system parts, data flow, risks, and technical choices.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# PRD to Architecture

**Stage:** Phase 2 — Design the System

## Purpose

Use this skill to convert a PRD into a simple architecture plan before coding, so students understand system parts, data flow, risks, and technical choices.

## Shared Principles

These skills are based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after `intent-to-prd`.
- Use before issue breakdown.
- Use for web, mobile, desktop, or API-based class projects.
- Do not over-engineer; choose the simplest architecture that satisfies the PRD.

## Inputs

- PRD.
- Preferred stack, if any.
- Deployment target, if known.
- Student/team skill level.

## Process

1. Summarize the app type and technical needs.
2. Choose the simplest viable stack.
3. Identify frontend, backend, database/storage, auth, external APIs, and deployment.
4. Draw the data flow in text.
5. Define key data models/entities.
6. Identify security/privacy concerns.
7. Identify failure points and what should happen.
8. List architecture decisions and reasons.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/04-architecture.md`
- **Artifact title:** Architecture Plan
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/03-prd.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Architecture Plan

## Stack Choice
...

## System Parts
- Frontend: ...
- Backend: ...
- Database/Storage: ...
- Auth: ...
- External Services: ...

## Data Flow
1. ...

## Data Model
- Entity: fields...

## Key Routes / Screens
- ...

## Security and Privacy Notes
- ...

## Failure Cases
- ...

## Architecture Decisions
- Decision: ... because ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/04-architecture.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Architecture is simpler than the maximum possible solution.
- [ ] Every system part has a reason.
- [ ] Data flow is understandable.
- [ ] Security/privacy risks are named.
- [ ] Student can explain the architecture verbally.

## Common Pitfalls

1. **Choosing trendy tools without reason.** Stack must fit student ability and PRD.
2. **Ignoring data ownership/privacy.** Student apps often collect personal data.
3. **Skipping failure cases.** Apps need behavior when things go wrong.

## Student Prompt Template

```text
Use `prd-to-architecture`.
Here is my PRD: [paste].
Create the simplest viable architecture plan, including system parts, data flow, data model, routes/screens, security/privacy notes, failure cases, and architecture decisions.

Save or update the artifact at `docs/ai-native/04-architecture.md`. End with `Saved artifact: docs/ai-native/04-architecture.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
