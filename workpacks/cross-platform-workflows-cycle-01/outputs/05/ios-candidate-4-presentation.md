# iOS Candidate 4 — Presentation proposal

STATUS: PROPOSAL — NOT CANONICAL

## Name
**Portable Mac-Gated, Risk-Tiered iOS Workflow**

## Core rule
Separate the workflow into:
1. provider-neutral task/context/evidence control;
2. an explicit macOS/Xcode build boundary;
3. risk-triggered simulator/device verification;
4. an isolated signing/TestFlight/App Store release boundary.

## Workflow
```text
AUTHORIZED TASK
→ minimal context reconstruction
→ implementation
→ portable/domain checks where applicable
→ MAC BUILD ADAPTER
   ├─ build + unit/integration tests
   └─ risk trigger → simulator/device tests
→ evidence bundle
→ independent review
→ RELEASE ADAPTER only if separately authorized
```

## Environment contract
Persist:
- Xcode/macOS compatibility;
- scheme/configuration;
- dependency state;
- deployment target;
- test plan/destinations;
- exact xcodebuild commands.

Do not encode "latest Xcode" as a permanent invariant.

## Test policy
Default:
- Swift Testing/XCTest unit/integration suite;
- xcodebuild affected scheme;
- retain .xcresult.

Simulator/device tier is required when UI/runtime/device semantics matter. Physical devices are required when simulator fidelity is insufficient.

## Portability rule
Linux may support pure Swift/package/domain work if compatible, but native iOS app build, simulator, archive and signing remain macOS/Xcode work.

The Mac build adapter may be backed by self-hosted Mac, GitHub macOS Actions, Xcode Cloud or another authorized macOS CI provider.

## Release/security boundary
Normal implementation context has no production distribution private keys by default.

Release requires:
- current App Store SDK/submission requirement check;
- authorized certificate/provisioning context;
- archive/export evidence;
- TestFlight/App Store action only when explicitly authorized.

## External actor
Optional Mac/device/release operator only for a concrete missing capability, under the standard actor contract (capability, preconditions, authorized/forbidden operations, expected baseline, evidence, stop conditions, escalation).

## Apple-specific facts preserved
- Xcode tooling is macOS-bound.
- simulator != physical device.
- certificates/profiles/App Store Connect are real release constraints.
- TestFlight is a distinct distribution boundary.
- Xcode Cloud is optional, not canonical infrastructure.

## Non-goals
- no mandatory Xcode Cloud;
- no mandatory GitHub Actions;
- no Linux-native iOS app build claim;
- no automatic App Store publication;
- no self-approval;
- no canonical adoption.

## Evidence trace
- macOS/Xcode boundary: I-01, I-02.
- testing: I-03, I-04, I-05.
- signing/provisioning: I-06.
- TestFlight/App Store Connect: I-07, I-08.
- current/future SDK requirements: I-09, I-10.
- cloud CI options: I-11, I-12.
- portability inference: I-13, I-14.
