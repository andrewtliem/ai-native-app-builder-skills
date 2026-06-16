---
name: issue-to-prompt
description: Use this skill to turn one implementation issue into a focused AI coding prompt that includes context, constraints, expected behavior, verification, and boundaries.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Issue to Prompt

**Stage:** Phase 3 — Build with AI

## Purpose

Use this skill to turn one implementation issue into a focused AI coding prompt that includes context, constraints, expected behavior, verification, and boundaries.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use when a student is ready to work on one issue with an AI coding tool.
- Use after `architecture-to-issues` and `agent-rules`.
- Use before `run-the-loop`, so the build loop starts with a focused prompt.
- Do not combine many unrelated issues into one prompt.

## Inputs

- One issue from the issue list.
- Relevant PRD section.
- Relevant architecture notes.
- Project rules or AGENTS.md.

## Process

1. Restate the issue goal.
2. Include only relevant context from PRD and architecture.
3. Tell AI what files to inspect first.
4. State constraints and forbidden changes.
5. Define exact expected output.
6. Include tests/checks to run.
7. Ask AI to explain assumptions and summarize changes.
8. Require no unrelated changes.
9. State that the output should feed into `run-the-loop` for review, test, fix, and acceptance decisions.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/07-issue-prompt.md`
- **Artifact title:** Issue Coding Prompt
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
- `AGENTS.md`
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
   - `AGENTS.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# AI Coding Prompt

You are working on Issue X: ...

## Goal
...

## Relevant Context
...

## Files to Inspect First
- ...

## Constraints
- ...

## Do Not
- ...

## Expected Output
- ...

## Verification
Run/check: ...

## Loop Handoff
After the build attempt, use `run-the-loop` with the changed files, review findings, and test evidence.

## Before You Finish
- Summarize changed files.
- Explain assumptions.
- Report verification results.
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/07-issue-prompt.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Prompt covers one issue only.
- [ ] Context is enough but not bloated.
- [ ] Boundaries are explicit.
- [ ] Verification is required.
- [ ] Student can judge the final output.

## Common Pitfalls

1. **Dumping the whole project into the prompt.** Use relevant context.
2. **Asking AI to “make it better.”** State exact goal.
3. **No verification.** AI must provide evidence, not just confidence.

## Student Prompt Template

```text
Use `issue-to-prompt`.
Here is one implementation issue plus relevant PRD/architecture/rules: [paste].
Create a focused AI coding prompt for this issue only, with goal, context, files to inspect, constraints, do-not list, expected output, verification, and finish requirements.

Save or update the artifact at `docs/ai-native/07-issue-prompt.md`. End with `Saved artifact: docs/ai-native/07-issue-prompt.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
