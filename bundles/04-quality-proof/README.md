# Quality Proof Bundle

**Purpose:** Prove that the app satisfies the requirements instead of only proving it runs.

**When to use:** Use before submission, grading, or demo.

## Skills

| Skill | Role |
|---|---|
| [`test-the-app`](../../skills/test-the-app/SKILL.md) | Create manual and automated test plans with evidence. |
| [`traceability-matrix`](../../skills/traceability-matrix/SKILL.md) | Map requirements to stories, issues, tests, and evidence. |
| [`red-team-my-app`](../../skills/red-team-my-app/SKILL.md) | Find security, privacy, misuse, reliability, accessibility, and UX risks. |
| [`converge-the-app`](../../skills/converge-the-app/SKILL.md) | Compare the current implementation against the intended artifacts and list remaining work. |

## Outputs

```text
docs/ai-native/10-test-plan.md
docs/ai-native/17-traceability-matrix.md
docs/ai-native/11-risk-review.md
docs/ai-native/18-convergence-report.md
```

## Student prompts

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

## Teacher checkpoint

The student should have evidence for:

- What requirements are covered.
- What tests or manual checks passed.
- What risks remain.
- What is missing or partial.
- Whether the app is ready, not ready, or ready with limitations.

## Teaching Note

Students should run these skills one at a time, read the saved artifact, make a human decision, revise if needed, then continue. The bundle is a teaching path, not an autopilot.

---

← [03-build-loop](../03-build-loop/README.md) · [Main README](../../README.md) · [05-demo-reflection](../05-demo-reflection/README.md) →
