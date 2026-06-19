# Implementation Issues — Course Todo

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md

## Issue 1 — Create Task Data Model and Storage
**Task ID:** T001  
**User Story:** US-004  
**Requirement IDs:** FR-007, SC-004  
**Priority:** P1  
**Parallelizable:** No  
**Goal:** Define the Task type and local storage functions.  
**Depends on:** none  
**Likely Files:** `src/types.ts`, `src/storage.ts`

**Acceptance Criteria**
- Given saved tasks exist, When the app loads, Then tasks are restored.
- Given local storage has invalid JSON, When loading, Then the app returns an empty list safely.

**Verification**
- Unit test storage load/save functions.
- Manual browser refresh test.

**AI Can Help With:** TypeScript types, storage helper functions, tests.  
**Student Must Judge:** Whether local storage behavior matches privacy and simplicity principles.  
**Risk Level:** Medium

## Issue 2 — Build Task Creation Form
**Task ID:** T002  
**User Story:** US-001  
**Requirement IDs:** FR-001, FR-002, SC-001  
**Priority:** P1  
**Parallelizable:** Yes after T001  
**Goal:** Add task form with title, course, optional due date, and validation.  
**Depends on:** T001  
**Likely Files:** `src/components/TaskForm.tsx`, `src/App.tsx`

**Acceptance Criteria**
- Given valid title and course, When Add is clicked, Then a task appears.
- Given empty title or course, When Add is clicked, Then validation message appears.

**Verification**
- Manual form test.
- Component test if test setup exists.

**AI Can Help With:** Form component and validation.  
**Student Must Judge:** Whether the form is understandable and accessible.  
**Risk Level:** Low

## Issue 3 — Display and Complete Tasks
**Task ID:** T003  
**User Story:** US-002  
**Requirement IDs:** FR-003, FR-004, SC-002  
**Priority:** P1  
**Parallelizable:** No  
**Goal:** Render tasks and allow complete/incomplete toggling.  
**Depends on:** T002  
**Likely Files:** `src/components/TaskList.tsx`, `src/components/TaskItem.tsx`

**Acceptance Criteria**
- Given an incomplete task, When Complete is clicked, Then it appears complete.
- Given a complete task, When Mark incomplete is clicked, Then it appears incomplete.

**Verification**
- Manual toggle test.

**Risk Level:** Low

## Issue 4 — Add Course and Status Filters
**Task ID:** T004  
**User Story:** US-003  
**Requirement IDs:** FR-005, FR-006, SC-003  
**Priority:** P2  
**Parallelizable:** Yes after T003  
**Goal:** Filter visible tasks by course and status.  
**Depends on:** T003  
**Likely Files:** `src/components/TaskFilters.tsx`, `src/App.tsx`

**Acceptance Criteria**
- Given multiple courses, When a course filter is selected, Then only matching tasks appear.
- Given complete/incomplete tasks, When a status filter is selected, Then only matching tasks appear.

**Verification**
- Manual filter test with at least three tasks.

**Risk Level:** Low

Saved artifact: docs/ai-native/05-issues.md
Next recommended skill: analyze-artifacts
