# Android Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Risk-Tiered Portable Android Workflow

## Purpose
Provide a reproducible Android engineering workflow that keeps authority, verification, secrets and release controls explicit without requiring a specific CI vendor, coding-agent vendor or device-lab provider.

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
→ record acceptance criteria and environment contract
→ bounded implementation
→ host verification: relevant unit tests + lint + build
→ risk classifier
→ device/emulator evidence only when Android semantics require it
→ evidence bundle
→ exact-SHA independent review/checkpoint
→ merge only after separate merge-eligibility checks
→ publication only by Human action

## Environment contract
Record project-selected:
- Gradle wrapper and Android Gradle Plugin compatibility;
- JDK/toolchain;
- Android SDK / compile / target / min SDK;
- Kotlin and UI stack versions;
- deterministic build/test/lint commands;
- network/dependency policy.

Versions are project facts and time-scoped evidence, not permanent workflow constants.

## Architecture guidance
For greenfield native Android, use current Android recommendations as the starting point:
- Kotlin-first;
- Compose for new UI where appropriate;
- unidirectional state flow and host-testable domain/data logic.

Existing Java/View projects are valid; this proposal does not require migration solely for workflow compliance.

## Verification tiers
Base checkpoint:
- relevant local/JVM tests;
- Android lint;
- affected compile/assemble/build task.

Add device evidence when changes affect UI/framework behavior, lifecycle, permissions, services, persistence semantics, hardware, vendor behavior, API/form-factor compatibility or release-critical journeys.

Host build capability MUST NOT be treated as emulator/device capability.

## Device adapter
Permitted implementations include:
- attached physical device;
- local emulator / Gradle Managed Device;
- authorized virtualized cloud runner;
- Firebase Test Lab;
- another authorized device farm.

Firebase is optional.

Adapter evidence includes artifact hashes, device/API metadata, test selection, pass/fail/skip, logs/reports and retries.

## Security / signing / publication boundary
Ordinary implementation/test contexts do not receive production signing authority by default.

Technical pre-publication work may include:
- current Google Play / target API / account policy freshness check;
- identified AAB/release artifact;
- protected signing material under explicit authority;
- retained artifact/signing evidence.

Publication invariant:

`PUBLISH = HUMAN ACTION`

Build/sign/upload/deploy capability, credentials, store roles or an ordinary Work Item permission do not transfer publication authority to Implementer, CI or an external actor.

## Optional external actor
Extension point: Android device-test, signing-support or pre-publication technical operator.

Contract:
- CAPABILITY: exact device/build/signing/pre-publication technical capability.
- PRECONDITIONS: authorized provider/account, artifact hashes, matrix, quota/cost authorization if applicable.
- AUTHORIZED OPERATIONS: only the named technical run/retrieve/build/sign/stage operation.
- FORBIDDEN OPERATIONS: unrelated source changes, scope/authority changes, baseline changes, self-approval, merge, semantic decisions and production publication.
- EXPECTED BASELINE: governing Work Item + exact ref/SHA + artifact hashes + configuration.
- EVIDENCE RETURNED: run ID, device metadata, reports/logs, status.
- STOP CONDITIONS: missing authority/credential/budget, inconsistent artifact, unsupported environment, scope contradiction or attempted publication.
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
A concrete Android project must still decide:
- supported API/form-factor/device matrix;
- CI provider and emulator/device availability;
- whether/which remote device lab is authorized;
- signing custody;
- allowed cost/quota for broad matrices;
- exact publication channels and the Human publication action.

## Platform delta preserved
Android remains distinct through Gradle/JDK/Android SDK, emulator/physical-device evidence, Android signing, APK/AAB artifacts and store-specific distribution. No iOS/Web symmetry is imposed.

## Evidence
Detailed basis:
- outputs/02/android-evidence.md
- outputs/03/android-comparison.md
- outputs/03/android-sensitivity.md
- outputs/08/platform-deltas.md
- outputs/09/contradiction-audit.md
- outputs/09/source-freshness-audit.md
