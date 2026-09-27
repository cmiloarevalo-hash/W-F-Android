# iOS Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Portable Mac-Gated, Risk-Tiered iOS Workflow

## Purpose
Keep task governance, context and evidence portable while recognizing the unavoidable macOS/Xcode boundary for native iOS app build, simulator, archive and signing operations.

## Core flow

AUTHORIZED WORK ITEM
→ reconstruct minimal durable context
→ implementation / portable domain checks where applicable
→ MAC BUILD ADAPTER
   → affected scheme build + unit/integration tests
   → risk trigger for simulator/device tests
→ evidence bundle
→ independent review/checkpoint
→ RELEASE ADAPTER only under separate authority

## Environment contract
Record:
- supported macOS/Xcode combination;
- scheme/configuration;
- dependencies;
- deployment target;
- test plan/destinations;
- deterministic xcodebuild commands.

Do not encode “latest Xcode” as a permanent invariant.

## Portability boundary
Pure Swift/package/domain work may be portable where its dependencies support it.

Native iOS app build, simulator, archive and signing are macOS/Xcode operations. Linux Swift support does not imply Linux-native iOS app build capability.

The Mac build adapter may use:
- self-hosted Mac;
- GitHub-hosted macOS runner;
- Xcode Cloud;
- another authorized macOS CI provider.

No one provider is mandatory.

## Verification tiers
Base checkpoint:
- Swift Testing and/or XCTest as appropriate;
- affected xcodebuild scheme;
- retained result evidence such as xcresult.

Add simulator evidence for UI/runtime behavior.

Add physical-device evidence when simulator fidelity is insufficient, including hardware, performance or device-specific behavior.

## Signing/TestFlight/App Store boundary
Normal implementation CI has no production distribution private keys by default.

Release/beta flow requires:
- current Apple SDK/submission requirement freshness check;
- authorized certificate/provisioning context;
- archive/export evidence;
- separately authorized TestFlight/App Store action.

CI capability does not grant App Store release authority.

## Optional external actor
Extension point: Mac/device/release operator.

Contract:
- CAPABILITY: exact macOS/Xcode/device/release operation.
- PRECONDITIONS: ref/artifact, Apple/team authority where needed, matrix/config.
- AUTHORIZED OPERATIONS: named build/test/release operation only.
- FORBIDDEN OPERATIONS: authority/scope changes, unrelated source edits, unapproved publication.
- EXPECTED BASELINE: ref + toolchain/config + artifact identity.
- EVIDENCE RETURNED: build/test/release IDs, results, device/destination metadata.
- STOP CONDITIONS: missing Apple role/credential/cost authorization, baseline mismatch, unsupported environment.
- ESCALATION PATH: Supervisor/Human.

## Unresolved human decisions
A concrete iOS project must decide:
- Mac CI provider/capacity;
- simulator/physical-device matrix;
- certificate/key/provisioning custody;
- whether TestFlight automation is authorized;
- App Store Connect roles;
- acceptable macOS runner/device cost.

## Evidence
Detailed basis:
- outputs/04/ios-evidence.md
- outputs/05/ios-comparison.md
- outputs/05/ios-sensitivity.md
- outputs/09/source-freshness-audit.md
