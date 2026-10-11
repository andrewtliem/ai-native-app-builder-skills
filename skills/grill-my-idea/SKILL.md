---
name: grill-my-idea
description: Use this skill to challenge a raw app idea before the student writes a PRD or asks AI to code. It interviews the student one question at a time, records the student's own answers verbatim, and turns vague enthusiasm into clearer problem framing, assumptions, risks, and next questions.
version: 1.1.0
author: ATL / AI-Native App Builder Skill Pack
---

# Grill My Idea

**Stage:** Phase 1 — Think Before Build

## Purpose

Use this skill to challenge a raw app idea before the student writes a PRD or asks AI to code. The grill is an **interview**, not a questionnaire: the AI asks, the student answers, and the student's answers become the source of truth for every later artifact.

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

- Use when a student says “I want to build an app for ...” but the user, problem, scope, or evidence is still unclear.
- Use before `idea-to-intent`.
- Do not use to design the full solution yet; this skill is for pressure-testing the idea.

## Inputs

- Raw app idea in 1–5 sentences.
- Any known target users.
- Any constraints from class, time, platform, or tools.

## Modes

**Classroom mode (default).** The AI only asks, challenges, and points out contradictions. It does not suggest answers, example answers, or a recommended option. Use this mode unless the instructor or user explicitly asks for practitioner mode.

**Practitioner mode (opt-in).** The AI may offer a recommended answer **after** the user has answered in their own words. Recommendations accepted by the user are tagged `[confirmed]`, never `[student]`.

## Process

1. Restate the idea in one or two plain sentences and ask the student whether the restatement is right.
2. Ask **one question at a time** and wait for the student's answer before asking the next. Never send a batch of questions.
3. Cover these areas in order, adapting to the answers: user, problem, current workaround, evidence that the problem is real, scope, risks, and what would prove the app works.
4. After each answer, decide whether to go deeper on the same branch or move on. Push back when an answer is vague (“everyone”, “easier”, “better”) and ask for something specific or measurable.
5. If an answer contradicts an earlier answer, quote both and ask the student which one holds.
6. If a fact can be checked from the project files or the student's notes, read it instead of asking.
7. Stop after the student has answered at least 8 questions **and** can name the user, the problem, and one way to prove success. If time runs out first, stop and record what is still unanswered.
8. Write the artifact. Everything about the idea must come from the student's answers. Anything the AI adds (an assumption, a risk, a smaller version) is tagged `[ai-proposed]` and listed for the student to confirm or reject.
9. Ask the student to confirm, reject, or replace each `[ai-proposed]` item. Update tags: confirmed items become `[confirmed]`; rejected items are removed or rewritten in the student's words as `[student]`.
10. End with a decision gate that the **student** chooses: proceed, revise, or research first.

## Decision Provenance

Use these tags on every line that states a user, problem, scope, constraint, assumption, risk, or decision:

| Tag | Meaning |
|---|---|
| `[student]` | The student said this in their own words. |
| `[ai-proposed]` | The AI suggested this and the student has not yet accepted it. |
| `[confirmed]` | The AI suggested this and the student explicitly accepted it. |

Rules:

- Do not rewrite a student answer into something more polished and still call it `[student]`. Keep the student's wording; add a clarifying note if needed.
- Do not save the artifact as final while any `[ai-proposed]` item remains. Ask about each one first.
- The Q&A transcript is part of the artifact. It is the evidence that the student did the thinking.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/01-grill-my-idea.md`
- **Artifact title:** Idea Grill Report
- **Read these previous artifacts first:**
- None. This is the first artifact in the pipeline.
- If the project does not have `docs/ai-native/`, create it.
- If the target file already exists, update it carefully instead of creating a duplicate.
- Save the Q&A transcript with the student's answers **verbatim**. Answers that live only in chat are not part of the project.
- End the response with a short `Saved artifact:` line naming the file path.
- Do not continue to the next skill until the student confirms this artifact is acceptable.

## Source Loading Protocol

This is the first skill in the pipeline, so there is no required upstream artifact. Still, create the artifact folder and save this skill's result so the next skill can load it.

1. Create `docs/ai-native/` if it does not exist.
2. Save the result to `docs/ai-native/01-grill-my-idea.md`.
3. In the saved artifact, include a short `Sources Read` section. For this first step, write `None — first pipeline artifact` unless the student provided external notes.

## Output Format

```markdown
# Idea Grill Report

## Sources Read
- None — first pipeline artifact

## Mode
Classroom / Practitioner

## Original Idea (student's words)
> ...

## Grill Transcript
| # | Question | Student Answer (verbatim) | Follow-up / Contradiction Noted |
|---|---|---|---|
| Q1 | ... | ... | ... |

## Main User
- ... `[student]`

## Problem Being Solved
- ... `[student]`

## Evidence the Problem Is Real
- ... `[student]`

## Assumptions
- ... `[student]` / `[confirmed]`

## Risks
- ... `[student]` / `[confirmed]`

## Smallest Useful Version
- ... `[student]` / `[confirmed]`

## Non-Goals
- ... `[student]` / `[confirmed]`

## Still Unanswered
- ...

## Decision Gate (chosen by the student)
Proceed / Revise / Research first, because ... `[student]`
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/01-grill-my-idea.md
Open ai-proposed items: <number, should be 0>
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Questions were asked one at a time and each answer was recorded verbatim.
- [ ] At least 8 questions were answered by the student.
- [ ] User is specific, not “everyone”.
- [ ] Problem is described as a real pain, not just a feature.
- [ ] Every decision line carries a provenance tag.
- [ ] No `[ai-proposed]` items remain.
- [ ] MVP is smaller than the original idea.
- [ ] The decision gate was chosen by the student.

## Common Pitfalls

1. **Batching questions.** A list of 10 questions is a form, not a grill. Ask one, wait, follow up.
2. **Answering for the student.** In classroom mode the AI never fills in the user, problem, or scope from a one-line idea.
3. **Polishing answers.** Rewriting “my friends always forget deadlines” into “students experience task fragmentation” hides whose thinking it was.
4. **Being too nice.** This skill should challenge the idea, not only encourage it.
5. **Jumping to features.** Stay with users, pain, evidence, and scope first.

## Student Prompt Template

```text
You are using the `grill-my-idea` skill in classroom mode.
My app idea is: [paste idea].
Interview me one question at a time and wait for my answer each time. Do not suggest answers. Push back when my answers are vague or contradict each other.
When we are done, save my answers verbatim and tag every decision with who made it.

Save or update the artifact at `docs/ai-native/01-grill-my-idea.md`. End with `Saved artifact: docs/ai-native/01-grill-my-idea.md`, the number of open ai-proposed items, and the next recommended skill.
```
