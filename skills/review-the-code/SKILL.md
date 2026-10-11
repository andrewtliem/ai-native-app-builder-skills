---
name: review-the-code
description: Use this skill to review student or AI-generated code against the issue, PRD, architecture, readability, security, privacy, and explainability requirements.
version: 1.1.0
author: ATL / AI-Native App Builder Skill Pack
---

# Review the Code

**Stage:** Phase 3 — Build with AI

## Purpose

Use this skill to review student or AI-generated code against the issue, PRD, architecture, readability, security, privacy, and explainability requirements.

## Shared Principles

These skills are based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.
- **Mark who decided:** every decision in an artifact is tagged `[student]`, `[ai-proposed]`, or `[confirmed]` so the student's judgment stays visible.

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

### Part A — Student reads first (before any AI review)

1. Pick **one** changed function or block that carries the most logic for this issue, and **one** edge case relevant to it (empty input, missing data, invalid value, failure of storage or network, and so on).
2. Ask the student, without showing any AI explanation or review yet:
   - What does this code do, and why is it written this way? (own words)
   - What happens for this edge case? (a concrete prediction: output, state, or error)
   - What is one thing in this change you suspect could be wrong?
3. Record the student's answers **verbatim**. Do not correct them yet.
4. Check the prediction by tracing the code or running it. Record whether the prediction was correct.
5. Rate the explanation: **Understood** (explanation and prediction correct), **Partial** (one of them wrong), or **Not yet** (both wrong or no answer).

### Part B — Review

6. Compare implementation to the issue.
7. Compare behavior to PRD acceptance criteria.
8. Check for unrelated changes.
9. Review readability and maintainability.
10. Check security/privacy risks.
11. Check missing tests or weak verification.
12. Compare the student's suspicion from Part A with what the review found.
13. Classify findings as must-fix, should-fix, or note.
14. Recommend the next loop decision: accept, fix, rollback, split, or ask for help.

### Explanation gate

- A loop cannot be **Accepted** while the explanation check is **Not yet**.
- For **Partial** or **Not yet**, the next step is a tutoring pass: the AI asks guiding questions and lets the student trace the code; it does not simply explain the answer. Then repeat Part A on the same block.

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

## Requirement Coverage
| Requirement / Story | Evidence in Code | Status |
|---|---|---|
| FR-001 / US-001 | ... | Covered / Partial / Missing |

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

## Student Explanation Check (written before the AI review)
**Block reviewed:** `file:function` or line range
**Edge case:** ...

| Prompt | Student Answer (verbatim) | Checked By | Correct? |
|---|---|---|---|
| What it does and why | ... | Trace / run | Yes / Partly / No |
| Prediction for the edge case | ... | Trace / run | Yes / No |
| One suspected problem | ... | Review findings | Confirmed / Not found |

**Rating:** Understood / Partial / Not yet

## Loop Decision
Accept / Continue with fix / Rollback / Split issue / Ask for help
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/09-code-review.md
Explanation check: Understood / Partial / Not yet
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Review references the issue and PRD.
- [ ] Review maps code changes to relevant `US-###`, `FR-###`, or `SC-###` IDs.
- [ ] Findings are prioritized.
- [ ] Unrelated changes are checked.
- [ ] Security/privacy are considered.
- [ ] The student explained one block and predicted one edge case **before** seeing the AI review, and the answers are saved verbatim.
- [ ] The prediction was checked by tracing or running the code.
- [ ] The loop is not accepted while the explanation check is Not yet.

## Common Pitfalls

1. **Only checking if it compiles.** Working code may still violate intent.
2. **Accepting AI summaries without reading diff.** Review evidence.
3. **Over-focusing on style.** Correctness, scope, and safety come first.
4. **Explaining before asking.** If the AI explains the code first, the student's explanation only repeats it. Ask first.

## Student Prompt Template

```text
Use `review-the-code`.
Here is the issue, relevant PRD/architecture, and code diff or changed files: [paste].
Before reviewing, pick one block and one edge case, and ask me to explain the block and predict the edge case in my own words. Then review whether the implementation satisfies the issue and PRD. Flag unrelated changes, bugs, security/privacy risks, missing tests, and what I must be able to explain.

Save or update the artifact at `docs/ai-native/09-code-review.md`. End with `Saved artifact: docs/ai-native/09-code-review.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
