# Spec-Driven Bundle

**Purpose:** Make the PRD buildable before any AI coding starts.

**When to use:** Use before coding. This is the main Spec Kit-inspired addition.

Adapted from GitHub Spec Kit’s spec-driven development workflow for students.

## Skills

| Skill | Role |
|---|---|
| [`project-constitution`](../../skills/project-constitution/SKILL.md) | Define non-negotiable project principles and quality gates. |
| [`clarify-prd`](../../skills/clarify-prd/SKILL.md) | Ask up to five important questions to remove ambiguity. |
| [`prd-to-architecture`](../../skills/prd-to-architecture/SKILL.md) | Turn the PRD into technical architecture and design decisions. |
| [`architecture-to-issues`](../../skills/architecture-to-issues/SKILL.md) | Break architecture into small implementation issues. |
| [`analyze-artifacts`](../../skills/analyze-artifacts/SKILL.md) | Check PRD, constitution, architecture, and issues for gaps and contradictions. |

## Outputs

```text
docs/ai-native/14-project-constitution.md
docs/ai-native/15-clarification-log.md
docs/ai-native/04-architecture.md
docs/ai-native/05-issues.md
docs/ai-native/16-artifact-analysis.md
```

## Student prompts

```text
Use project-constitution.
Read docs/ai-native/03-prd.md first.
Create non-negotiable project principles and quality gates.
Save the output to docs/ai-native/14-project-constitution.md.
```

```text
Use clarify-prd.
Read docs/ai-native/03-prd.md and docs/ai-native/14-project-constitution.md first.
Ask up to 5 high-impact clarification questions, one at a time.
Show your recommended default only after I answer.
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

## Teacher checkpoint

Before coding, the student should have:

- Requirement IDs: `FR-001`, `FR-002`, etc.
- User story IDs: `US-001`, `US-002`, etc.
- Success criteria IDs: `SC-001`, `SC-002`, etc.
- Small issues that map back to requirements.
- A clean artifact analysis with no critical gaps.

## Teaching Note

Students should run these skills one at a time, read the saved artifact, make a human decision, revise if needed, then continue. The bundle is a teaching path, not an autopilot.

---

← [01-starter](../01-starter/README.md) · [Main README](../../README.md) · [03-build-loop](../03-build-loop/README.md) →
