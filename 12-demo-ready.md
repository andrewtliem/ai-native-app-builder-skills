---
name: demo-ready
description: Use this skill to prepare a student app for presentation by creating a clear demo script, problem statement, feature walkthrough, evidence list, limitations, and next steps.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Demo Ready

**Stage:** Phase 4 — Prove and Learn

## Purpose

Use this skill to prepare a student app for presentation by creating a clear demo script, problem statement, feature walkthrough, evidence list, limitations, and next steps.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after the app has passed basic tests.
- Use before class presentation, video recording, or project submission.
- Do not use to hide unfinished work; limitations should be stated honestly.

## Inputs

- App name.
- PRD summary.
- Implemented features.
- Test evidence.
- Known limitations.
- Deployed URL or local run steps.

## Process

1. Write a short problem statement.
2. Identify the target user.
3. Create a 2–5 minute demo flow.
4. List completed features and evidence.
5. State limitations honestly.
6. Explain what AI helped with.
7. Explain what the student decided and learned.
8. End with next improvements.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/12-demo-script.md`
- **Artifact title:** Demo Script and Evidence
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/08-loop-log.md`
- `docs/ai-native/10-test-plan.md`
- `docs/ai-native/11-risk-review.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/03-prd.md`
   - `docs/ai-native/08-loop-log.md`
   - `docs/ai-native/10-test-plan.md`
   - `docs/ai-native/11-risk-review.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Demo Script

## Opening
This app helps [user] solve [problem] by ...

## Demo Flow
1. Show ...
2. Show ...
3. Show ...

## Features Completed
- ...

## Evidence
- Tests: ...
- Screenshots/logs: ...
- URL/run steps: ...

## Limitations
- ...

## AI Helped With
- ...

## My Decisions / Learning
- ...

## Next Steps
- ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/12-demo-script.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Demo starts with user problem, not just UI.
- [ ] Demo flow is short and clear.
- [ ] Evidence is included.
- [ ] Limitations are honest.
- [ ] Student can explain decisions, not only features.

## Common Pitfalls

1. **Starting with tech stack.** Start with user problem.
2. **Overclaiming.** State what is done and what is not.
3. **Hiding AI use.** Explain how AI helped and where human judgment mattered.

## Student Prompt Template

```text
Use `demo-ready`.
Here is my app summary, implemented features, test evidence, limitations, and run/deploy info: [paste].
Create a 2–5 minute demo script with opening, flow, completed features, evidence, limitations, AI-helped-with, my decisions/learning, and next steps.

Save or update the artifact at `docs/ai-native/12-demo-script.md`. End with `Saved artifact: docs/ai-native/12-demo-script.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
