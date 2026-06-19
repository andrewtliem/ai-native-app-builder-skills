# Project Constitution — Course Todo

## Sources Read
- docs/ai-native/03-prd.md

## Core Principles

### I. Human Judgment Over AI Output
AI may draft code, tests, and UI, but the student must be able to explain every feature and design decision.

### II. Simplicity First
The first version must be local-first and must not add login, backend, notifications, or collaboration.

### III. Testable Features Only
Every feature must map to at least one manual test or automated test.

### IV. Privacy and Safety
No personal data leaves the browser in v1. No analytics, tracking, or external storage.

### V. Accessibility Basics
Inputs, buttons, and filters must have readable labels and keyboard-usable controls.

## Quality Gates
- [ ] PRD has `US-###`, `FR-###`, and `SC-###` identifiers.
- [ ] Architecture does not introduce a backend.
- [ ] Issues map to requirement IDs.
- [ ] Tests verify core user stories.
- [ ] Demo shows evidence, not only UI.

## Governance
If an AI suggestion adds backend sync, login, or notifications, reject it for v1 unless the PRD is explicitly revised.

Saved artifact: docs/ai-native/14-project-constitution.md
Next recommended skill: clarify-prd
