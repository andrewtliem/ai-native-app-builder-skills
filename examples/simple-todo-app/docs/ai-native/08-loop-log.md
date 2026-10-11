# Loop Log — T002 Build Task Creation Form

## Sources Read
- docs/ai-native/07-issue-prompt.md
- docs/ai-native/05-issues.md

## Issue
T002 — Build Task Creation Form

## Build Attempt 1

### Prompt Used
See `docs/ai-native/07-issue-prompt.md`.

### AI Output Summary
AI created:
- `TaskForm.tsx`
- form state for title, course, due date
- validation message
- submit handler integration in `App.tsx`

### Human Review Notes
- Form labels are visible.
- Validation message is understandable.
- AI initially added a priority field that was not in the PRD. Removed it to avoid scope creep.

### Test Evidence
Manual checks:
- Added task “Read Chapter 3” with course “MIS”: passed.
- Tried empty title: validation shown, no task created.
- Tried empty course: validation shown, no task created.

### Decision
Accept with small cleanup.

## Cleanup
- Removed unrequested priority field.
- Confirmed due date remains optional.

## Build Attempt 2 (after code review)

### Why
The explanation check in `09-code-review.md` showed that a title made only of spaces passes validation. The student's own prediction was wrong, which is how the bug was found.

### Prompt Used
“In `TaskForm.tsx`, treat a title or course that is empty after trimming spaces as empty. Do not change anything else.”

### Test Evidence
- Title “   ” with course “MIS”: validation shown, no task created. Passed.
- Title “  Read Chapter 3 ” with course “MIS”: task saved as “Read Chapter 3”. Passed.
- Re-ran the three checks from Attempt 1: passed.

### Decision
Accept.

Saved artifact: docs/ai-native/08-loop-log.md
Next recommended skill: review-the-code
