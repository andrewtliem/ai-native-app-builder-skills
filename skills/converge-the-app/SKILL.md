---
name: converge-the-app
description: Use this skill to compare the current implemented app against PRD, architecture, issues, tests, and evidence, then list remaining work.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Converge The App

**Stage:** Phase 4 — Quality Proof

## Purpose

Close the gap between “the app runs” and “the app satisfies the intended requirements.” This skill identifies done, missing, partial, contradictory, and unrequested work.

## Shared Principles

- **Delegate tasks, not judgment:** AI can draft and compare, but students remain responsible for decisions.
- **No vibe coding:** do not move from vague intent to generated code without artifacts.
- **Verification is the bottleneck:** every claim should lead to a check, test, or evidence item.
- **Artifacts are project memory:** if it is not saved to disk, it is not part of the project memory.
- **Small loops beat big guesses:** clarify, build, test, review, and revise in small steps.

## When to Use

- Use after implementation and testing.
- Use before demo or final submission.
- Use when students need to decide whether to accept, fix, split, or defer remaining work.

## Inputs

- PRD.
- Architecture.
- Issues.
- Loop log.
- Code review.
- Test plan.
- Traceability matrix if available.
- Current codebase state.

## Process

1. Load the required upstream artifacts from disk.
2. Preserve student intent; do not invent a different project.
3. Produce a concrete, reviewable artifact using the output format below.
4. Mark uncertainty explicitly instead of hiding it.
5. Save the artifact to the required path.
6. End with `Saved artifact:` and `Next recommended skill:`.

## Artifact Discipline

- **Write/update this file:** `docs/ai-native/18-convergence-report.md`
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
- `docs/ai-native/08-loop-log.md`
- `docs/ai-native/09-code-review.md`
- `docs/ai-native/10-test-plan.md`
- Optional: `docs/ai-native/17-traceability-matrix.md`
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
# Convergence Report

## Sources Read
- ...

## Current App Evidence Inspected
- Files/code areas: ...
- Test outputs: ...
- Screenshots/demo checks: ...

## What Is Done
- ...

## What Is Missing
- ...

## What Is Partial
- ...

## What Contradicts the Artifacts
- ...

## Unrequested or Risky Additions
- ...

## Follow-up Issues
- [ ] ...

## Submission Recommendation
Ready / Not ready / Ready with limitations because ...
```

## Final Response Contract

```text
Saved artifact: docs/ai-native/18-convergence-report.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Findings trace back to PRD, architecture, issue, test, or constitution.
- [ ] Missing and partial work are separated.
- [ ] Unrequested features are surfaced honestly.
- [ ] Follow-up issues are actionable.
- [ ] Submission recommendation is evidence-based.

## Common Pitfalls

1. **Treating running app as done app.** Running is only one signal.
2. **Rewriting old issues silently.** Add follow-up work; do not erase history.
3. **Over-claiming readiness.** Be honest about limitations.

## Student Prompt Template

```text
Use `converge-the-app`. Read the PRD, architecture, issues, loop log, code review, and test plan. Inspect the current app/code if available. Produce a convergence report at `docs/ai-native/18-convergence-report.md`.
```
