# Postmortem — Course Todo

## Sources Read
- docs/ai-native/01-grill-my-idea.md
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md
- docs/ai-native/05-issues.md
- docs/ai-native/08-loop-log.md
- docs/ai-native/09-code-review.md
- docs/ai-native/18-convergence-report.md

## What Worked
- The idea became clearer after limiting scope to local-first course tasks.
- Requirement IDs made review and testing easier.
- The project constitution helped reject scope creep such as login and priority fields.
- The loop log captured AI mistakes and human decisions.

## What Failed or Was Weak
- Automated tests were suggested but not implemented in this compact example.
- Only one issue has a detailed loop log.
- Evidence is described but screenshots/videos are not included.

## How AI Helped
- Drafted artifact structure.
- Suggested implementation details.
- Helped identify edge cases and risks.

## How AI Misled
- Suggested a priority field that was not requested in the PRD.
- Recommended making the due date required; the student rejected it because it conflicted with SC-001 (add a task in under 30 seconds).
- Its validation code looked correct but accepted a title made only of spaces. The bug surfaced only because the student had to predict the edge case before reading the AI review.
- Could have expanded scope too quickly without the constitution.

## What Was Verified
- Task creation and validation were manually verified in the example notes.
- 2 of 3 clarification decisions matched the AI default; the student gave a reason for each change and for the one rejection.
- Traceability shows every FR maps to at least one issue and test/check.

## What Should Improve Next Time
1. Add source code and actual test output to the example.
2. Add screenshots or a short demo video as evidence.
3. Create separate loop logs for completion, filtering, and persistence.

## Main Lesson
AI-native development is not asking AI to build everything. It is using AI inside a system of intent, artifacts, review, tests, and human judgment.

Saved artifact: docs/ai-native/13-postmortem.md
Next recommended skill: human review
