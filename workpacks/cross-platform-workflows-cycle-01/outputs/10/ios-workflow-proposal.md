# iOS Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Portable Mac-Gated, Risk-Tiered iOS Workflow

## Purpose
Keep task governance, context and evidence portable while recognizing the unavoidable macOS/Xcode boundary for native iOS app build, simulator, archive and signing operations.

## Baseline governance preservation — mandatory

This proposal preserves the accepted baseline guarantees exactly:

1. **Work Item contract** — every Work Item retains Objective + Acceptance Criteria + Authorized Scope + Relevant Sources + Verification + Base.
2. **Semantic Scope + Path Scope** — both are independent constraints; path permission never grants semantic permission.
3. **Exact-SHA Supervisor review** — semantic decisions apply only to the exact reviewed SHA; a new commit requires a new review.
4. **Supervisor decision state machine** — only `SEMANTIC_ACCEPTED | REWORK | HOLD | ESCALATE`; tests, CI, scores and actor output are evidence, not substitute decisions.
5. **Same-objective REWORK continuity** — corrections remain in the same Issue/branch/PR when objective and scope remain valid; scope/authority changes escalate.
6. **Supervisor-only merge boundary** — Implementer never self-merges and `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`.
7. **Publication authority** — `PUBLISH = HUMAN ACTION`. Build, sign, upload, deploy, credentials or release-tool capability do not transfer publication authority.
8. **GitHub session recovery** — a new authorized session must reconstruct Work Item, branch/ref + exact HEAD, PR, latest Supervisor decision/reviewed SHA, evidence/state and unresolved REWORK/HOLD/ESCALATE from durable GitHub artifacts.
9. **Baseline functional non-regression gate** — before recommendation/adoption, every protected guarantee must be preserved explicitly. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO**.

A HARD VETO cannot be compensated by analytical score, CI/test success, automation, portability, cost, convenience or external-actor capability.

Authority invariant:

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`


## Core flow

AUTHORIZED WORK ITEM
→ reconstruct minimal durable context
→ implementation / portable domain checks where applicable
→ MAC BUILD ADAPTER
   → affected scheme build + unit/integration tests
   → risk trigger for simulator/device tests
→ evidence bundle
→ exact-SHA independent review/checkpoint
→ merge only after separate merge-eligibility checks
→ publication only by Human action

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

## Signing / TestFlight / App Store boundary
Normal implementation CI has no production distribution private keys by default.

Technical pre-publication work may include:
- current Apple SDK/submission requirement freshness check;
- authorized certificate/provisioning context;
- archive/export evidence;
- staging evidence.

Publication invariant:

`PUBLISH = HUMAN ACTION`

CI capability, signing keys, App Store Connect access, upload ability or ordinary Work Item permission do not transfer TestFlight/App Store publication authority to Implementer, CI or an external actor.

## Optional external actor
Extension point: Mac/device/build/signing/pre-publication technical operator.

Contract:
- CAPABILITY: exact macOS/Xcode/device/build/signing operation.
- PRECONDITIONS: governing Work Item, exact ref/SHA/artifact, Apple/team authority where needed, matrix/config.
- AUTHORIZED OPERATIONS: named technical build/test/archive/sign/stage operation only.
- FORBIDDEN OPERATIONS: authority/scope changes, unrelated source edits, self-approval, merge, semantic decisions and production publication.
- EXPECTED BASELINE: governing Work Item + exact ref/SHA + toolchain/config + artifact identity.
- EVIDENCE RETURNED: build/test IDs, results, device/destination metadata and artifact references.
- STOP CONDITIONS: missing Apple role/credential/cost authorization, baseline mismatch, unsupported environment, scope contradiction or attempted publication.
- ESCALATION PATH: Supervisor/Human.

### Durable external-actor activity — mandatory

Every external-actor invocation MUST create or update a durable GitHub activity/record under the governing Work Item, per Issue #2 comment `5879863384`.

Minimum record:
- ACTIVITY_ID / reference;
- GOVERNING_WORK_ITEM;
- ACTOR_TYPE;
- CAPABILITY;
- OBJECTIVE;
- PRECONDITIONS;
- AUTHORIZED_OPERATIONS;
- FORBIDDEN_OPERATIONS;
- EXPECTED_BASELINE / exact ref or SHA when applicable;
- EVIDENCE_REQUIRED;
- RESULT / evidence returned;
- STOP_CONDITIONS;
- ESCALATION_PATH;
- STATUS / closure state.

Required reconstructable lifecycle:

`request → authority → execution → evidence → result → stop/escalation`

The durable activity record is evidence/continuity only. It does not create Workflow authority, expand scope, authorize merge, issue semantic decisions or authorize publication.


## Unresolved human decisions
A concrete iOS project must decide:
- Mac CI provider/capacity;
- simulator/physical-device matrix;
- certificate/key/provisioning custody;
- whether TestFlight/App Store technical staging is authorized;
- App Store Connect roles;
- acceptable macOS runner/device cost;
- the Human publication action.

## Platform delta preserved
iOS remains distinct through the macOS/Xcode native boundary, simulator versus physical-device evidence, Apple certificates/provisioning and TestFlight/App Store distribution. Unavoidable Apple coupling is not abstracted away.

## Evidence
Detailed basis:
- outputs/04/ios-evidence.md
- outputs/05/ios-comparison.md
- outputs/05/ios-sensitivity.md
- outputs/08/platform-deltas.md
- outputs/09/contradiction-audit.md
- outputs/09/source-freshness-audit.md
