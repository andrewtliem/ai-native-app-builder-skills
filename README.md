# AI-Native App Builder Skill Pack

A small skill pack for students building apps with AI. It is based on two YouTube talks about AI-native software engineering, interpreted through ATL’s own teaching perspective.

The pack is intentionally **not one giant skill**. Each markdown file is a focused skill that covers one stage from *hulu ke hilir*: raw idea → intent → PRD → architecture → issues → AI prompts → loop engineering → review → testing → red team → demo → postmortem.


## Installation

This repository is structured so agents that support the [skills.sh](https://skills.sh/) installer can install the pack directly from GitHub.

### Install all skills globally

Use this if you want the skills available across supported agents on your machine:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --all -g
```

### Install for Codex only

Use this if you only want the skill pack available to Codex CLI:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --agent codex --skill '*' -g -y
```

### Install for a project only

Run this inside a project folder if you want the skill pack scoped to that project instead of globally:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --all
```

### Preview available skills

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --list
```

Expected skills:

```text
grill-my-idea
idea-to-intent
intent-to-prd
prd-to-architecture
architecture-to-issues
agent-rules
issue-to-prompt
run-the-loop
review-the-code
test-the-app
red-team-my-app
demo-ready
postmortem
```

### Manual use

If your agent does not support `skills.sh`, you can still clone the repository and paste or reference the relevant `SKILL.md` file in your coding agent session:

```bash
git clone https://github.com/andrewtliem/ai-native-app-builder-skills.git
```

Each installable skill lives in a folder like:

```text
08-run-the-loop/SKILL.md
09-review-the-code/SKILL.md
10-test-the-app/SKILL.md
```


## Repository Layout

The installable skill folders are the canonical source. Each skill lives in its own directory with a `SKILL.md` file:

```text
01-grill-my-idea/SKILL.md
02-idea-to-intent/SKILL.md
...
13-postmortem/SKILL.md
```

There are no duplicate top-level numbered `.md` files; keep edits inside the matching `SKILL.md`.

## Core Mantra

> **Delegate tasks, not judgment.**

AI can help draft, compare, implement, and review. The student remains responsible for intent, decisions, verification, and explanation.

## Loop Engineering Principle

The build phase uses a small loop:

```text
issue → prompt → build → review → test → fix → decide → repeat or accept
```

This is not an infinite autopilot. It is a controlled learning loop. The student designs the loop, records evidence, and decides whether to accept, fix, rollback, split the issue, or ask for help.

## Artifact System

Each skill must save its output to a file. This prevents the workflow from becoming a series of disconnected chat answers. The next skill reads the previous artifact as its source of truth.

Default project artifact folder:

```text
docs/ai-native/
```

Artifact chain:

1. [`01-grill-my-idea.md`](./01-grill-my-idea/SKILL.md) → `docs/ai-native/01-grill-my-idea.md`
2. [`02-idea-to-intent.md`](./02-idea-to-intent/SKILL.md) → `docs/ai-native/02-intent-brief.md`
3. [`03-intent-to-prd.md`](./03-intent-to-prd/SKILL.md) → `docs/ai-native/03-prd.md`
4. [`04-prd-to-architecture.md`](./04-prd-to-architecture/SKILL.md) → `docs/ai-native/04-architecture.md`
5. [`05-architecture-to-issues.md`](./05-architecture-to-issues/SKILL.md) → `docs/ai-native/05-issues.md`
6. [`06-agent-rules.md`](./06-agent-rules/SKILL.md) → `AGENTS.md`
7. [`07-issue-to-prompt.md`](./07-issue-to-prompt/SKILL.md) → `docs/ai-native/07-issue-prompt.md`
8. [`08-run-the-loop.md`](./08-run-the-loop/SKILL.md) → `docs/ai-native/08-loop-log.md`
9. [`09-review-the-code.md`](./09-review-the-code/SKILL.md) → `docs/ai-native/09-code-review.md`
10. [`10-test-the-app.md`](./10-test-the-app/SKILL.md) → `docs/ai-native/10-test-plan.md`
11. [`11-red-team-my-app.md`](./11-red-team-my-app/SKILL.md) → `docs/ai-native/11-risk-review.md`
12. [`12-demo-ready.md`](./12-demo-ready/SKILL.md) → `docs/ai-native/12-demo-script.md`
13. [`13-postmortem.md`](./13-postmortem/SKILL.md) → `docs/ai-native/13-postmortem.md`

Rule for agents/students:

> If it is not saved to a project file, it is not part of the project memory.

Each skill should finish with:

```text
Saved artifact: <path>
Next recommended skill: <skill-name>
```

## Source Loading Rule

Every downstream skill must load files from disk before it drafts the next artifact.

Required behavior:

1. Check that the upstream artifact files exist.
2. Read the upstream files from the current project, not only from chat history.
3. If a required file is missing, stop and ask the student to run the previous skill or provide the missing artifact.
4. Save the new artifact only after the source files have been read.
5. Add a `Sources Read` section to each saved artifact so reviewers know what the next step was based on.

This prevents hidden context loss between tools, chat sessions, or coding agents.

## Pipeline

1. [`01-grill-my-idea.md`](./01-grill-my-idea/SKILL.md) — challenge the raw idea.
2. [`02-idea-to-intent.md`](./02-idea-to-intent/SKILL.md) — capture the project intent.
3. [`03-intent-to-prd.md`](./03-intent-to-prd/SKILL.md) — create a student-friendly PRD.
4. [`04-prd-to-architecture.md`](./04-prd-to-architecture/SKILL.md) — design the simplest viable system.
5. [`05-architecture-to-issues.md`](./05-architecture-to-issues/SKILL.md) — create ordered implementation issues.
6. [`06-agent-rules.md`](./06-agent-rules/SKILL.md) — create AGENTS.md / project AI rules.
7. [`07-issue-to-prompt.md`](./07-issue-to-prompt/SKILL.md) — turn one issue into a focused coding prompt.
8. [`08-run-the-loop.md`](./08-run-the-loop/SKILL.md) — operate one safe AI-assisted build/review/test/fix loop.
9. [`09-review-the-code.md`](./09-review-the-code/SKILL.md) — review code against issue, PRD, safety, and explainability.
10. [`10-test-the-app.md`](./10-test-the-app/SKILL.md) — create manual/automated test plans and evidence.
11. [`11-red-team-my-app.md`](./11-red-team-my-app/SKILL.md) — find security, privacy, misuse, AI, reliability, and UX risks.
12. [`12-demo-ready.md`](./12-demo-ready/SKILL.md) — prepare a short honest demo script.
13. [`13-postmortem.md`](./13-postmortem/SKILL.md) — reflect and improve the next project loop.

## Phase View

### Phase 1 — Think Before Build

- `grill-my-idea`
- `idea-to-intent`
- `intent-to-prd`

### Phase 2 — Design the System

- `prd-to-architecture`
- `architecture-to-issues`
- `agent-rules`

### Phase 3 — Build with AI

- `issue-to-prompt`
- `run-the-loop`
- `review-the-code`
- `test-the-app`

### Phase 4 — Prove and Learn

- `red-team-my-app`
- `demo-ready`
- `postmortem`

## How to Use in Class

Students should not run all skills in one prompt. They should move stage by stage:

1. Run one skill.
2. Read the output.
3. Make a human decision.
4. Revise if needed.
5. Move to the next skill.

During implementation, students should use the loop rhythm for each issue:

1. Pick one issue.
2. Generate a focused prompt.
3. Run one build attempt.
4. Review the diff.
5. Test the behavior.
6. Fix or accept based on evidence.
7. Record what they learned.

This skill pack is based on two YouTube talks that shaped ATL’s thinking about AI-native software engineering:

- https://www.youtube.com/watch?v=q_Jq4IgYImk
- https://www.youtube.com/watch?v=VTYx7Ex-0bA

The interpretation here is ATL’s own reading of those ideas. Other educators may draw different lessons from the same videos. For ATL, the main lesson is this: AI-native engineering is not about generating more code faster. It is about clearer intent, better systems, stronger verification, and human judgment.
