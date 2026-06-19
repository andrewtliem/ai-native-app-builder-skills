# Traceability Matrix — Course Todo

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md
- docs/ai-native/05-issues.md
- docs/ai-native/10-test-plan.md

## Coverage Summary
- Fully covered: FR-001 through FR-007
- Partially covered: local storage unavailable edge case
- Missing evidence: automated tests not yet implemented

## Matrix

| Requirement | User Story | Architecture Component | Issue / Task | Test / Check | Evidence | Status |
|---|---|---|---|---|---|---|
| FR-001 | US-001 | TaskForm | T002 | Test 1 | screenshot / manual check | Covered |
| FR-002 | US-001 | TaskForm validation | T002 | Test 2 | validation screenshot | Covered |
| FR-003 | US-001 | TaskList | T003 | Test 1 | list screenshot | Covered |
| FR-004 | US-002 | TaskItem | T003 | Test 3 | manual check | Covered |
| FR-005 | US-003 | TaskFilters | T004 | Test 5 | manual check | Covered |
| FR-006 | US-003 | TaskFilters | T004 | Test 4 | manual check | Covered |
| FR-007 | US-004 | storage.ts | T001 | Test 6 | refresh recording | Covered |
| SC-001 | US-001 | TaskForm | T002 | Test 1 | under 30 seconds | Covered |
| SC-004 | US-004 | storage.ts | T001 | Test 6 | refresh recording | Covered |

## Missing or Weak Evidence
- No automated tests yet.
- Local storage unavailable behavior needs explicit demo or unit test.

## Recommended Next Actions
1. Add storage helper unit tests.
2. Capture a short demo video for refresh persistence.

Saved artifact: docs/ai-native/17-traceability-matrix.md
Next recommended skill: red-team-my-app
