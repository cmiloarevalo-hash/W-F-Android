# iOS Candidate 1 — Minimal

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Keep the smallest credible iOS workflow.

## Flow
```text
Issue/task
→ minimal context
→ implement
→ Swift unit tests
→ xcodebuild affected scheme
→ targeted simulator/UI tests when needed
→ evidence summary
→ review
→ separate release gate
```

## Environment
- one known-good macOS/Xcode lane;
- project-pinned package/dependency state;
- xcodebuild as automation surface;
- Linux may be used only for non-iOS Swift/package work when actually compatible.

## Testing
- Swift Testing for new unit/integration logic where suitable;
- XCTest retained for existing tests and UI automation;
- simulator test only when the change crosses UI/platform boundaries;
- physical device reserved for behavior simulators cannot prove.

## Release
Signing, provisioning, TestFlight and App Store upload remain manual/authorized actions. Production distribution credentials are not present in normal implementation CI.

## External actor
None by default. A Mac operator may be introduced only when the Implementer lacks macOS/Xcode capability, with source-write and release authority forbidden unless separately authorized.

## Strengths
Low ceremony and cost; clear Apple boundary.

## Weaknesses
Less portable CI definition, thinner long-horizon evidence, more manual device/release judgment.
