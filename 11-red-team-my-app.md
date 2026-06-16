---
name: red-team-my-app
description: Use this skill to find misuse, privacy, security, reliability, accessibility, and UX risks in a student app before demo or submission.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Red Team My App

**Stage:** Phase 4 — Prove and Learn

## Purpose

Use this skill to find misuse, privacy, security, reliability, accessibility, and UX risks in a student app before demo or submission.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after main flows work.
- Use before public demo, deployment, or grading.
- Use especially for apps with login, personal data, AI features, uploads, messaging, payments, or classroom records.
- Do not use to attack real users or systems.

## Inputs

- PRD.
- Architecture Plan.
- Feature list.
- Data collected by the app.
- Deployment context.

## Process

1. Identify sensitive data and trust boundaries.
2. List likely misuse or abuse cases.
3. Check authentication/authorization risks.
4. Check input validation and file upload risks.
5. Check privacy and data retention risks.
6. Check AI-specific risks if the app uses LLMs: prompt injection, hallucination, unsafe output.
7. Check reliability and accessibility.
8. Propose mitigations with priority.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `docs/ai-native/11-risk-review.md`
- **Artifact title:** Risk and Red-Team Review
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/08-loop-log.md`
- `docs/ai-native/10-test-plan.md`
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
   - `docs/ai-native/08-loop-log.md`
   - `docs/ai-native/10-test-plan.md`
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# Red Team Report

## Risk Summary
Low / Medium / High

## Sensitive Data
- ...

## Misuse Cases
- ...

## Security Risks
- ...

## Privacy Risks
- ...

## AI-Specific Risks
- ...

## Reliability / Accessibility Risks
- ...

## Mitigation Plan
### Must Fix
- ...
### Should Fix
- ...
### Acceptable for Class Demo
- ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: docs/ai-native/11-risk-review.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Sensitive data is identified.
- [ ] Misuse cases are realistic.
- [ ] Risks are prioritized.
- [ ] Mitigations are practical for students.
- [ ] The report distinguishes class demo risk from production risk.

## Common Pitfalls

1. **Being dramatic without prioritizing.** Students need actionable risk levels.
2. **Ignoring privacy.** Classroom apps often involve names, grades, attendance, or messages.
3. **Treating class demo as production.** Be honest about what is acceptable for learning vs real deployment.

## Student Prompt Template

```text
Use `red-team-my-app`.
Here is my PRD, architecture, feature list, and data collected: [paste].
Find realistic security, privacy, misuse, AI-specific, reliability, accessibility, and UX risks. Prioritize mitigations as must-fix, should-fix, or acceptable for class demo.

Save or update the artifact at `docs/ai-native/11-risk-review.md`. End with `Saved artifact: docs/ai-native/11-risk-review.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
