# Risk Review — Course Todo

## Sources Read
- docs/ai-native/03-prd.md
- docs/ai-native/04-architecture.md
- docs/ai-native/10-test-plan.md
- docs/ai-native/17-traceability-matrix.md

## Security Risks
- Low: no backend or authentication.
- Local storage can be inspected by anyone using the same browser profile.

## Privacy Risks
- Tasks may contain sensitive course or personal information.
- Because data stays local, cloud exposure risk is low.

## Reliability Risks
- Browser local storage can be cleared.
- Invalid local storage data can break loading if not handled safely.

## Accessibility Risks
- Form fields need labels.
- Status changes should not rely only on color.

## UX Risks
- Too many tasks can make the list hard to scan.
- Filters need a clear reset option.

## Misuse Risks
- Minimal. App does not post content publicly or contact other users.

## Recommended Fixes
1. Add “local-only data” note in UI.
2. Ensure complete status has text label, not color only.
3. Add safe handling for invalid local storage data.

Saved artifact: docs/ai-native/11-risk-review.md
Next recommended skill: converge-the-app
