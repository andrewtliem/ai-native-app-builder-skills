# AI-Native App Builder Skill Pack

A student-friendly skill pack for building software with AI while preserving **human judgment, traceability, verification, and reflection**.

This is not a prompt collection for “make me an app.” It is a guided workflow that helps students move from a vague idea into a tested, explainable, demo-ready software project.

> **Core mantra:** Delegate tasks, not judgment.

AI can help draft, compare, implement, and review. The student remains responsible for intent, decisions, verification, and explanation.

---

## Who This Is For

This repo is for:

- **Students** building apps with AI assistants.
- **Lecturers / instructors** teaching AI-native software engineering.
- **Bootcamp mentors** who want students to produce evidence, not only code.
- **Self-learners** who want to move from vibe coding to disciplined app building.

If you have ever asked AI to “build this app” and then felt lost reviewing the output, this skill pack is for you.

---

## What You Will Learn

By using the skills, students practice how to:

1. Turn a raw idea into a clear project intent.
2. Write a PRD that is specific enough to guide AI coding.
3. Clarify vague requirements before coding.
4. Design a simple architecture that matches the PRD.
5. Break work into small implementation issues.
6. Prompt AI one issue at a time.
7. Review, test, and fix AI-generated code.
8. Prove requirement coverage with traceability and evidence.
9. Prepare an honest demo and postmortem.

The goal is not “AI builds everything.” The goal is:

```text
clear intent → structured artifacts → small AI-assisted loops → verified software → student explanation
```

---

## Choose Your Path

You do **not** need to use all 18 skills for every project.

Think of this repo as a toolkit with three paths:

| Path | Best For | Skills Used | Outcome |
|---|---|---:|---|
| **Mini Path** | 1-week assignment, prototype, beginner practice | 6 | Simple app with basic intent, prompt, test, and demo |
| **Class Project Path** | Normal course project | 12 | PRD, architecture, implementation loop, review, tests, demo, reflection |
| **Capstone Path** | Final project, research, serious portfolio work | 18 | Full spec-driven workflow with traceability, risk review, and convergence |

### Path 1 — Mini Path

Use this for small assignments or first-time students.

```text
idea-to-intent
intent-to-prd
issue-to-prompt
run-the-loop
test-the-app
demo-ready
```

**Use when:** the project is small, the student is new, or the goal is to practice AI-assisted building without overwhelming process.

**Minimum artifacts:**

```text
docs/ai-native/02-intent-brief.md
docs/ai-native/03-prd.md
docs/ai-native/07-issue-prompt.md
docs/ai-native/08-loop-log.md
docs/ai-native/10-test-plan.md
docs/ai-native/12-demo-script.md
```

### Path 2 — Class Project Path

Use this for a normal multi-week class project.

```text
grill-my-idea
idea-to-intent
intent-to-prd
clarify-prd
prd-to-architecture
architecture-to-issues
issue-to-prompt
run-the-loop
review-the-code
test-the-app
demo-ready
postmortem
```

**Use when:** students need enough structure to prevent vibe coding, but do not need the full capstone-level audit trail.

### Path 3 — Capstone Path

Use this for final projects, research prototypes, or serious portfolio apps.

```text
all 18 skills
```

This adds:

```text
project-constitution
analyze-artifacts
traceability-matrix
red-team-my-app
converge-the-app
```

**Use when:** the project needs stronger evidence, grading traceability, security/privacy review, or a clear “ready / not ready” decision.

> Recommendation: start with the Mini Path. Add more skills only when the project becomes serious enough to need them.

---

## Repository Structure

```text
skills/      actual installable skills
bundles/     classroom learning paths that group skills
templates/   reusable artifact worksheets
examples/    sample student-project artifact chains
```

### Important distinction

| Folder | Meaning |
|---|---|
| `skills/` | The actual skills installed into supported AI agents. |
| `bundles/` | Tutorial paths that tell students which skills to use together. |
| `templates/` | Blank worksheets for PRD, architecture, issues, traceability, etc. |
| `examples/` | Future sample projects showing completed artifact chains. |

---

## Quick Start for Students

### Step 1 — Install the skills

If your AI tool supports [`skills.sh`](https://skills.sh/), install the pack globally:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --all -g
```

For Codex only:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --agent codex --skill '*' -g -y
```

For one project only, run inside your project folder:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --all
```

Preview the available skills:

```bash
npx -y skills add andrewtliem/ai-native-app-builder-skills --list
```

You should see skills such as:

```text
grill-my-idea
idea-to-intent
intent-to-prd
project-constitution
clarify-prd
prd-to-architecture
architecture-to-issues
analyze-artifacts
issue-to-prompt
run-the-loop
review-the-code
test-the-app
traceability-matrix
red-team-my-app
converge-the-app
demo-ready
postmortem
```

---

### Step 2 — Create or open your app project

Use an existing project folder or create a new one:

```bash
mkdir my-ai-native-app
cd my-ai-native-app
```

Every skill will save its output under:

```text
docs/ai-native/
```

Example:

```text
docs/ai-native/02-intent-brief.md
docs/ai-native/03-prd.md
docs/ai-native/04-architecture.md
```

Rule:

> If it is not saved to a project file, it is not part of the project memory.

---

### Step 3 — Start with Bundle 1

Ask your AI assistant:

```text
Use the grill-my-idea skill.

My app idea is:
[write your idea here]

Challenge the idea and save the artifact to docs/ai-native/01-grill-my-idea.md.
```

Then continue:

```text
Use the idea-to-intent skill.
Read docs/ai-native/01-grill-my-idea.md first.
Create the Intent Brief and save it to docs/ai-native/02-intent-brief.md.
```

Then:

```text
Use the intent-to-prd skill.
Read docs/ai-native/02-intent-brief.md first.
Create the PRD and save it to docs/ai-native/03-prd.md.
```

Do not run all skills in one prompt. Move step by step.

---

## The Bundle Tutorial

The easiest way to use this repository is by following bundles **after you choose a path**.

- If you are new, start with the **Mini Path** above.
- If you are doing a normal class project, use the **Class Project Path** and selected bundles.
- If this is a capstone or final project, use the full bundle sequence.

| Bundle | Use When | Main Output |
|---|---|---|
| [`01-starter`](./bundles/01-starter/README.md) | You have a raw idea | Idea review, Intent Brief, PRD |
| [`02-spec-driven`](./bundles/02-spec-driven/README.md) | Before coding | Constitution, clarification, architecture, issues, artifact analysis |
| [`03-build-loop`](./bundles/03-build-loop/README.md) | During implementation | Agent rules, issue prompt, loop log, code review |
| [`04-quality-proof`](./bundles/04-quality-proof/README.md) | Before submission | Test plan, traceability, risk review, convergence report |
| [`05-demo-reflection`](./bundles/05-demo-reflection/README.md) | Before presentation | Demo script, postmortem |
| [`06-advanced`](./bundles/06-advanced/README.md) | Larger projects | Feature folders, checklists, GitHub issue workflows |

---

## Bundle 1 — Starter: From Raw Idea to PRD

Use this when you only have an app idea.

### Skills

1. [`grill-my-idea`](./skills/grill-my-idea/SKILL.md)
2. [`idea-to-intent`](./skills/idea-to-intent/SKILL.md)
3. [`intent-to-prd`](./skills/intent-to-prd/SKILL.md)

### Outputs

```text
docs/ai-native/01-grill-my-idea.md
docs/ai-native/02-intent-brief.md
docs/ai-native/03-prd.md
```

### Student prompts

```text
Use grill-my-idea.
My app idea is: [idea].
Challenge the idea before I write a PRD.
Save the output to docs/ai-native/01-grill-my-idea.md.
```

```text
Use idea-to-intent.
Read docs/ai-native/01-grill-my-idea.md first.
Create an Intent Brief.
Save the output to docs/ai-native/02-intent-brief.md.
```

```text
Use intent-to-prd.
Read docs/ai-native/02-intent-brief.md first.
Create a PRD with user stories, FR IDs, SC IDs, acceptance criteria, non-goals, and risks.
Save the output to docs/ai-native/03-prd.md.
```

### Teacher checkpoint

Before moving on, the student should be able to answer:

- Who is the user?
- What problem is being solved?
- What is out of scope?
- What would prove the app works?

---

## Bundle 2 — Spec-Driven: Make the PRD Buildable

This bundle is inspired by GitHub Spec Kit’s spec-driven development workflow, adapted for students.

### Skills

1. [`project-constitution`](./skills/project-constitution/SKILL.md)
2. [`clarify-prd`](./skills/clarify-prd/SKILL.md)
3. [`prd-to-architecture`](./skills/prd-to-architecture/SKILL.md)
4. [`architecture-to-issues`](./skills/architecture-to-issues/SKILL.md)
5. [`analyze-artifacts`](./skills/analyze-artifacts/SKILL.md)

### Outputs

```text
docs/ai-native/14-project-constitution.md
docs/ai-native/15-clarification-log.md
docs/ai-native/04-architecture.md
docs/ai-native/05-issues.md
docs/ai-native/16-artifact-analysis.md
```

### Student prompts

```text
Use project-constitution.
Read docs/ai-native/03-prd.md first.
Create non-negotiable project principles and quality gates.
Save the output to docs/ai-native/14-project-constitution.md.
```

```text
Use clarify-prd.
Read docs/ai-native/03-prd.md and docs/ai-native/14-project-constitution.md first.
Ask up to 5 high-impact clarification questions.
Save the log to docs/ai-native/15-clarification-log.md.
```

```text
Use prd-to-architecture.
Read the PRD, constitution, and clarification log first.
Create a simple architecture plan with data model, contracts, research notes, risks, and requirement mapping.
Save the output to docs/ai-native/04-architecture.md.
```

```text
Use architecture-to-issues.
Read the PRD and architecture first.
Break the work into small issues with T### IDs, US/FR/SC links, likely files, acceptance criteria, and verification.
Save the output to docs/ai-native/05-issues.md.
```

```text
Use analyze-artifacts.
Read the PRD, constitution, architecture, and issues first.
Find contradictions, missing coverage, vague requirements, and traceability gaps.
Save the report to docs/ai-native/16-artifact-analysis.md.
```

### Teacher checkpoint

Before coding, the student should have:

- Requirement IDs: `FR-001`, `FR-002`, etc.
- User story IDs: `US-001`, `US-002`, etc.
- Success criteria IDs: `SC-001`, `SC-002`, etc.
- Small issues that map back to requirements.
- A clean artifact analysis with no critical gaps.

---

## Bundle 3 — Build Loop: Prompt, Build, Review, Fix

Use this bundle during implementation. Do **one issue at a time**.

### Skills

1. [`agent-rules`](./skills/agent-rules/SKILL.md)
2. [`issue-to-prompt`](./skills/issue-to-prompt/SKILL.md)
3. [`run-the-loop`](./skills/run-the-loop/SKILL.md)
4. [`review-the-code`](./skills/review-the-code/SKILL.md)

### Outputs

```text
AGENTS.md
docs/ai-native/07-issue-prompt.md
docs/ai-native/08-loop-log.md
docs/ai-native/09-code-review.md
```

### Student workflow

For each issue:

```text
issue → prompt → build → review → test → fix → decide
```

### Student prompts

```text
Use agent-rules.
Read the PRD, architecture, and issues first.
Create AGENTS.md so AI assistants follow this project’s intent, stack, style, and verification rules.
```

```text
Use issue-to-prompt.
Read docs/ai-native/05-issues.md and select Issue [number].
Create one focused coding prompt for that issue only.
Save the output to docs/ai-native/07-issue-prompt.md.
```

```text
Use run-the-loop.
Run one safe AI-assisted build loop for this issue.
Record build steps, review notes, test results, fixes, and the final decision.
Save the log to docs/ai-native/08-loop-log.md.
```

```text
Use review-the-code.
Read the issue, PRD, architecture, and loop log.
Review the implementation against the requirement IDs and flag must-fix items.
Save the review to docs/ai-native/09-code-review.md.
```

### Teacher checkpoint

The student should show:

- The issue they worked on.
- The prompt they gave AI.
- The code diff or changed files.
- Review findings.
- Test or manual evidence.
- A decision: accept, fix, rollback, split, or ask for help.

---

## Bundle 4 — Quality Proof: Test, Trace, Red-Team, Converge

Use this before submission. This bundle turns “the app runs” into “the app is supported by evidence.”

### Skills

1. [`test-the-app`](./skills/test-the-app/SKILL.md)
2. [`traceability-matrix`](./skills/traceability-matrix/SKILL.md)
3. [`red-team-my-app`](./skills/red-team-my-app/SKILL.md)
4. [`converge-the-app`](./skills/converge-the-app/SKILL.md)

### Outputs

```text
docs/ai-native/10-test-plan.md
docs/ai-native/17-traceability-matrix.md
docs/ai-native/11-risk-review.md
docs/ai-native/18-convergence-report.md
```

### Student prompts

```text
Use test-the-app.
Read the PRD, issues, loop log, and code review first.
Create a test plan where each test names the US/FR/SC ID it verifies.
Save the output to docs/ai-native/10-test-plan.md.
```

```text
Use traceability-matrix.
Read the PRD, architecture, issues, and test plan first.
Map every requirement to user story, architecture component, issue, test/check, evidence, and status.
Save the output to docs/ai-native/17-traceability-matrix.md.
```

```text
Use red-team-my-app.
Read the PRD, architecture, and current app behavior.
Find misuse, privacy, security, reliability, accessibility, and UX risks.
Save the output to docs/ai-native/11-risk-review.md.
```

```text
Use converge-the-app.
Read all project artifacts and inspect the current implementation.
Compare the app against intended requirements and list done, missing, partial, contradictory, and unrequested work.
Save the report to docs/ai-native/18-convergence-report.md.
```

### Teacher checkpoint

The student should have evidence for:

- What requirements are covered.
- What tests or manual checks passed.
- What risks remain.
- What is missing or partial.
- Whether the app is ready, not ready, or ready with limitations.

---

## Bundle 5 — Demo & Reflection

Use this before presentation or after a milestone.

### Skills

1. [`demo-ready`](./skills/demo-ready/SKILL.md)
2. [`postmortem`](./skills/postmortem/SKILL.md)

### Outputs

```text
docs/ai-native/12-demo-script.md
docs/ai-native/13-postmortem.md
```

### Student prompts

```text
Use demo-ready.
Read the PRD, test plan, traceability matrix, risk review, and convergence report first.
Create a clear demo script with problem statement, walkthrough, evidence, limitations, and next steps.
Save the output to docs/ai-native/12-demo-script.md.
```

```text
Use postmortem.
Read all major project artifacts.
Reflect on what worked, what failed, how AI helped or misled, what was verified, and what should improve next time.
Save the output to docs/ai-native/13-postmortem.md.
```

### Teacher checkpoint

The student should be able to explain:

- What they built.
- Why they built it.
- Which requirements are proven.
- What AI generated.
- What they personally verified.
- What they would improve next.

---

## Bundle 6 — Advanced Use

Use this for capstone projects, stronger teams, or larger apps.

Advanced students may organize each feature like this:

```text
docs/ai-native/features/001-login/
├── spec.md
├── plan.md
├── data-model.md
├── contracts.md
├── tasks.md
├── tests.md
└── evidence.md
```

Possible advanced workflows:

- Convert issues into GitHub issues.
- Use separate feature folders for large apps.
- Create custom checklists for privacy, UX, accessibility, or grading.
- Use multiple AI agents only after PRD, architecture, and issues are stable.

---

## Complete Skill Index

| # | Skill | Use It To | Artifact |
|---:|---|---|---|
| 01 | [`grill-my-idea`](./skills/grill-my-idea/SKILL.md) | Challenge a raw app idea | `docs/ai-native/01-grill-my-idea.md` |
| 02 | [`idea-to-intent`](./skills/idea-to-intent/SKILL.md) | Create an Intent Brief | `docs/ai-native/02-intent-brief.md` |
| 03 | [`intent-to-prd`](./skills/intent-to-prd/SKILL.md) | Create a PRD | `docs/ai-native/03-prd.md` |
| 04 | [`project-constitution`](./skills/project-constitution/SKILL.md) | Define project principles | `docs/ai-native/14-project-constitution.md` |
| 05 | [`clarify-prd`](./skills/clarify-prd/SKILL.md) | Remove ambiguity | `docs/ai-native/15-clarification-log.md` |
| 06 | [`prd-to-architecture`](./skills/prd-to-architecture/SKILL.md) | Design the system | `docs/ai-native/04-architecture.md` |
| 07 | [`architecture-to-issues`](./skills/architecture-to-issues/SKILL.md) | Create small implementation issues | `docs/ai-native/05-issues.md` |
| 08 | [`analyze-artifacts`](./skills/analyze-artifacts/SKILL.md) | Check consistency before coding | `docs/ai-native/16-artifact-analysis.md` |
| 09 | [`agent-rules`](./skills/agent-rules/SKILL.md) | Create AI rules / AGENTS.md | `AGENTS.md` |
| 10 | [`issue-to-prompt`](./skills/issue-to-prompt/SKILL.md) | Create one focused coding prompt | `docs/ai-native/07-issue-prompt.md` |
| 11 | [`run-the-loop`](./skills/run-the-loop/SKILL.md) | Build one issue safely | `docs/ai-native/08-loop-log.md` |
| 12 | [`review-the-code`](./skills/review-the-code/SKILL.md) | Review AI-generated code | `docs/ai-native/09-code-review.md` |
| 13 | [`test-the-app`](./skills/test-the-app/SKILL.md) | Create test plan and evidence | `docs/ai-native/10-test-plan.md` |
| 14 | [`traceability-matrix`](./skills/traceability-matrix/SKILL.md) | Map requirements to proof | `docs/ai-native/17-traceability-matrix.md` |
| 15 | [`red-team-my-app`](./skills/red-team-my-app/SKILL.md) | Find risks before demo | `docs/ai-native/11-risk-review.md` |
| 16 | [`converge-the-app`](./skills/converge-the-app/SKILL.md) | Compare app against intended artifacts | `docs/ai-native/18-convergence-report.md` |
| 17 | [`demo-ready`](./skills/demo-ready/SKILL.md) | Prepare final demo | `docs/ai-native/12-demo-script.md` |
| 18 | [`postmortem`](./skills/postmortem/SKILL.md) | Reflect and improve | `docs/ai-native/13-postmortem.md` |

---

## Artifact System

Every downstream skill must load files from disk before drafting the next artifact.

Required behavior:

1. Check that upstream artifact files exist.
2. Read upstream files from the current project, not only from chat history.
3. If a required file is missing, stop and ask the student to run the previous skill or provide the missing artifact.
4. Save the new artifact only after the source files have been read.
5. Add a `Sources Read` section to each saved artifact.

Why this matters:

- Chat history disappears.
- AI agents hallucinate if they rely on memory.
- Project artifacts create a visible evidence trail.
- Teachers can grade process, not only the final app.

---

## Spec-Driven Additions Borrowed From GitHub Spec Kit

This repo adapts several ideas from GitHub Spec Kit for university students:

| Spec Kit idea | Student-friendly adaptation |
|---|---|
| Constitution | `project-constitution` defines non-negotiable rules and quality gates. |
| Clarification | `clarify-prd` asks up to 5 important questions before architecture. |
| Requirement IDs | PRDs use `US-###`, `FR-###`, and `SC-###`. |
| Artifact analysis | `analyze-artifacts` checks PRD, architecture, and issues before coding. |
| Traceability | `traceability-matrix` maps requirements to issues, tests, and evidence. |
| Convergence | `converge-the-app` compares the implemented app against intended artifacts. |

The goal is not to copy Spec Kit exactly. The goal is to make spec-driven thinking practical for students.

---

## Templates

Reusable templates live in [`templates/`](./templates/):

- [`prd-template.md`](./templates/prd-template.md)
- [`constitution-template.md`](./templates/constitution-template.md)
- [`architecture-template.md`](./templates/architecture-template.md)
- [`issue-template.md`](./templates/issue-template.md)
- [`artifact-analysis-template.md`](./templates/artifact-analysis-template.md)
- [`traceability-matrix-template.md`](./templates/traceability-matrix-template.md)
- [`convergence-report-template.md`](./templates/convergence-report-template.md)
- [`checklist-template.md`](./templates/checklist-template.md)

Use these manually if your AI tool does not support skills.

---

## Manual Use Without skills.sh

If your agent does not support `skills.sh`, clone the repository:

```bash
git clone https://github.com/andrewtliem/ai-native-app-builder-skills.git
```

Then open the relevant `SKILL.md` file under `skills/` and paste or reference it in your AI assistant.

Example:

```text
Use the instructions from skills/intent-to-prd/SKILL.md.
Here is my Intent Brief: ...
Save the PRD to docs/ai-native/03-prd.md.
```

---

## Instructor Usage

A simple 5-week class flow:

| Week | Student Activity | Skills |
|---:|---|---|
| 1 | Idea framing | `grill-my-idea`, `idea-to-intent`, `intent-to-prd` |
| 2 | Spec and design | `project-constitution`, `clarify-prd`, `prd-to-architecture`, `architecture-to-issues`, `analyze-artifacts` |
| 3 | Implementation loop | `agent-rules`, `issue-to-prompt`, `run-the-loop`, `review-the-code` |
| 4 | Quality proof | `test-the-app`, `traceability-matrix`, `red-team-my-app`, `converge-the-app` |
| 5 | Demo and reflection | `demo-ready`, `postmortem` |

Suggested grading categories:

| Category | Evidence |
|---|---|
| Intent clarity | Intent Brief + PRD |
| Design quality | Architecture + issues |
| AI process discipline | Prompt + loop log + code review |
| Verification | Test plan + traceability matrix |
| Responsibility | Risk review + convergence report + postmortem |

---

## Common Mistakes to Avoid

1. **Running every skill in one prompt**  
   Move stage by stage. Read the artifact. Make a human decision.

2. **Letting AI invent the app**  
   AI may suggest, but the student owns the intent.

3. **Skipping verification**  
   A working demo is not the same as requirement coverage.

4. **Ignoring saved files**  
   Always read artifacts from `docs/ai-native/` before continuing.

5. **Accepting AI code without review**  
   Students must understand and explain the code they submit.

---

## Teaching Philosophy

This skill pack is based on two YouTube talks that shaped ATL’s thinking about AI-native software engineering:

- https://www.youtube.com/watch?v=q_Jq4IgYImk
- https://www.youtube.com/watch?v=VTYx7Ex-0bA

The interpretation here is ATL’s own reading of those ideas. Other educators may draw different lessons from the same videos.

For ATL, the main lesson is this:

> AI-native engineering is not about generating more code faster. It is about clearer intent, better systems, stronger verification, and human judgment.
