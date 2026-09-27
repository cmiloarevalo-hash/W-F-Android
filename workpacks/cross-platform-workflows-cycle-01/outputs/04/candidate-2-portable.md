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

## Baseline functional non-regression ledger

Candidate 2 remains **PORTABLE / PROVIDER-NEUTRAL OUTSIDE UNAVOIDABLE APPLE BOUNDARIES**. Portability applies to orchestration and provider choice; it does not pretend Apple-required build/sign/distribution boundaries are portable away.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 2 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | The provider-neutral task contract retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Xcode/macOS adapter inputs, destination data and release preconditions extend the contract without weakening it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope and Path Scope remain separate authorization dimensions for portable prep, Mac build, test and release adapters. Provider substitution never expands either scope. |
| 3. Exact-SHA Supervisor semantic review | PRESERVED AS-IS | Evidence bundles identify the exact commit SHA reviewed by the Supervisor. A provider rerun or adapter substitution cannot carry semantic acceptance to a new HEAD created by another commit. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Adapter outputs, .xcresult bundles, simulator/device evidence and CI status are evidence only and cannot replace the semantic state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Same-objective corrections remain in the same Issue, branch and PR, preserving provider-neutral history and evidence continuity. Material contract/scope/authority changes require escalation. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer and provider adapters never self-merge. SEMANTIC_ACCEPTED is exact-SHA and distinct from MERGE_ELIGIBLE. Where merge is authorized, the Supervisor verifies exact-SHA acceptance plus baseline integration conditions before merge. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | A release adapter may technically archive, sign, upload or interact with App Store Connect only within explicit authorization, but those capabilities do not create publication authority. **PUBLISH = HUMAN ACTION** unless the Human explicitly changes that rule. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | Durable GitHub state records the Work Item, branch/ref and exact HEAD, PR, environment/adapter contract, evidence bundle, latest applicable Supervisor decision/reviewed SHA and unresolved decisions so a new session can continue without prior chat transcript. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | Provider portability is subordinate to the non-regression gate. Any abstraction that drops or weakens a protected baseline function is a **HARD VETO** and cannot be rescued by provider substitution, lower cost, automation or later scoring. |

iOS-specific semantics remain unchanged: native iOS build remains macOS/Xcode-bound where required; Linux stays limited to compatible non-iOS work; simulator != physical-device proof; signing/provisioning are protected; Xcode Cloud is optional; self-hosted Mac, GitHub macOS runner and other authorized Mac providers remain implementation choices.

## Strengths
Best provider substitution possible while acknowledging Apple-only steps; strong recovery.

## Weaknesses
Adapter abstraction adds documentation; Apple signing/distribution cannot be provider-neutral in the same sense as core orchestration.
