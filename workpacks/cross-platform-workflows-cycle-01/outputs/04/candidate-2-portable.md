# iOS Candidate 2 — Portable

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Maximize portability outside the unavoidable Apple build/sign/distribution boundary.

## Architecture
```text
TASK CONTRACT
→ PORTABLE PREP/DOMAIN LANE
→ MAC BUILD ADAPTER
→ TEST ADAPTER
→ EVIDENCE BUNDLE
→ RELEASE ADAPTER (separate authority)
```

## Portable prep/domain lane
May run on Linux/macOS when code permits:
- source validation;
- Swift package/domain tests that do not require Apple SDKs;
- generation/analysis tasks;
- task/evidence handling.

## Mac build adapter
Inputs:
- repo ref;
- Xcode version;
- scheme/configuration;
- destination;
- dependency state.

Outputs:
- build/test status;
- .xcresult;
- artifact identifiers;
- environment metadata.

Implementations may use self-hosted Mac, GitHub macOS runner, Xcode Cloud, or another authorized macOS service.

## Test adapter
- Swift Testing/XCTest unit suite;
- simulator destinations;
- optional physical-device provider;
- no assumption that simulator proves hardware behavior.

## Release adapter
Separates:
- certificates/private keys;
- provisioning profiles;
- archive/export;
- TestFlight/App Store Connect actions.

Release credentials and Apple account roles are explicit preconditions, never inferred from CI capability.

## Context recovery
Persist environment contract, evidence, unresolved decisions and provider-neutral adapter inputs/outputs.

## External actor
Optional Mac CI/device/release operator with capability, preconditions, authorized/forbidden operations, expected baseline, evidence, stop conditions and escalation.

## Strengths
Best provider substitution possible while acknowledging Apple-only steps; strong recovery.

## Weaknesses
Adapter abstraction adds documentation; Apple signing/distribution cannot be provider-neutral in the same sense as core orchestration.
