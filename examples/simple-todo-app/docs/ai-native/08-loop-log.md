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

Saved artifact: docs/ai-native/08-loop-log.md
Next recommended skill: review-the-code
