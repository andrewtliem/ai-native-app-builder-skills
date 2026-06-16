---
name: test-the-app
description: Use this skill to convert requirements and implemented features into a practical test plan with manual checks, acceptance tests, edge cases, and demo verification.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Test the App

**Stage:** Phase 3 — Build with AI

## Purpose

Use this skill to convert requirements and implemented features into a practical test plan with manual checks, acceptance tests, edge cases, and demo verification.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after one feature or milestone is implemented.
- Use before demo/submission.
- Use when students need evidence that the app works.
- Do not treat testing as optional because AI said the code is done.

## Inputs

- PRD acceptance criteria.
- Implemented feature list.
- Known environment/platform.
- Existing test commands, if any.

## Process

1. Extract acceptance criteria from the PRD.
2. Map each criterion to a manual or automated test.
3. Add happy path, edge cases, failure cases, and misuse cases.
4. Include setup/test data.
5. Define expected results.
6. Include a demo checklist.
7. Separate must-pass tests from nice-to-have tests.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/10-test-plan.md`
- **Artifact title:** Test Plan and Test Results
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/05-issues.md`
- `docs/ai-native/08-loop-log.md`
- `docs/ai-native/09-code-review.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/03-prd.md`
   - `docs/ai-native/05-issues.md`
   - `docs/ai-native/08-loop-log.md`
   - `docs/ai-native/09-code-review.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Test Plan

## Scope
...

## Must-Pass Tests
### Test 1: ...
**Steps:** ...
**Expected Result:** ...

## Edge Cases
- ...

## Failure Cases
- ...

## Automated Test Suggestions
- ...

## Demo Checklist
- ...

## Evidence to Collect
- Screenshots / logs / test output / deployed URL
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/10-test-plan.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Every major acceptance criterion has a test.
- [ ] Failure cases are included.
- [ ] Expected result is clear.
- [ ] Evidence to collect is listed.
- [ ] Demo checklist covers the main user flow.

## Loop Handoff

If tests fail, return the failure evidence to `run-the-loop` and create a focused fix prompt. If tests pass, still confirm the student can explain the behavior and that the change matches the PRD.

## Common Pitfalls

1. **Only testing the happy path.** Real apps fail at edges.
2. **No expected result.** A test without expected behavior is vague.
3. **No evidence.** Students should capture proof: screenshot, logs, test output, deployed URL.

## Student Prompt Template

```text
Use `test-the-app`.
Here is my PRD acceptance criteria and implemented features: [paste].
Create a test plan with must-pass tests, edge cases, failure cases, automated test suggestions, demo checklist, and evidence to collect.

Save or update the artifact at `docs/ai-native/10-test-plan.md`. End with `Saved artifact: docs/ai-native/10-test-plan.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
