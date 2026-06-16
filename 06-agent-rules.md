---
name: agent-rules
description: Use this skill to create project AI rules such as AGENTS.md, .cursorrules, or classroom agent instructions so AI tools work inside the student’s intent, stack, style, and verification expectations.
version: 1.0.0
author: ATL / AI-Native App Builder Skill Pack
---

# Agent Rules

**Stage:** Phase 2 — Design the System

## Purpose

Use this skill to create project AI rules such as AGENTS.md, .cursorrules, or classroom agent instructions so AI tools work inside the student’s intent, stack, style, and verification expectations.

## Shared Principles

These skills are based on the Google AI-native software engineering transcript ATL provided.

- **Shift left on intent:** clarify goals, users, constraints, tradeoffs, and success before coding.
- **Delegate tasks, not judgment:** AI may draft, compare, or implement; the student remains responsible for decisions.
- **Verification is the bottleneck:** every output must include checks, acceptance criteria, or evidence.
- **No vibe coding:** do not jump from idea directly to generated code without intent, design, and review.
- **Small loops beat big guesses:** move one step at a time, verify, then continue.
- **AI amplifies the system:** unclear intent creates faster confusion; clear intent creates faster learning.

## When to Use

- Use after PRD and architecture are stable.
- Use before asking AI to modify project code.
- Use when students use Codex, Claude Code, Cursor, Copilot, or similar tools.
- Do not use to hide uncertainty; include open questions.

## Inputs

- Intent Brief.
- PRD.
- Architecture Plan.
- Known commands: install, run, test, build.
- Coding style or class rules.

## Process

1. Summarize project purpose and stack.
2. State source-of-truth documents.
3. Define coding conventions.
4. Define allowed and forbidden changes.
5. Define commands AI should run.
6. Define verification protocol before saying done.
7. Define security/privacy rules.
8. Define when AI must ask the student instead of guessing.

## Artifact Discipline

This skill must not only answer in chat. It must produce or update a project file so the next skill has a stable source of truth.

- **Write/update this file:** `AGENTS.md`
- **Artifact title:** Project Agent Rules
- **Read these previous artifacts first:**
- `docs/ai-native/03-prd.md`
- `docs/ai-native/04-architecture.md`
- `docs/ai-native/05-issues.md`
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
2. Read every existing required file before drafting this artifact.
3. If a required upstream file is missing, stop and ask the student to run the previous skill or provide the missing file. Do not silently recreate or guess the missing source of truth.
4. In the saved artifact, include a short `Sources Read` section listing the files actually read.
5. If the student pasted newer content than the saved file, ask whether to update the upstream artifact first before continuing.

## Output Format

```markdown
# AGENTS.md

## Project Purpose
...

## Source of Truth
- Intent Brief
- PRD
- Architecture Plan

## Stack
...

## Coding Rules
- ...

## Do Not
- Do not change unrelated files.
- Do not invent requirements.
- Do not remove tests without explanation.

## Commands
- Install: ...
- Run: ...
- Test: ...
- Build: ...

## Verification Before Done
- ...

## Security and Privacy
- ...

## Ask First When
- ...
```

## Final Response Contract

When this skill finishes, respond briefly and include:

```text
Saved artifact: AGENTS.md
Next recommended skill: <next-skill-or-human-review>
```

If you cannot write the file, say exactly why and do not pretend the artifact was saved.

## Quality Checklist

- [ ] Rules are specific to the project.
- [ ] AI has commands and verification steps.
- [ ] Forbidden behaviors are clear.
- [ ] Rules preserve student judgment.
- [ ] Open questions are not buried.

## Common Pitfalls

1. **Generic rules.** “Write clean code” is weak; project-specific rules are stronger.
2. **No commands.** AI needs exact run/test/build commands when possible.
3. **No ask-first boundary.** AI should not silently choose major product changes.

## Student Prompt Template

```text
Use `agent-rules`.
Here are my Intent Brief, PRD, Architecture Plan, and known project commands: [paste].
Create an AGENTS.md-style rule file for AI coding tools. Include source of truth, stack, coding rules, forbidden changes, commands, verification before done, security/privacy, and ask-first cases.

Save or update the artifact at `AGENTS.md`. End with `Saved artifact: AGENTS.md` and the next recommended skill.

Before drafting, read the required upstream artifact files listed in the skill. If any are missing, stop and report which file is missing.
```
