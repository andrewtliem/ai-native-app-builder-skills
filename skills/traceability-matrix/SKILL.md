---
name: traceability-matrix
description: Use this skill to map student app requirements to user stories, architecture, issues, tests, demo steps, and evidence.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Traceability Matrix

**Stage:** Phase 4 — Quality Proof

## Purpose

Create an audit trail that shows how each requirement moved from PRD to implementation and evidence. This helps students prove the app satisfies the intended scope.

## Shared Principles

- **Delegate tasks, not judgment:** AI can draft and compare, but students remain responsible for decisions.
- **No vibe coding:** do not move from vague intent to generated code without artifacts.
- **Verification is the bottleneck:** every claim should lead to a check, test, or evidence item.
- **Artifacts are project memory:** if it is not saved to disk, it is not part of the project memory.
- **Small loops beat big guesses:** clarify, build, test, review, and revise in small steps.

## When to Use

- Use after `test-the-app`.
- Use before demo, grading, or final submission.
- Use when the instructor needs proof that requirements were not lost during AI-assisted coding.

## Inputs

- PRD.
- Architecture.
- Issues.
- Test plan.
- Code review, loop log, risk review, or demo evidence if available.

## Process

1. Load the required upstream artifacts from disk.
2. Preserve student intent; do not invent a different project.
3. Produce a concrete, reviewable artifact using the output format below.
4. Mark uncertainty explicitly instead of hiding it.
5. Save the artifact to the required path.
6. End with `Saved artifact:` and `Next recommended skill:`.

## Artifact Discipline

- **Write/update this file:** `docs/ai-native/17-traceability-matrix.md`
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
- `docs/ai-native/10-test-plan.md`
- Optional: `docs/ai-native/09-code-review.md`
- Optional: `docs/ai-native/11-risk-review.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists.
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Traceability Matrix

## Sources Read
- ...

## Coverage Summary
- Fully covered: ...
- Partially covered: ...
- Missing evidence: ...

## Matrix

| Requirement | User Story | Architecture Component | Issue / Task | Test / Check | Evidence | Status |
|---|---|---|---|---|---|---|
| FR-001 | US-001 | ... | Issue 01 / T001 | ... | ... | Covered / Partial / Missing |

## Missing or Weak Evidence
- ...

## Recommended Next Actions
1. ...
```

## Final Response Contract

```text
Saved artifact: docs/ai-native/17-traceability-matrix.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Every FR/SC has at least one row.
- [ ] Each row links to an issue/task and a test/check where possible.
- [ ] Evidence is concrete: screenshot, test output, demo step, or manual check.
- [ ] Missing evidence is clearly marked.
- [ ] Status values are honest.

## Common Pitfalls

1. **Marking covered without evidence.** “Implemented” is not proof.
2. **Using vague evidence.** Prefer file paths, screenshots, commands, or demo steps.
3. **Ignoring partial coverage.** Partial is acceptable if honestly recorded.

## Student Prompt Template

```text
Use `traceability-matrix`. Read PRD, architecture, issues, and test plan. Create a matrix mapping requirements to issues, tests, and evidence. Save to `docs/ai-native/17-traceability-matrix.md`.
```
