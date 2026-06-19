# AI-Native App Builder Skill Pack

A student-friendly skill pack for building software with AI while preserving **human judgment, traceability, verification, and reflection**.

The pack is organized into four kinds of content:

```text
skills/      actual installable skills
bundles/     classroom learning paths that group skills
templates/   reusable artifact worksheets
examples/    sample student-project artifact chains
```

This cleaner layout avoids confusing root-level numbered folders while keeping all skills installable through `skills.sh`.

## Article

This repository accompanies ATL’s article about the AI-Native App Builder Skill Pack:

- [From Vibe Coder to Software Developer: An AI-Native Skill Pack for University Students](https://blog.atlverse.xyz/en/blog/ai-native-app-builder-skills-for-students/)

## Core Mantra

> **Delegate tasks, not judgment.**

AI can help draft, compare, implement, and review. The student remains responsible for intent, decisions, verification, and explanation.

## Bundle Overview

| Bundle | Use When | Main Output |
|---|---|---|
| [`01-starter`](./bundles/01-starter/README.md) | Students have a raw idea | Intent Brief + PRD |
| [`02-spec-driven`](./bundles/02-spec-driven/README.md) | Before coding | Constitution + clarification + architecture + issues + artifact analysis |
| [`03-build-loop`](./bundles/03-build-loop/README.md) | During implementation | Agent rules + issue prompt + loop log + code review |
| [`04-quality-proof`](./bundles/04-quality-proof/README.md) | Before submission | Test plan + traceability + risk review + convergence report |
| [`05-demo-reflection`](./bundles/05-demo-reflection/README.md) | Before presentation | Demo script + postmortem |
| [`06-advanced`](./bundles/06-advanced/README.md) | Larger projects | Feature folders, checklists, GitHub issue workflows |

## Recommended Classroom Flow

### Week 1 — Starter

Use Bundle 1:

1. `grill-my-idea`
2. `idea-to-intent`
3. `intent-to-prd`

### Week 2 — Spec-Driven Foundation

Use Bundle 2:

1. `project-constitution`
2. `clarify-prd`
3. `prd-to-architecture`
4. `architecture-to-issues`
5. `analyze-artifacts`

### Week 3+ — Build Loop

Use Bundle 3 repeatedly, one issue at a time:

1. `agent-rules`
2. `issue-to-prompt`
3. `run-the-loop`
4. `review-the-code`

### Before Submission — Quality Proof

Use Bundle 4:

1. `test-the-app`
2. `traceability-matrix`
3. `red-team-my-app`
4. `converge-the-app`

### Before Presentation — Demo & Reflection

Use Bundle 5:

1. `demo-ready`
2. `postmortem`

## Installation

This repository is structured so agents that support the [skills.sh](https://skills.sh/) installer can install the pack directly from GitHub.

### Install all skills globally

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --all -g
```

### Install for Codex only

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
project-constitution
clarify-prd
analyze-artifacts
traceability-matrix
converge-the-app
```

## Repository Layout

```text
skills/
├── grill-my-idea/SKILL.md
├── idea-to-intent/SKILL.md
├── intent-to-prd/SKILL.md
├── prd-to-architecture/SKILL.md
├── architecture-to-issues/SKILL.md
├── agent-rules/SKILL.md
├── issue-to-prompt/SKILL.md
├── run-the-loop/SKILL.md
├── review-the-code/SKILL.md
├── test-the-app/SKILL.md
├── red-team-my-app/SKILL.md
├── demo-ready/SKILL.md
├── postmortem/SKILL.md
├── project-constitution/SKILL.md
├── clarify-prd/SKILL.md
├── analyze-artifacts/SKILL.md
├── traceability-matrix/SKILL.md
└── converge-the-app/SKILL.md

bundles/
templates/
examples/
```

## Skill Index

| # | Skill | Artifact |
|---:|---|---|
| 01 | [`grill-my-idea`](./skills/grill-my-idea/SKILL.md) | `docs/ai-native/01-grill-my-idea.md` |
| 02 | [`idea-to-intent`](./skills/idea-to-intent/SKILL.md) | `docs/ai-native/02-intent-brief.md` |
| 03 | [`intent-to-prd`](./skills/intent-to-prd/SKILL.md) | `docs/ai-native/03-prd.md` |
| 04 | [`project-constitution`](./skills/project-constitution/SKILL.md) | `docs/ai-native/14-project-constitution.md` |
| 05 | [`clarify-prd`](./skills/clarify-prd/SKILL.md) | `docs/ai-native/15-clarification-log.md` |
| 06 | [`prd-to-architecture`](./skills/prd-to-architecture/SKILL.md) | `docs/ai-native/04-architecture.md` |
| 07 | [`architecture-to-issues`](./skills/architecture-to-issues/SKILL.md) | `docs/ai-native/05-issues.md` |
| 08 | [`analyze-artifacts`](./skills/analyze-artifacts/SKILL.md) | `docs/ai-native/16-artifact-analysis.md` |
| 09 | [`agent-rules`](./skills/agent-rules/SKILL.md) | `AGENTS.md` |
| 10 | [`issue-to-prompt`](./skills/issue-to-prompt/SKILL.md) | `docs/ai-native/07-issue-prompt.md` |
| 11 | [`run-the-loop`](./skills/run-the-loop/SKILL.md) | `docs/ai-native/08-loop-log.md` |
| 12 | [`review-the-code`](./skills/review-the-code/SKILL.md) | `docs/ai-native/09-code-review.md` |
| 13 | [`test-the-app`](./skills/test-the-app/SKILL.md) | `docs/ai-native/10-test-plan.md` |
| 14 | [`traceability-matrix`](./skills/traceability-matrix/SKILL.md) | `docs/ai-native/17-traceability-matrix.md` |
| 15 | [`red-team-my-app`](./skills/red-team-my-app/SKILL.md) | `docs/ai-native/11-risk-review.md` |
| 16 | [`converge-the-app`](./skills/converge-the-app/SKILL.md) | `docs/ai-native/18-convergence-report.md` |
| 17 | [`demo-ready`](./skills/demo-ready/SKILL.md) | `docs/ai-native/12-demo-script.md` |
| 18 | [`postmortem`](./skills/postmortem/SKILL.md) | `docs/ai-native/13-postmortem.md` |

## Artifact System

Each skill must save its output to a file. This prevents the workflow from becoming a series of disconnected chat answers. The next skill reads the previous artifact as its source of truth.

Default project artifact folder:

```text
docs/ai-native/
```

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

1. Check that upstream artifact files exist.
2. Read upstream files from the current project, not only from chat history.
3. If a required file is missing, stop and ask the student to run the previous skill or provide the missing artifact.
4. Save the new artifact only after the source files have been read.
5. Add a `Sources Read` section to each saved artifact.

## Spec-Driven Additions Borrowed From GitHub Spec Kit

This repo adapts several ideas from GitHub Spec Kit for university students:

- **Constitution:** non-negotiable project principles before coding.
- **Clarification:** ask targeted questions before architecture.
- **Requirement IDs:** use `FR-001`, `SC-001`, `US-001` for traceability.
- **Artifact analysis:** check consistency across PRD, architecture, and issues before implementation.
- **Traceability matrix:** prove every requirement has issue/test/evidence coverage.
- **Convergence:** compare the current app against intended artifacts before claiming done.

## Loop Engineering Principle

The build phase uses a small loop:

```text
issue → prompt → build → review → test → fix → decide → repeat or accept
```

This is not an infinite autopilot. It is a controlled learning loop. The student designs the loop, records evidence, and decides whether to accept, fix, rollback, split the issue, or ask for help.

## Templates

Reusable templates live in [`templates/`](./templates/):

- `prd-template.md`
- `constitution-template.md`
- `architecture-template.md`
- `issue-template.md`
- `artifact-analysis-template.md`
- `traceability-matrix-template.md`
- `convergence-report-template.md`
- `checklist-template.md`

## Manual Use

If your agent does not support `skills.sh`, clone the repository and paste or reference the relevant `SKILL.md` file in your coding agent session:

```bash
git clone https://github.com/andrewtliem/ai-native-app-builder-skills.git
```

## Teaching Philosophy

This skill pack is based on two YouTube talks that shaped ATL’s thinking about AI-native software engineering:

- https://www.youtube.com/watch?v=q_Jq4IgYImk
- https://www.youtube.com/watch?v=VTYx7Ex-0bA

The interpretation here is ATL’s own reading of those ideas. Other educators may draw different lessons from the same videos. For ATL, the main lesson is this: AI-native engineering is not about generating more code faster. It is about clearer intent, better systems, stronger verification, and human judgment.
