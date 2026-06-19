# Test Plan — Course Todo

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/05-issues.md
- docs/ai-native/08-loop-log.md
- docs/ai-native/09-code-review.md

## Scope
Manual test plan for v1 classroom demo.

## Must-Pass Tests

### Test 1 — Add Valid Task
**Verifies:** US-001, FR-001, SC-001  
**Steps:** Enter title “Read Chapter 3”, course “MIS”, click Add.  
**Expected Result:** Task appears in list.

### Test 2 — Validate Empty Task
**Verifies:** US-001, FR-002  
**Steps:** Leave title empty, enter course “MIS”, click Add.  
**Expected Result:** Validation message appears and no task is created.

### Test 3 — Complete Task
**Verifies:** US-002, FR-004, SC-002  
**Steps:** Click Complete on an incomplete task.  
**Expected Result:** Task status changes to complete.

### Test 4 — Filter by Course
**Verifies:** US-003, FR-006, SC-003  
**Steps:** Add tasks for MIS and SWE, select MIS filter.  
**Expected Result:** Only MIS tasks appear.

### Test 5 — Filter by Status
**Verifies:** US-003, FR-005, SC-003  
**Steps:** Create complete and incomplete tasks, select incomplete filter.  
**Expected Result:** Only incomplete tasks appear.

### Test 6 — Refresh Persistence
**Verifies:** US-004, FR-007, SC-004  
**Steps:** Add a task, refresh browser.  
**Expected Result:** Task remains visible.

## Edge Cases
- Very long task title.
- Duplicate task title.
- Optional due date left blank.

## Failure Cases
- Local storage unavailable.
- Invalid stored JSON.

## Automated Test Suggestions
- Unit test storage helpers.
- Component test TaskForm validation.
- Integration test add + persist flow.

## Demo Checklist
- Add task.
- Complete task.
- Filter by course.
- Filter by status.
- Refresh and show task remains.

## Evidence to Collect
- Screenshot of populated task list.
- Screenshot of validation message.
- Screen recording of refresh persistence.

Saved artifact: docs/ai-native/10-test-plan.md
Next recommended skill: traceability-matrix
