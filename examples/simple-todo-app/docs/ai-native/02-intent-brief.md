# Intent Brief — Simple Todo App

## Sources Read
- docs/ai-native/01-grill-my-idea.md

## Project Name
Course Todo `[student]`

## Purpose
Help university students track course-related tasks in one simple local-first app. `[student]`

## Target Users
- Primary: university students taking several courses at once `[student]`

## Problem
Course tasks are scattered across the LMS, chat groups, and notebooks, and phone notes do not group them by course, so tasks get missed. `[student]`

## Proposed Solution
A browser-based todo app where students can:

- create course tasks `[student]`
- assign each task to a course `[student]`
- add a due date (whether it is required is still open) `[confirmed]`
- mark tasks as complete `[student]`
- filter tasks by status or course `[student]`

## Constraints
- No login in v1 `[student]`
- Store data locally in the browser `[student]`
- Keep UI simple enough for a beginner to explain `[confirmed]`
- Must be testable manually in a classroom demo `[confirmed]`

## Success Criteria
- A student can add a task in under 30 seconds (student: “before the lecturer finishes talking — under half a minute”) `[student]`
- A student can filter tasks by course and completion status `[student]`
- A student can close and reopen the browser without losing tasks `[student]`

## Tradeoffs
- Local-only storage is simpler but does not sync across devices `[student]`
- No collaboration in v1 `[student]`
- No notification system in v1, even though missed reminders were part of the original pain `[student]`

## AI Proposals Reviewed With the Student

| Proposal | Student Decision | Student's Reason |
|---|---|---|
| Add a due date field | Accepted | “Readings and quizzes have dates, I just forgot to say it.” |
| Add instructors as a secondary user | Rejected | “Lecturers won't use this. It's for students. Adding them changes the app.” |
| Add a “priority” field | Rejected | “Too much to fill in when I'm in a hurry. It goes against adding a task fast.” |

## Open Questions
- Should the due date be required or optional? (to settle in `clarify-prd`)

Saved artifact: docs/ai-native/02-intent-brief.md
Open ai-proposed items: 0
Next recommended skill: intent-to-prd
