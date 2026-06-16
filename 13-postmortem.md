---
name: postmortem
description: Use this skill after a student app project or milestone to reflect on what worked, what failed, how AI helped or misled, what was verified, and what rules should improve next time.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Postmortem

**Stage:** Phase 4 — Prove and Learn

## Purpose

Use this skill after a student app project or milestone to reflect on what worked, what failed, how AI helped or misled, what was verified, and what rules should improve next time.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after demo/submission or after a difficult milestone.
- Use when the student needs learning evidence, not just a finished app.
- Use before starting the next project so rules and habits improve.

## Inputs

- Intent Brief or PRD.
- Final app state.
- Test/review/red-team results.
- Notes about AI usage.
- Problems encountered.

## Process

1. Compare original intent to final result.
2. Identify what changed and why.
3. Record where AI accelerated work.
4. Record where AI caused confusion, bugs, or overconfidence.
5. Identify what the student verified and what remains unverified.
6. Extract rules to add to future prompts or AGENTS.md.
7. Write one practical improvement for the next project.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/13-postmortem.md`
- **Artifact title:** Postmortem Reflection
- **Read these previous artifacts first:**
- `docs/ai-native/02-intent-brief.md`
- `docs/ai-native/03-prd.md`
- `docs/ai-native/08-loop-log.md`
- `docs/ai-native/10-test-plan.md`
- `docs/ai-native/12-demo-script.md`
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Do not draft from memory: follow the Source Loading Protocol below before writing this file.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the user or student confirms this artifact is acceptable.

## Source Loading Protocol

Before producing this skill's output, the agent must explicitly load the upstream artifact files from the current project. Do not rely on pasted chat history if the files exist.

1. Check whether each required upstream file exists:
   - `docs/ai-native/02-intent-brief.md`
   - `docs/ai-native/03-prd.md`
   - `docs/ai-native/08-loop-log.md`
   - `docs/ai-native/10-test-plan.md`
   - `docs/ai-native/12-demo-script.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Project Postmortem

## Original Intent
...

## Final Result
...

## What Changed
- ...

## Where AI Helped
- ...

## Where AI Misled or Failed
- ...

## What I Verified
- ...

## What I Did Not Verify
- ...

## Rules to Add Next Time
- ...

## Biggest Lesson
...

## Next Improvement
...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/13-postmortem.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Reflection compares intent to result.
- [ ] AI help and AI failure are both discussed.
- [ ] Verification is explicit.
- [ ] Future rules are concrete.
- [ ] Student identifies one real learning point.

## Common Pitfalls

1. **Writing only a success story.** Postmortem should include confusion and mistakes.
2. **Blaming AI only.** Student must own judgment and verification.
3. **No reusable lesson.** End with rules for next time.

## Student Prompt Template

```text
Use `postmortem`.
Here is my original intent/PRD, final app state, test/review results, AI usage notes, and problems encountered: [paste].
Write a postmortem comparing intent to result, where AI helped/misled, what I verified/did not verify, rules to add next time, biggest lesson, and next improvement.

Save or update the artifact at `docs/ai-native/13-postmortem.md`. End with `Saved artifact: docs/ai-native/13-postmortem.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
