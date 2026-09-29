# TASK 08 — Cross-platform evidence map

STATUS: EXPERIMENTAL TRACEABILITY MAP

## Common-core evidence

| Common rule | Android basis | iOS basis | Web basis | Cross-platform classification |
|---|---|---|---|---|
| Work Item defines authority | outputs/03 Candidate 4 governance + ledger | outputs/05 Candidate 4 governance + ledger | outputs/07 Candidate 4 governance + ledger | PROJECT FACT / INVARIANT |
| Durable repo state | outputs/01 invariants I-05/I-19/I-28 | same | same | PROJECT FACT + governance |
| Environment contract | Android A-04/A-05/A-06 | iOS I-01/I-02/I-04 | web W-08 + project-native adapter | INFERENCE from verified facts |
| Tiered verification | A-07..A-13 | I-03..I-05 | W-01..W-03/W-07 | RECOMMENDATION supported by facts |
| CI evidence != approval | invariants I-11/I-13/I-24 | same | same | PROJECT FACT / GOVERNANCE |
| Secrets/release separation | A-15..A-18 | I-06..I-10 | W-04..W-06 | VERIFIED EXTERNAL FACT + recommendation |
| External actor optional | Android Candidate 4 | iOS Candidate 4 | web Candidate 4 | RECOMMENDATION constrained by I-17 |
| Durable external-actor activity | Issue #2 comment 5879863384 + I-05/I-17 | same | same | PROJECT FACT / GOVERNANCE INPUT |
| TECHNICAL CAPABILITY != WORKFLOW AUTHORITY | invariants I-01/I-02/I-13 + baseline §31 | same | same | PROJECT FACT / GOVERNANCE |
| PUBLISH = HUMAN ACTION | invariants I-27 + baseline publication rule | same | same | PROJECT FACT / HARD AUTHORITY BOUNDARY |
| Provider-specific service optional | Firebase/Test Lab optional | Xcode Cloud optional | hosting/framework optional | RECOMMENDATION |
| Platform-specific verification adapter | device/emulator | simulator/device/Mac | browser/E2E/preview | VERIFIED platform delta |
| Proposal remains non-canonical | Issue #2 / invariants I-14 | same | same | PROJECT FACT |

## Nine-guarantee baseline trace

| # | Protected guarantee | TASK 01 basis | Android accepted basis | iOS accepted basis | Web accepted basis | Common Core result |
|---:|---|---|---|---|---|---|
| 1 | Work Item contract: Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, Base | I-21 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION |
| 2 | Semantic Scope + Path Scope independently enforced | I-22 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 3 | Exact-SHA Supervisor semantic review; new commit invalidates acceptance for new HEAD | I-23 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 4 | SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | I-24 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 5 | Same-objective REWORK continuity in same Issue/branch/PR; material scope/authority change escalates | I-25 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 6 | Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | I-26 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 7 | PUBLISH = HUMAN ACTION | I-27 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |
| 8 | GitHub recovery: Issue, ref/HEAD, PR, latest Supervisor decision/reviewed SHA, checkpoint/evidence, unresolved states | I-28 | outputs/03 Candidate 4 recovery/ledger | outputs/05 Candidate 4 recovery/ledger | outputs/07 Candidate 4 recovery/ledger | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION |
| 9 | Baseline functional non-regression gate / HARD VETO | I-29 | outputs/03 Candidate 4 ledger | outputs/05 Candidate 4 ledger | outputs/07 Candidate 4 ledger | PRESERVED AS-IS |

## External actor durable-activity trace

Source authority:
- Issue #2 comment `5879863384` — SUPERVISOR WORKFLOW RULE — EXTERNAL ACTOR ACTIVITY RECORD.
- TASK 01 I-17 — bounded external actor contract.
- TASK 01 I-05/I-28 — durable GitHub continuity/recovery.

TASK 08 preservation:
- contract remains capability-specific and provider-neutral;
- every invocation is persisted under the governing GitHub Work Item;
- activity fields include ACTIVITY_ID/reference, GOVERNING_WORK_ITEM, ACTOR_TYPE, CAPABILITY, OBJECTIVE, PRECONDITIONS, AUTHORIZED_OPERATIONS, FORBIDDEN_OPERATIONS, EXPECTED_BASELINE/ref/SHA, EVIDENCE_REQUIRED, RESULT, STOP_CONDITIONS, ESCALATION_PATH and STATUS;
- reconstruction lifecycle is `request → authority → execution → evidence → result → stop/escalation`;
- the activity record is evidence, never a new source of authority;
- no public-standard AIFUE semantics are assumed.

## Platform differences preserved

TASK 08 Common Core does not replace `outputs/08/platform-deltas.md`.

The following remain intentionally different:
- Android: Gradle/JDK/Android SDK, emulator/physical-device constraints, Android signing and APK/AAB/store distribution.
- iOS: macOS/Xcode boundary, simulator vs physical device, Apple signing/provisioning, TestFlight/App Store and unavoidable Apple coupling.
- Web: project-selected runtime/build system, browser/E2E matrix, frontend/backend/secrets boundary, provider-specific deployment and no universal mobile-style signing gate.

No Firebase, Xcode Cloud, Playwright, package manager, CI provider, hosting provider, device matrix or distribution model is made mandatory merely for symmetry.

## Source families
- TASK 01 governance: `outputs/01/invariants.md`.
- OpenAI current agent guidance: `outputs/01/source-register.md`.
- Android official evidence: `outputs/02/android-evidence.md`.
- Android accepted synthesis: `outputs/03/android-candidate-4-presentation.md`.
- iOS official evidence: `outputs/04/ios-evidence.md`.
- iOS accepted synthesis: `outputs/05/ios-candidate-4-presentation.md`.
- Web standards/tooling evidence: `outputs/06/web-evidence.md`.
- Web accepted synthesis: `outputs/07/web-candidate-4-presentation.md`.
- External-actor activity governance input: Issue #2 comment `5879863384`.

## Conclusion

The common core is governance/evidence-oriented and explicitly preserves the nine baseline guarantees. Build, test surface, device/browser execution, signing and distribution remain platform deltas.

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`

`PUBLISH = HUMAN ACTION`
