# PRD Clarification Log — Course Todo

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/14-project-constitution.md

## Ambiguity Scan Summary

| Area | Status | Notes |
|---|---|---|
| User roles | Clear | Single student user, no accounts. |
| Data model | Partial | Due date optionality needs decision. |
| UX flows | Clear | Add, complete, filter, refresh. |
| Edge cases | Partial | Local storage failure needs expected behavior. |
| Security/privacy | Clear | Local-only data. |
| Success criteria | Clear | SC IDs are measurable enough for class demo. |

## Clarification Questions

| # | Question | Why It Matters | Recommended Default | Student Answer |
|---|---|---|---|---|
| Q1 | Should due date be required or optional? | Affects form validation and data model. | Optional | Optional |
| Q2 | What should happen when local storage is unavailable? | Affects failure handling and tests. | Show warning and keep current session only | Show warning |
| Q3 | Should completed tasks be visible by default? | Affects filter behavior. | Visible with status label | Visible |

## Decisions Added Back to PRD
- Due date is optional in v1.
- If local storage fails, show a warning and keep tasks in memory for the current session.
- Completed tasks remain visible unless filtered out.

## Remaining Open Questions
- None blocking architecture.

Saved artifact: docs/ai-native/15-clarification-log.md
Next recommended skill: prd-to-architecture
