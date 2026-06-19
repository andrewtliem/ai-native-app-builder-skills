# Issue Prompt — T002 Build Task Creation Form

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md
- docs/ai-native/05-issues.md
- docs/ai-native/16-artifact-analysis.md

## Selected Issue
T002 — Build Task Creation Form

## Prompt to Coding Agent

You are implementing one issue only: T002 Build Task Creation Form.

### Context
The app is Course Todo, a local-first browser app for students to track course tasks.

### Requirements Covered
- US-001
- FR-001: The system MUST allow users to create a task with title and course.
- FR-002: The system MUST validate that task title and course are not empty.
- SC-001: A user can add a valid task in under 30 seconds.

### Files Likely Touched
- `src/components/TaskForm.tsx`
- `src/App.tsx`
- optionally `src/types.ts`

### Implementation Instructions
1. Create a task form with fields for title, course, and optional due date.
2. Validate that title and course are not empty.
3. On valid submit, call the parent add-task handler.
4. Clear form after successful submit.
5. Show a clear validation message for invalid input.
6. Do not add backend, login, notifications, or collaboration.

### Acceptance Criteria
- Given valid title and course, When Add is clicked, Then a task appears.
- Given empty title or course, When Add is clicked, Then validation message appears.

### Verification
- Run the app.
- Add “Read Chapter 3” for course “MIS”.
- Confirm the task appears in the list.
- Try adding empty title and confirm validation message.

### Boundaries
Do not implement filters in this issue. Do not implement completion toggle in this issue unless already required by existing structure.

Saved artifact: docs/ai-native/07-issue-prompt.md
Next recommended skill: run-the-loop
