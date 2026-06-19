---
name: project-constitution
description: Use this skill to define non-negotiable project principles and quality gates before architecture, coding, or AI-agent work.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Project Constitution

**Stage:** Phase 2 — Spec-Driven Foundation

## Purpose

Create a short project constitution that governs later AI output, architecture decisions, review, testing, and grading. The constitution is the project rulebook: if a later AI suggestion conflicts with it, the constitution wins.

## Shared Principles

- **Delegate tasks, not judgment:** AI can draft and compare, but students remain responsible for decisions.
- **No vibe coding:** do not move from vague intent to generated code without artifacts.
- **Verification is the bottleneck:** every claim should lead to a check, test, or evidence item.
- **Artifacts are project memory:** if it is not saved to disk, it is not part of the project memory.
- **Small loops beat big guesses:** clarify, build, test, review, and revise in small steps.

## When to Use

- Use after `intent-to-prd` and before or alongside `prd-to-architecture`.
- Use when students need clear quality, privacy, simplicity, testing, and explainability rules.
- Do not use as a generic motivational document; it must create enforceable project rules.

## Inputs

- PRD.
- Course constraints or grading rubric if available.
- Any non-negotiable stack, privacy, or deployment constraints.

## Process

1. Load the required upstream artifacts from disk.
2. Preserve student intent; do not invent a different project.
3. Produce a concrete, reviewable artifact using the output format below.
4. Mark uncertainty explicitly instead of hiding it.
5. Save the artifact to the required path.
6. End with `Saved artifact:` and `Next recommended skill:`.

## Artifact Discipline

- **Write/update this file:** `docs/ai-native/14-project-constitution.md`
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- Optional: course rubric, assignment brief, or `docs/ai-native/02-intent-brief.md`
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
# Project Constitution

## Sources Read
- ...

## Core Principles

### I. Human Judgment Over AI Output
...

### II. Simplicity First
...

### III. Testable Features Only
...

### IV. Privacy and Safety
...

### V. Explainability
...

## Quality Gates
- [ ] PRD has measurable success criteria
- [ ] Architecture matches the PRD
- [ ] Issues map to requirements
- [ ] Code is reviewed
- [ ] Tests or demo evidence exist

## Governance
If a later AI output conflicts with this constitution, the constitution wins.

## Open Questions
- ...
```

## Final Response Contract

```text
Saved artifact: docs/ai-native/14-project-constitution.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Principles are specific enough to enforce.
- [ ] Quality gates are checkable.
- [ ] Privacy/security expectations are explicit.
- [ ] Simplicity and explainability are included.
- [ ] The constitution can guide later review decisions.

## Common Pitfalls

1. **Writing slogans instead of rules.** “Build good software” is not enforceable.
2. **Too many principles.** Keep the constitution short enough for students to use.
3. **Ignoring course constraints.** The constitution should support grading and demonstration.

## Student Prompt Template

```text
Use `project-constitution`. Read `docs/ai-native/03-prd.md` first. Create non-negotiable project principles and quality gates, then save to `docs/ai-native/14-project-constitution.md`.
```
