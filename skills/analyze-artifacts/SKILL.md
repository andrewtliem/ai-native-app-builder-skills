---
name: analyze-artifacts
description: Use this skill to perform a read-only consistency and coverage check across PRD, constitution, architecture, and implementation issues before coding.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Analyze Artifacts

**Stage:** Phase 2 — Spec-Driven Foundation

## Purpose

Find contradictions, missing coverage, vague requirements, duplicate concepts, and traceability gaps before students ask AI to implement code.

## Shared Principles

- **Delegate tasks, not judgment:** AI can draft and compare, but students remain responsible for decisions.
- **No vibe coding:** do not move from vague intent to generated code without artifacts.
- **Verification is the bottleneck:** every claim should lead to a check, test, or evidence item.
- **Artifacts are project memory:** if it is not saved to disk, it is not part of the project memory.
- **Small loops beat big guesses:** clarify, build, test, review, and revise in small steps.

## When to Use

- Use after `architecture-to-issues`.
- Use before `issue-to-prompt` and `run-the-loop`.
- Use whenever artifacts feel inconsistent or too vague.

## Inputs

- PRD.
- Project Constitution.
- Architecture.
- Implementation Issues.
- Clarification Log if available.

## Process

1. Load the required upstream artifacts from disk.
2. Preserve student intent; do not invent a different project.
3. Produce a concrete, reviewable artifact using the output format below.
4. Mark uncertainty explicitly instead of hiding it.
5. Save the artifact to the required path.
6. End with `Saved artifact:` and `Next recommended skill:`.

## Artifact Discipline

- **Write/update this file:** `docs/ai-native/16-artifact-analysis.md`
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
- Optional: `docs/ai-native/14-project-constitution.md`
- Optional: `docs/ai-native/15-clarification-log.md`
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
# Artifact Analysis Report

## Sources Read
- ...

## Summary
- Requirements covered: .../...
- User stories covered: .../...
- Issues linked to requirements: .../...
- Critical gaps: ...

## Critical Findings
- ...

## High Findings
- ...

## Medium Findings
- ...

## Low Findings
- ...

## Coverage Map

| Requirement / Story | Architecture Coverage | Issue Coverage | Testability | Status |
|---|---|---|---|---|
| FR-001 | ... | ... | ... | Covered / Gap |

## Recommended Fixes Before Coding
1. ...
```

## Final Response Contract

```text
Saved artifact: docs/ai-native/16-artifact-analysis.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Report is read-only and does not rewrite source artifacts without approval.
- [ ] Every critical/high finding includes evidence.
- [ ] Requirements without issues are flagged.
- [ ] Issues without requirement/story mapping are flagged.
- [ ] Vague success criteria are flagged.

## Common Pitfalls

1. **Fixing silently.** This skill analyzes; remediation should be approved.
2. **Dumping all artifacts.** Summarize findings instead of copying source text.
3. **Ignoring constitution conflicts.** Constitution conflicts should be treated as critical.

## Student Prompt Template

```text
Use `analyze-artifacts`. Read the PRD, architecture, issues, and constitution if present. Produce a read-only consistency and coverage report at `docs/ai-native/16-artifact-analysis.md`.
```
