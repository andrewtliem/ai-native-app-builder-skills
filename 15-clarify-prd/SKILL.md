---
name: clarify-prd
description: Use this skill to identify underspecified areas in a student PRD by asking up to five targeted clarification questions before architecture or coding.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Clarify Prd

**Stage:** Phase 2 — Spec-Driven Foundation

## Purpose

Reduce ambiguity before design and implementation. This skill turns vague PRD language into concrete decisions that affect architecture, data modeling, tests, UX, security, or scope.

## Shared Principles

- **Delegate tasks, not judgment:** AI can draft and compare, but students remain responsible for decisions.
- **No vibe coding:** do not move from vague intent to generated code without artifacts.
- **Verification is the bottleneck:** every claim should lead to a check, test, or evidence item.
- **Artifacts are project memory:** if it is not saved to disk, it is not part of the project memory.
- **Small loops beat big guesses:** clarify, build, test, review, and revise in small steps.

## When to Use

- Use after `intent-to-prd`.
- Use before `prd-to-architecture`.
- Use when the PRD contains vague words like “simple,” “secure,” “fast,” “easy,” “admin,” or “manage” without concrete meaning.

## Inputs

- PRD.
- Intent Brief if needed.
- Optional course constraints.

## Process

1. Load the required upstream artifacts from disk.
2. Preserve student intent; do not invent a different project.
3. Produce a concrete, reviewable artifact using the output format below.
4. Mark uncertainty explicitly instead of hiding it.
5. Save the artifact to the required path.
6. End with `Saved artifact:` and `Next recommended skill:`.

## Artifact Discipline

- **Write/update this file:** `docs/ai-native/15-clarification-log.md`
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- Optional: `docs/ai-native/02-intent-brief.md`
- Optional: `docs/ai-native/14-project-constitution.md`
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
# PRD Clarification Log

## Sources Read
- ...

## Ambiguity Scan Summary

| Area | Status | Notes |
|---|---|---|
| User roles | Clear / Partial / Missing | ... |
| Data model | Clear / Partial / Missing | ... |
| UX flows | Clear / Partial / Missing | ... |
| Edge cases | Clear / Partial / Missing | ... |
| Security/privacy | Clear / Partial / Missing | ... |
| Success criteria | Clear / Partial / Missing | ... |

## Clarification Questions

Ask at most 5 questions. For each question include why it matters and recommended default.

| # | Question | Why It Matters | Recommended Default | Student Answer |
|---|---|---|---|---|
| Q1 | ... | ... | ... | ... |

## Decisions Added Back to PRD
- ...

## Remaining Open Questions
- ...
```

## Final Response Contract

```text
Saved artifact: docs/ai-native/15-clarification-log.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] No more than five high-impact questions.
- [ ] Questions materially affect design, tests, security, UX, or scope.
- [ ] Each question has a recommended default.
- [ ] Student answers are recorded.
- [ ] Remaining uncertainty is explicit.

## Common Pitfalls

1. **Asking cosmetic questions.** Only ask questions that change implementation or verification.
2. **Asking too many questions.** Students need focus, not a survey.
3. **Failing to update the PRD.** Clarifications must become project memory.

## Student Prompt Template

```text
Use `clarify-prd`. Read `docs/ai-native/03-prd.md` first. Identify underspecified areas and ask up to five targeted questions. Save the log to `docs/ai-native/15-clarification-log.md`.
```
