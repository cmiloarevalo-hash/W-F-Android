# TASK 09 — Semantic propagation risks

STATUS: RE-AUDITED — HISTORICAL MISS PRESERVED

## Historical propagation failure

The original TASK 09 risk assessment was too strong when it marked publication/release authority as contained.

The original TASK 08 external-actor wording allowed production release to be read as permitted when the Work Item explicitly granted it. Supervisor comment `5880275506` later classified that weakening as a **PUBLICATION AUTHORITY — HARD VETO** because the governing rule is:

`PUBLISH = HUMAN ACTION`

Therefore the historical TASK 09 audit contained a false negative. The risk register below records both the miss and the accepted correction rather than rewriting history.

## Current risk register

| Risk | Propagation path tested | Historical status | Current post-REWORK status | Required control |
|---|---|---|---|---|
| Technical capability becomes Workflow authority | TASK 01 → platform proposals → Common Core/external actor | Conceptually contained | CONTAINED / VERIFIED | Preserve `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`; no technical permission creates semantic, merge or publication authority. |
| Publication/release capability becomes publication authority | platform release models → original TASK 08 actor interface | **MISSED — FALSE NEGATIVE** | **CORRECTED / CONTAINED** | `PUBLISH = HUMAN ACTION`; technical actor cannot publish, even with deploy/sign/upload capability or ordinary Work Item technical permission. |
| External actor invocation lacks durable authority/evidence record | platform actor adapters → Common Core | NOT AUDITED | CONTAINED / VERIFIED | Apply Issue #2 comment `5879863384` to every invocation; persist the complete activity record in GitHub. |
| Workpack API-only access becomes universal workflow rule | repository contract → Candidate 4/Common Core | CONTAINED | CONTAINED | Keep Workpack execution restriction local to this Workpack. |
| Baseline AI_STUDIO_OPERATOR becomes universal external actor | baseline → platform proposals → Common Core | CONTAINED | CONTAINED | External actor remains optional, capability-specific and provider-neutral. |
| Firebase becomes Android/core dependency | Android evidence → Candidate 4 → Common Core | CONTAINED | CONTAINED | Keep Firebase/Test Lab optional. |
| Xcode Cloud becomes iOS/core dependency | iOS evidence → Candidate 4 → Common Core | CONTAINED | CONTAINED | Keep Xcode Cloud optional while preserving unavoidable macOS/Xcode native boundary. |
| npm/framework/host becomes Web/core dependency | Web evidence → Candidate 4 → Common Core | CONTAINED | CONTAINED | Use project-native adapters; no mandatory framework/package manager/host. |
| Host build implies device/simulator support | platform candidates → Common Core | CONTAINED | CONTAINED | Preserve platform verification adapters and capability boundaries. |
| Simulator/emulator/browser automation treated as complete real-world equivalence | platform verification → final proposal | CONTAINED | CONTAINED | Risk-trigger physical-device/human/real-environment evidence. |
| CI/test success becomes approval | all tasks | CONTAINED | CONTAINED | Evidence != approval; exact-SHA Supervisor state machine remains mandatory. |
| Score overrides baseline eligibility | comparisons → synthesis | Partially tested | CONTAINED / VERIFIED | Nine-guarantee gate + HARD VETO precedes scoring; score cannot restore eligibility. |
| Current versions become permanent workflow constants | evidence → Candidate 4 → presentation | CONTAINED | CONTAINED | Date/version scope + release-time freshness checks. |
| Common-core abstraction erases Android/iOS/Web constraints | TASK 08 → TASK 10 | CONTAINED | CONTAINED | Preserve `platform-deltas.md` and non-symmetry rules. |
| Historical checkpoint mistaken for accepted SHA | sequential REWORK history → later audit | NOT EXPLICITLY CONTROLLED | CONTAINED IN RE-AUDIT | Trace original checkpoint, REWORK correction and final SEMANTIC_ACCEPTED SHA separately. |
| Durable activity record mistaken for authority | comment 5879863384 → external actor execution | NOT AUDITED | CONTAINED / VERIFIED | Activity is evidence/continuity only; authority remains with governing Workflow/Work Item/Supervisor/Human boundaries. |

## Durable external-actor activity control

Every invocation must persist under the governing Work Item:
- ACTIVITY_ID / reference;
- GOVERNING_WORK_ITEM;
- ACTOR_TYPE;
- CAPABILITY;
- OBJECTIVE;
- PRECONDITIONS;
- AUTHORIZED_OPERATIONS;
- FORBIDDEN_OPERATIONS;
- EXPECTED_BASELINE / exact ref or SHA;
- EVIDENCE_REQUIRED;
- RESULT / evidence returned;
- STOP_CONDITIONS;
- ESCALATION_PATH;
- STATUS / closure state.

Required reconstruction:
`request → authority → execution → evidence → result → stop/escalation`

The activity record cannot modify Workflow, Objective, Acceptance Criteria, Semantic Scope, Path Scope, baseline/canonical state, semantic decision, merge authority or publication authority.

## Highest residual risks for TASK 10

1. Presentation compression could omit the nine-guarantee/HARD-VETO eligibility contract.
2. Publication language could regress from `PUBLISH = HUMAN ACTION` to a weaker “separately authorized technical release” phrase.
3. “Capability” wording could again be interpreted as Workflow authority.
4. External-actor summaries could omit durable GitHub activity requirements or mistake the activity record for authority.
5. Cross-platform wording could erase Android/iOS/Web execution, signing or distribution differences.
6. Original checkpoint SHAs could be presented as accepted state instead of the final reviewed REWORK SHAs.
7. Analytical score headlines could obscure eligibility and sensitivity.

## TASK 10 controls

Any final package must:
- remain PROPOSAL — NOT CANONICAL;
- preserve all nine guarantees and HARD VETO ordering;
- state `PUBLISH = HUMAN ACTION`;
- state `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`;
- retain the durable external-actor activity requirement from `5879863384`;
- preserve explicit Android/iOS/Web platform deltas;
- use final SEMANTIC_ACCEPTED SHAs when describing accepted task state;
- retain analytical-score labels and sensitivity context;
- keep volatile platform/version claims subject to freshness checks.

This file does not authorize TASK 10 execution or adoption.
