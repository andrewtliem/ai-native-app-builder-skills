# Intent Brief — Simple Todo App

## Sources Read
- docs/ai-native/01-grill-my-idea.md

## Project Name
Course Todo

## Purpose
Help university students track course-related tasks in one simple local-first app.

## Target Users
- Primary: university students taking several classes.
- Secondary: instructors who want a small example app for teaching AI-native development.

## Problem
Students often lose track of assignments, readings, quizzes, and project deadlines because tasks are spread across many places.

## Proposed Solution
A browser-based todo app where students can:

- create course tasks
- assign each task to a course
- add optional due dates
- mark tasks as complete
- filter tasks by status or course

## Constraints
- No login in v1.
- Store data locally in the browser.
- Keep UI simple enough for a beginner to explain.
- Must be testable manually in a classroom demo.

## Success Criteria
- A student can add a task in under 30 seconds.
- A student can filter tasks by course and completion status.
- A student can close and reopen the browser without losing tasks.

## Tradeoffs
- Local-only storage is simpler but does not sync across devices.
- No collaboration in v1.
- No notification system in v1.

## Human Decision Needed
Confirm whether due dates are required or optional.

Saved artifact: docs/ai-native/02-intent-brief.md
Next recommended skill: intent-to-prd
