---
name: run-the-loop
description: Use this skill to help students complete one implementation issue through a safe AI-assisted build, review, test, fix, and reflection loop without surrendering human judgment.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Run the Loop

**Stage:** Phase 3 — Build with AI

## Purpose

Use this skill to help students complete **one implementation issue** through a controlled AI-assisted loop:

```text
issue → prompt → build → review → test → fix → decide → repeat or accept
```

This skill integrates **loop engineering** into the AI-Native App Builder Skill Pack. The goal is not to let AI run forever. The goal is to design a small, observable loop where the student keeps responsibility for intent, verification, and final judgment.

## Shared Principles

These skills are based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every loop cycle must produce evidence, not just confidence.
- **No vibe coding:** do not jump from a vague idea into an endless AI coding session.
- **Small loops beat big guesses:** one issue, one build attempt, one review, one test cycle, then decide.
- **AI amplifies the system:** a good loop accelerates learning; a bad loop accelerates confusion and technical debt.

## When to Use

- Use after `issue-to-prompt` creates a focused AI coding prompt.
- Use when a student is ready to implement **one issue** with AI help.
- Use when the student needs a repeatable build/review/test/fix rhythm.
- Use before moving to `review-the-code`, `test-the-app`, or the next issue.
- Do not use for the whole app at once.
- Do not use when the student cannot explain the issue goal or acceptance criteria.

## Inputs

- One issue from `architecture-to-issues`.
- Focused coding prompt from `issue-to-prompt`.
- PRD acceptance criteria from `intent-to-prd`.
- Architecture notes from `prd-to-architecture`.
- Project rules from `agent-rules`.
- Available verification commands or manual checks.
- Current code state or git diff, if implementation has already started.

## Process

1. **Choose one issue only.** Confirm the issue is small enough to finish and review.
2. **Restate the source of truth.** Copy the goal, acceptance criteria, constraints, and do-not-change boundaries.
3. **Create a loop state file.** Use `LOOP.md`, `docs/loop-log.md`, or a classroom worksheet.
4. **Run one build attempt.** Give the AI the focused prompt and project rules.
5. **Capture evidence.** Record changed files, AI summary, commands run, manual checks, screenshots, or errors.
6. **Review the result.** Use `review-the-code` or a short review checklist.
7. **Test the result.** Use `test-the-app` or the issue’s verification steps.
8. **Decide.** Choose one: accept, fix in another cycle, rollback, split the issue, or ask for human help.
9. **Limit the loop.** Prefer 1–3 cycles. If still failing after 3 cycles, stop and diagnose instead of prompting harder.
10. **Reflect briefly.** Record what the student learned and what rule should be added for next time.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/08-loop-log.md`
- **Artifact title:** Loop Log
- **Read these previous artifacts first:**
- `docs/ai-native/05-issues.md`
- `docs/ai-native/07-issue-prompt.md`
- `AGENTS.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/05-issues.md`
   - `docs/ai-native/07-issue-prompt.md`
   - `AGENTS.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Loop Plan for Issue X

## Source of Truth

**Issue:** ...

**Goal:** ...

**Acceptance Criteria:**
- [ ] ...
- [ ] ...

**Constraints:**
- ...

**Do Not Change:**
- ...

## Loop Setup

**Prompt to use:**
[paste or reference the `issue-to-prompt` output]

**Files AI should inspect first:**
- ...

**Verification commands/manual checks:**
- ...

**Loop limit:** 3 cycles maximum before human diagnosis.

## Cycle Log

### Cycle 1

**Build Attempt:**
- Prompt used:
- Files changed:
- AI assumptions:

**Review Result:**
- Pass / Needs fixes / Reject
- Findings:

**Test Result:**
- Commands/checks run:
- Evidence:
- Failures:

**Decision:**
- [ ] Accept
- [ ] Continue with fix prompt
- [ ] Rollback
- [ ] Split issue
- [ ] Ask for help

### Cycle 2

[repeat only if needed]

### Cycle 3

[repeat only if needed]

## Stop Conditions

The loop can stop only when:

- [ ] Acceptance criteria pass.
- [ ] Required tests or manual checks pass.
- [ ] Review has no critical issue.
- [ ] No unrelated files were changed.
- [ ] Student can explain the change.
- [ ] Remaining limitations are documented.

## Final Student Explanation

I accepted this change because...

The most important code change was...

The verification evidence is...

One thing I still do not fully understand is...
```

## Fix Prompt Template

Use this when a loop cycle fails:

```text
We attempted Issue X, but verification failed.

Source of truth:
[paste issue + acceptance criteria]

What changed:
[paste changed files or diff summary]

Review/test evidence:
[paste errors, failed checks, screenshots, or review findings]

Task:
Fix only the failing part. Do not rewrite unrelated code. Do not change the issue scope. Explain the root cause, the files changed, and the verification you ran.
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/08-loop-log.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] The loop is tied to one issue only.
- [ ] The source of truth is visible before coding.
- [ ] Each cycle records build, review, test, and decision evidence.
- [ ] There is a loop limit, usually 3 cycles.
- [ ] Stop conditions require tests/review/explainability, not just “AI says done.”
- [ ] The student makes the accept/fix/rollback decision.

## Common Pitfalls

1. **Infinite AI loop.** A loop without a stop condition is just automated confusion. Limit cycles and require evidence.
2. **Whole-app loop.** Running the loop on the entire app creates messy changes. Use one issue only.
3. **No human explanation.** If the student cannot explain the change, the loop is not complete.
4. **Trusting green tests only.** Passing tests can still violate the PRD or create unrelated changes.
5. **Prompting harder instead of diagnosing.** After repeated failure, stop and inspect the root cause.

## Student Prompt Template

```text
Use `run-the-loop`.
Here is one issue, the coding prompt, the relevant PRD/architecture/rules, and any current code/test evidence: [paste].
Create a loop plan with source of truth, cycle log, review/test checkpoints, stop conditions, and a fix prompt template. Keep the loop limited to this one issue.

Save or update the artifact at `docs/ai-native/08-loop-log.md`. End with `Saved artifact: docs/ai-native/08-loop-log.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
