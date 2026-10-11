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

Mode: Classroom

Questions were asked one at a time. The student answered each question before the AI default was shown.

| # | Question | Why It Matters | Student First Answer | AI Default (shown after) | Final Decision | Reason if Changed (student's words) | Tag |
|---|---|---|---|---|---|---|---|
| Q1 | Should due date be required or optional? | Affects form validation and data model. | Optional — some readings have no deadline. | Required, so tasks can always be sorted by date. | Optional | Kept my answer: “If it's required I'd type fake dates for readings, and adding a task takes longer than 30 seconds.” | `[student]` |
| Q2 | What should happen when local storage is unavailable? | Affects failure handling and tests. | Show a warning. | Show a warning and keep tasks in memory for the current session. | Show a warning and keep tasks in memory for the current session | Changed: “I didn't think about whether the tasks disappear right away. Keeping them until the tab closes is better.” | `[confirmed]` |
| Q3 | Should completed tasks be visible by default? | Affects filter behavior. | Visible. | Visible with a status label. | Visible with a status label | Changed: “Yes, without a label I can't tell done from not done at a glance.” | `[confirmed]` |

## Default Match Summary
- Final decisions identical to the AI default: 2 of 3
- Q1 shows the student rejecting the AI default with a reason tied to their own success criterion (SC-001).

## Decisions Added Back to PRD
- Due date is optional in v1 `[student]`
- If local storage fails, show a warning and keep tasks in memory for the current session `[confirmed]`
- Completed tasks remain visible with a status label unless filtered out `[confirmed]`

## Remaining Open Questions
- None blocking architecture.

Saved artifact: docs/ai-native/15-clarification-log.md
Default matches: 2 of 3
Next recommended skill: prd-to-architecture
