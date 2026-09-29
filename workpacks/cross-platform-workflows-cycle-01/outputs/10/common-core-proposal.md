# Common Core Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Purpose
Define only the governance/evidence concepts genuinely shared by Android, iOS and Web while preserving platform-specific execution, signing and distribution differences.

## Common lifecycle

AUTHORIZED WORK ITEM
→ reconstruct durable GitHub context
→ define acceptance evidence
→ bounded implementation within Semantic Scope + Path Scope
→ project-native verification
→ risk-triggered platform-specific verification
→ evidence bundle
→ exact-SHA Supervisor review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ merge eligibility checked separately when authorized
→ publication only by Human action

## Nine protected baseline guarantees

| # | Guarantee | Final-package preservation |
|---:|---|---|
| 1 | Work Item contract | Objective + Acceptance Criteria + Authorized Scope + Relevant Sources + Verification + Base remain mandatory. |
| 2 | Semantic Scope + Path Scope | Independent constraints; path permission never grants semantic permission. |
| 3 | Exact-SHA Supervisor review | Decision binds only the reviewed SHA; any new commit requires renewed semantic review. |
| 4 | Review state machine | Exactly `SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE`; automation cannot substitute. |
| 5 | Same-objective REWORK continuity | Same Issue/branch/PR while objective/scope remain valid; scope/authority changes escalate. |
| 6 | Supervisor-only merge boundary | Implementer never self-merges; `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`. |
| 7 | Publication authority | `PUBLISH = HUMAN ACTION`; technical publication capability never transfers authority. |
| 8 | GitHub session recovery | Reconstruct Work Item, branch/ref + exact HEAD, PR, latest Supervisor decision/reviewed SHA, evidence/state and unresolved conditions from GitHub. |
| 9 | Baseline functional non-regression gate | Every protected guarantee must be explicitly preserved; unexplained weakening is a HARD VETO. |

## HARD VETO

Any unexplained loss, weakening, substitution or reinterpretation of a protected baseline guarantee is a **HARD VETO**.

A HARD VETO cannot be compensated by:
- analytical score;
- CI/test success;
- automation depth;
- portability;
- cost;
- convenience;
- external-actor capability.

Eligibility/non-regression is evaluated before scoring or recommendation.

## Authority invariants

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`

`PUBLISH = HUMAN ACTION`

Technical access to source, devices, browsers, signing, deployment, credentials, release tooling or hosting controls does not create semantic authority, scope authority, merge authority or publication authority.

## Evidence bundle

Every substantial checkpoint should identify:
- governing Work Item;
- branch/ref and exact commit SHA;
- environment/toolchain identity;
- checks performed;
- results/artifacts;
- device/browser/destination details when applicable;
- deviations/retries;
- unresolved warnings/uncertainties;
- latest applicable Supervisor decision and reviewed SHA.

## Platform deltas that remain mandatory

### Android
Gradle/JDK/Android SDK, Android device/emulator capability, Android signing, APK/AAB and Google Play/other authorized distribution specifics.

### iOS
macOS/Xcode native boundary, simulator/physical device, Apple certificates/provisioning, TestFlight/App Store.

### Web
Project-selected runtime/build system, browser/E2E/accessibility/human UX, preview and provider-specific deployment; no universal mobile-style signing gate.

The Common Core must not erase those differences or force one build, device, signing, CI or distribution model.

## External actor interface

Any optional actor MUST define:
- CAPABILITY;
- PRECONDITIONS;
- AUTHORIZED OPERATIONS;
- FORBIDDEN OPERATIONS;
- EXPECTED BASELINE;
- EVIDENCE RETURNED;
- STOP CONDITIONS;
- ESCALATION PATH.

The actor cannot:
- expand Objective, Acceptance Criteria, Semantic Scope or Path Scope;
- modify baseline/canonical state without separate authority;
- self-approve;
- issue SEMANTIC_ACCEPTED;
- issue MERGE_ELIGIBLE;
- gain merge authority from capability;
- publish.

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


## Accepted TASK 01–09 semantic chain

The final package traces semantic acceptance, not obsolete historical checkpoints:

- TASK 01: `a863f099cd0adf9b62fc9185c990dddda614a795`
- TASK 02: `e57b4aa6cbca215fc162ae4a0d7aa8800e706dd5`
- TASK 03: `6e061a0793e039f3eccdc7514d7b89b62bbb747b`
- TASK 04: `1e594bfce5abbd9c2b13933aa13aa293b66a19d8`
- TASK 05: `018cecbb6446db682fd4061d1b03b7d81e3e5d64`
- TASK 06: `8d7038cf774db3aada3d48270b6d0077ef84e88d`
- TASK 07: `8ca5f3c9bc26484e2a26e1098afd475e6754169a`
- TASK 08: `e1013c3a629032e98a4169b8b58eca77edd84230`
- TASK 09: `c1fe4ba3e80dd5d9077188026fd1d1988fb066bc`

Historical checkpoints remain evidence only and do not supersede later exact-SHA Supervisor decisions.

## Historical correction record

The final package preserves, rather than erases, the accepted REWORK history:
- original TASK 09 at `9a0da69e4fd031e203080d165eb65b89a9de5c22` contained a confirmed false negative;
- original TASK 08 had a publication-authority weakening later classified as HARD VETO by Supervisor comment `5880275506`;
- TASK 08 was corrected and accepted at `e1013c3a629032e98a4169b8b58eca77edd84230`;
- TASK 09 was reworked to record the historical miss and re-audit the corrected chain;
- TASK 09 was accepted at `c1fe4ba3e80dd5d9077188026fd1d1988fb066bc`.

## Adoption boundary

This proposal is a presentation artifact only.

A future separately authorized Work Item is required to adopt or adapt any element as canonical.

No merge or canonical adoption is authorized by this package.
