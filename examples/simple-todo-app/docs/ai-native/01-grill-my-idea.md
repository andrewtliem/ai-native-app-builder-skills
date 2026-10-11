# Idea Grill Report — Simple Todo App

## Sources Read
- None — first pipeline artifact

## Mode
Classroom

## Original Idea (student's words)
> I want to build a todo app for my class tasks.

## Grill Transcript

| # | Question | Student Answer (verbatim) | Follow-up / Contradiction Noted |
|---|---|---|---|
| Q1 | I restate your idea as: “an app where you write down tasks from your classes and tick them off.” Is that right? | Yes, but mostly for assignments and readings, not personal stuff. | Scope narrowed to course tasks. |
| Q2 | Who exactly would use it? | Me and students like me who take 6–7 courses a semester. | Specific enough. |
| Q3 | What goes wrong today without this app? | Tasks are everywhere. Some are in the LMS, some in WhatsApp groups, some I write in my notebook. I missed a reading quiz last month because the reminder was in a group chat. | Concrete pain with an example. |
| Q4 | How do you handle it now, and why isn't that enough? | I use the phone notes app. It doesn't know which course a task belongs to, so it becomes one long list. | Workaround exists; gap is course grouping. |
| Q5 | Is this only your problem, or have you seen others have it? | My two roommates complain about the same thing. I haven't asked anyone else. | Evidence is thin (3 people). Recorded as an assumption. |
| Q6 | You said “students like me.” Does that include people who want to share tasks with a group? | No. Just personal. Group projects are a different problem. | Collaboration is out of scope. |
| Q7 | Will people need an account? | I don't want login. I also don't know how to build a backend yet. | Constraint from skill level, not only preference. |
| Q8 | If there is no backend, where does the data live, and what happens if they switch phones? | In the browser, I guess. If they switch devices it's gone. That's okay for the first version. | Student accepts the tradeoff. |
| Q9 | Earlier you said you missed a quiz because of a reminder. Are notifications part of this app? | Hmm. I want them, but that sounds big. Not in v1. | Contradiction resolved: pain mentions reminders, v1 excludes them. Student aware. |
| Q10 | What would prove the app actually helps? | If I can add a task fast, like before the lecturer finishes talking — under half a minute — and I can see only one course's tasks when I need to. | Two checkable criteria. |
| Q11 | What should the app intentionally not do? | No login, no sharing, no notifications, no calendar sync. | — |
| Q12 | Do you want to proceed, revise, or research first? | Proceed, but keep it small. | — |

## Main User
- University students taking several courses at once, starting with me and my roommates `[student]`

## Problem Being Solved
- Course tasks are scattered across the LMS, chat groups, and notebooks, so tasks get missed `[student]`
- Phone notes do not group tasks by course `[student]`

## Evidence the Problem Is Real
- Student missed a reading quiz last month; two roommates report the same issue `[student]`

## Assumptions
- Other students have the same problem; evidence so far is only 3 people `[student]`
- Browser-only storage is acceptable for v1 `[student]`
- Students will open a web app quickly during a lecture `[confirmed]` (AI raised it as an unstated assumption; student agreed)

## Risks
- The app becomes another generic todo clone with no course focus `[confirmed]`
- Student adds login, collaboration, or notifications too early `[student]`

## Smallest Useful Version
- Add a task with a course, mark it done, filter by course and status, keep tasks after closing the browser `[student]`

## Non-Goals
- Login, sharing, notifications, calendar sync `[student]`

## Still Unanswered
- Whether students beyond the student's roommates have this problem (not researched yet)

## Decision Gate (chosen by the student)
Proceed, but keep v1 small and testable `[student]`

Saved artifact: docs/ai-native/01-grill-my-idea.md
Open ai-proposed items: 0
Next recommended skill: idea-to-intent
