# Common Core Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Purpose
Define only the governance/evidence concepts genuinely shared by Android, iOS and Web.

## Common lifecycle

AUTHORIZED WORK ITEM
→ minimal context reconstruction
→ acceptance evidence definition
→ environment/application contract
→ bounded implementation
→ project-native verification
→ risk classifier
→ platform-specific verification adapter if required
→ evidence bundle
→ independent review/checkpoint
→ separately authorized merge/release/deployment

## Common invariants
1. Work Item defines authority and scope.
2. Technical capability does not create workflow authority.
3. Durable repository state, not chat memory, carries continuity.
4. Stable governance stays concise; task context is progressively disclosed.
5. Versions/policies used as evidence remain time-scoped.
6. Tests/CI are evidence, not approval.
7. Secrets/network/external services use least privilege.
8. Higher-risk device/browser/release checks are selected by evidence/risk.
9. Implementer cannot self-approve, merge or declare canonical adoption.
10. External actors are optional and capability-specific.

## Evidence bundle
Every substantial checkpoint should be able to identify:
- Work Item and ref/commit;
- environment/toolchain identity;
- checks performed;
- results and artifacts;
- device/browser/destination details when applicable;
- deviations/retries;
- unresolved warnings/uncertainties.

## Platform deltas that remain mandatory

### Android
Gradle/JDK/Android SDK, Android device/emulator capability, signing/AAB and Google Play/release policy.

### iOS
macOS/Xcode boundary, simulator/physical device, certificates/provisioning, TestFlight/App Store.

### Web
project-selected runtime/framework, browser matrix, accessibility/human UX, preview and deploy environments.

The common core must not erase those differences.

## External actor interface
Any optional actor MUST define:
- CAPABILITY
- PRECONDITIONS
- AUTHORIZED OPERATIONS
- FORBIDDEN OPERATIONS
- EXPECTED BASELINE
- EVIDENCE RETURNED
- STOP CONDITIONS
- ESCALATION PATH

CAPABILITY != AUTHORITY.

## Adoption boundary
This proposal is a presentation artifact only. A future authorized Work Item is required to adopt or adapt any element as canonical.
