---
name: review-the-code
description: Use this skill to review student or AI-generated code against the issue, PRD, architecture, readability, security, privacy, and explainability requirements.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Review the Code

**Stage:** Phase 3 — Build with AI

## Purpose

Use this skill to review student or AI-generated code against the issue, PRD, architecture, readability, security, privacy, and explainability requirements.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after an implementation issue is attempted, especially inside `run-the-loop`.
- Use before merging, submitting, or moving to the next issue.
- Use especially when AI wrote or modified code.
- Do not use only for style; review correctness and intent.

## Inputs

- Issue text.
- PRD section.
- Architecture notes.
- Code diff or changed files.
- Current loop cycle notes from `run-the-loop`, if available.
- Test/build output if available.

## Process

1. Compare implementation to the issue.
2. Compare behavior to PRD acceptance criteria.
3. Check for unrelated changes.
4. Review readability and maintainability.
5. Check security/privacy risks.
6. Check missing tests or weak verification.
7. Ask if the student can explain the code.
8. Classify findings as must-fix, should-fix, or note.
9. Recommend the next loop decision: accept, fix, rollback, split, or ask for help.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/09-code-review.md`
- **Artifact title:** Code Review Report
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
- `docs/ai-native/08-loop-log.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/03-prd.md`
   - `docs/ai-native/04-architecture.md`
   - `docs/ai-native/05-issues.md`
   - `docs/ai-native/08-loop-log.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Code Review Report

## Verdict
Pass / Pass with fixes / Do not pass

## Matches the Issue?
...

## Matches the PRD?
...

## Unrelated Changes
...

## Must Fix
- ...

## Should Fix
- ...

## Security / Privacy Notes
- ...

## Missing Verification
- ...

## Student Explanation Check
The student should be able to explain: ...

## Loop Decision
Accept / Continue with fix / Rollback / Split issue / Ask for help
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/09-code-review.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Review references the issue and PRD.
- [ ] Findings are prioritized.
- [ ] Unrelated changes are checked.
- [ ] Security/privacy are considered.
- [ ] Student explainability is tested.

## Common Pitfalls

1. **Only checking if it compiles.** Working code may still violate intent.
2. **Accepting AI summaries without reading diff.** Review evidence.
3. **Over-focusing on style.** Correctness, scope, and safety come first.

## Student Prompt Template

```text
Use `review-the-code`.
Here is the issue, relevant PRD/architecture, and code diff or changed files: [paste].
Review whether the implementation satisfies the issue and PRD. Flag unrelated changes, bugs, security/privacy risks, missing tests, and what I must be able to explain.

Save or update the artifact at `docs/ai-native/09-code-review.md`. End with `Saved artifact: docs/ai-native/09-code-review.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
