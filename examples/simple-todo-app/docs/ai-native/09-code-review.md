# Code Review Report — T002 Task Creation Form

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md
- docs/ai-native/05-issues.md
- docs/ai-native/08-loop-log.md

## Verdict
Pass after one fix (whitespace-only title found during the explanation check).

## Matches the Issue?
Yes. The form creates tasks and validates required fields.

## Requirement Coverage

| Requirement / Story | Evidence in Code | Status |
|---|---|---|
| US-001 | TaskForm supports user task creation flow | Covered |
| FR-001 | title + course fields and submit handler | Covered |
| FR-002 | empty title/course validation | Covered |
| SC-001 | manual add task flow under 30 seconds | Covered |

## Matches the PRD?
Yes. No login, backend, or collaboration was added.

## Unrelated Changes
AI initially added a priority field. It was removed during cleanup.

## Must Fix
- Title or course made only of spaces passes validation (`if (!title)` treats `"   "` as filled). Trim before validating. Fixed in Build Attempt 2 of `08-loop-log.md`.

## Should Fix
- Add automated component test later if test framework is available.

## Security / Privacy Notes
No network calls or external storage introduced.

## Missing Verification
Automated test not yet written.

## Student Explanation Check (written before the AI review)
**Block reviewed:** `TaskForm.tsx` → `handleSubmit`
**Edge case:** title made only of spaces

| Prompt | Student Answer (verbatim) | Checked By | Correct? |
|---|---|---|---|
| What it does and why | “It stops the page from reloading, checks that title and course are filled, shows the error if not, otherwise makes a task object with an id and sends it up to App, then clears the form.” | Trace | Yes |
| Prediction for the edge case | “It shows the validation message because the title is empty.” | Trace + manual run | No — `!title` is false for `"   "`, so a blank-looking task was created |
| One suspected problem | “Maybe the due date format is wrong if the browser doesn't support date input.” | Review findings | Not found (date input falls back to text; stored as string) |

**Rating (first pass):** Partial — explanation correct, prediction wrong.

**Tutoring pass:** The AI asked “What does `!"   "` evaluate to in JavaScript?” The student tested it in the console, saw `false`, and proposed trimming the input.

**Rating (after fix, same block):** Understood — student predicted that `"   "` now shows the message and that `"  Read Chapter 3 "` is saved trimmed. Both confirmed by manual run.

## Loop Decision
Continue with fix (attempt 1) → Accept (attempt 2).

Saved artifact: docs/ai-native/09-code-review.md
Explanation check: Understood (after one tutoring pass)
Next recommended skill: test-the-app
