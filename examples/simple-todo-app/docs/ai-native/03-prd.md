# Product Requirements Document — Course Todo

## Sources Read
- docs/ai-native/02-intent-brief.md

## Overview
Course Todo is a local-first browser app that helps university students track course-related tasks.

## Target Users
University students managing multiple course responsibilities.

## Problem
Course tasks are scattered across LMS pages, chat groups, notebooks, and memory. Students need a simple way to capture and review tasks by course.

## Goals
- Let students create course tasks quickly.
- Let students view incomplete and completed tasks.
- Let students filter tasks by course.
- Preserve tasks after browser refresh.

## Non-Goals / Out of Scope
- User accounts and login.
- Cloud sync.
- Collaboration.
- Push notifications.
- Calendar integration.

## User Stories

### US-001 — Add Course Task (Priority: P1)
**User need:** As a student, I want to add a task with a course name so that I can track work for each class.  
**Why this priority:** Without task creation, the app has no core value.  
**Independent Test:** A user can add one valid task and see it appear in the task list.

**Acceptance Scenarios**
1. Given an empty task list, When the user enters a title and course then clicks Add, Then the task appears in the list.
2. Given an empty title, When the user clicks Add, Then the app shows a validation message and does not create a task.

### US-002 — Complete Task (Priority: P1)
**User need:** As a student, I want to mark a task complete so that I can see what work is done.  
**Why this priority:** Completion is central to task tracking.  
**Independent Test:** A user can mark a task complete and it moves to completed status.

**Acceptance Scenarios**
1. Given an incomplete task, When the user clicks Complete, Then the task status becomes complete.

### US-003 — Filter Tasks (Priority: P2)
**User need:** As a student, I want to filter tasks by course and status so that I can focus on relevant work.  
**Why this priority:** Filtering improves usability after multiple tasks exist.  
**Independent Test:** A user can select a course or status filter and only matching tasks are shown.

### US-004 — Persist Tasks Locally (Priority: P2)
**User need:** As a student, I want tasks to remain after refresh so that I do not lose my list.  
**Why this priority:** A todo app is not useful if data disappears.  
**Independent Test:** A user can create a task, refresh the page, and still see it.

## Functional Requirements
- **FR-001**: The system MUST allow users to create a task with title and course. `[student]`
- **FR-002**: The system MUST validate that task title and course are not empty. `[confirmed]`
- **FR-003**: The system MUST display all created tasks in a list. `[student]`
- **FR-004**: The system MUST allow users to mark a task complete or incomplete. `[student]`
- **FR-005**: The system MUST allow users to filter tasks by status. `[student]`
- **FR-006**: The system MUST allow users to filter tasks by course. `[student]`
- **FR-007**: The system MUST persist tasks in browser local storage automatically after each add or toggle, without a separate Save action. `[student]` (save timing `[confirmed]` in architecture read-back A1)

## Non-Functional Requirements
- **NFR-001 Accessibility**: Form controls must have visible labels. `[confirmed]`
- **NFR-002 Usability**: Primary actions must be clear and visible. `[confirmed]`
- **NFR-003 Privacy**: Data remains local to the browser. `[student]`
- **NFR-004 Simplicity**: v1 must not require a backend. `[student]`

## Success Criteria
- **SC-001**: A user can add a valid task in under 30 seconds. `[student]`
- **SC-002**: A user can complete and uncomplete a task without page reload. `[confirmed]`
- **SC-003**: A user can filter tasks by course and status. `[student]`
- **SC-004**: A created task remains after browser refresh. `[student]`

## Risks and Open Questions
- Should due date be required or optional? → resolved in `15-clarification-log.md` (Q1, optional `[student]`)
- What happens if local storage is unavailable? → resolved in `15-clarification-log.md` (Q2)
- Should completed tasks be hidden by default? → resolved in `15-clarification-log.md` (Q3)
- Known limitation: if stored data is corrupted, the app starts with an empty list (architecture read-back A2) `[confirmed]`

Saved artifact: docs/ai-native/03-prd.md
Open ai-proposed items: 0
Next recommended skill: project-constitution
