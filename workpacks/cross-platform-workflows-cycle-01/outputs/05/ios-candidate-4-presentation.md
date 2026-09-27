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

## Baseline functional non-regression ledger

Candidate 4 is a synthesis proposal, not an exception to the accepted Workflow baseline. The following ledger is an eligibility condition independent of analytical score.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 4 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every iOS Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Xcode/macOS, scheme, simulator/device, signing and release details populate the contract without replacing it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes intended behavior/change and Path Scope authorizes files/modules. Both constraints apply independently across portable, Mac build, test and release lanes; path permission never authorizes unrelated semantic change. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review applies only to the exact reviewed commit SHA. Any later commit creates a new HEAD and requires a new semantic decision; repeated CI/Xcode results cannot carry acceptance forward automatically. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Swift tests, xcodebuild, simulator/device checks, .xcresult, CI and analytical scores are evidence only and cannot replace the semantic state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections that keep the same Objective continue in the same Issue, branch and PR. Changes to Objective, Semantic Scope, Path Scope, authority, baseline semantics or other material contract terms require escalation instead of silent expansion. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI and optional external actors never self-merge. SEMANTIC_ACCEPTED is exact-SHA and distinct from MERGE_ELIGIBLE. Where integration is authorized, the Supervisor merges only after exact-SHA semantic acceptance plus baseline merge-eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Archive/export, signing, TestFlight upload, App Store Connect access or release automation do not create publication authority. **PUBLISH = HUMAN ACTION** unless explicitly changed by the Human. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | A new authorized session reconstructs from GitHub the governing Work Item/Issue, branch/ref and exact HEAD, active PR, environment contract, latest applicable Supervisor decision and reviewed SHA, verification/checkpoint evidence, release constraints and unresolved blockers. Prior chat transcript is not authoritative continuity. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | Candidate 4 remains eligible only if every protected baseline function is preserved or explicitly justified. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO** that analytical score, sensitivity, portability, automation, CI/test success or cost cannot offset. |

The ledger preserves iOS platform semantics: native app build/simulator/archive/signing remain macOS/Xcode-bound where required; Linux remains limited to compatible non-iOS Swift/package/domain work; simulator and physical-device evidence remain distinct; signing/provisioning remain protected; TestFlight/App Store remain separately authorized; Xcode Cloud remains optional; Apple-required coupling remains distinct from avoidable provider coupling.

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
