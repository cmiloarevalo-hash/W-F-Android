# Android Candidate 3 — Verified

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent

Optimize for verification depth, security, auditability and persistent long-horizon execution.

## Control plane

GitHub Issue/Work Item is the durable control plane. Every material phase persists:
- objective and acceptance criteria;
- source/evidence ledger;
- environment/toolchain fingerprint;
- verification results;
- checkpoint commit;
- unresolved risks.

Technical capability never changes workflow authority.

## Tiered verification

### Tier 0 — deterministic setup
- verify expected JDK/Gradle/AGP/SDK inputs;
- dependency resolution within network policy;
- validate no production secrets are present in repository/build output.

### Tier 1 — every implementation checkpoint
- local/JVM unit tests;
- lint;
- relevant debug/release compilation;
- static analysis required by project.

### Tier 2 — UI/framework changes
- Compose UI or View/Espresso tests as applicable;
- selected instrumented tests on Gradle Managed Device/emulator;
- configuration-change/device behavior tests when relevant.

### Tier 3 — integration/high-risk changes
- multi-API/form-factor matrix;
- physical-device or remote-device testing when hardware/vendor behavior matters;
- optional Firebase Test Lab adapter with explicit quota/billing/auth authorization.

### Tier 4 — release candidate
- clean release build/AAB;
- artifact hash/provenance;
- signing performed only in protected release context;
- Play target/policy freshness check;
- no publication without explicit release authority.

## CI topology

```text
PR
├─ host lane: test + lint + build
├─ device lane: risk-selected managed emulator tests
└─ evidence aggregation
      ↓
review gate
      ↓
merge/release authority (outside Implementer self-approval)
```

Long-running or expensive device matrices can move to pre-release/nightly gates if the risk model justifies it; the decision must be explicit.

## Security model

- No release secrets in source.
- CI credentials are least-privilege and scoped to the exact external service.
- Network access is allowlisted/limited when supported.
- Host build and production release contexts are separated.
- Upload key and Play app-signing key are treated as distinct assets.
- External device providers receive test artifacts/credentials only as required.
- Logs/evidence are reviewed for accidental secret leakage.

## Auditability

Each checkpoint records:
- commit/ref;
- commands/tasks executed;
- toolchain versions;
- device/API matrix;
- test pass/fail/skip;
- retries/flaky-test handling;
- external provider used;
- artifact identifiers;
- unresolved warnings.

A retry never silently converts a failure into a pass; flaky behavior is recorded.

## Android-specific defaults

- Kotlin-first for greenfield.
- Compose preferred for new native UI where appropriate; existing Views remain supported.
- UDF/state-holder separation to maximize host-testable logic.
- Gradle wrapper as the reproducible automation entry point.
- Explicit Java toolchain.
- Lint as a blocking CI check.
- Device testing selected by change risk, not blindly on every supported API level.

## Optional external actor — Device/Google service operator

- CAPABILITY: execute an authorized device matrix in Firebase Test Lab or another provider.
- PRECONDITIONS: provider selected by Work Item, project/auth/billing authorized, artifacts and matrix defined.
- AUTHORIZED OPERATIONS: submit tests, monitor matrix, retrieve evidence.
- FORBIDDEN OPERATIONS: source edits, production data access, signing keys, Play rollout, provider/account changes.
- EXPECTED BASELINE: exact APK/test APK hashes, test runner, matrix definition.
- EVIDENCE RETURNED: provider matrix ID, device metadata, logs, screenshots/results, exit status.
- STOP CONDITIONS: unexpected billing requirement, missing authorization, unsupported device, provider instability that invalidates evidence.
- ESCALATION PATH: Supervisor/Human.

## Baseline functional non-regression ledger

Candidate 3 adds stronger verification/audit controls without replacing the baseline authority model. Its additional evidence is subordinate to the same semantic workflow guarantees.

| Baseline guarantee | Status | Preserved behavior in Candidate 3 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | The durable control plane records Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base, plus Android environment/audit metadata. Additional audit fields strengthen evidence but do not change the contract semantics. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Every audited operation must be authorized both semantically and by path. Device, CI, release, and external-provider capabilities cannot expand either scope. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Audit evidence records the exact commit SHA submitted for Supervisor semantic review. Any later commit creates a new HEAD whose semantic acceptance must be reviewed again, regardless of identical test outcomes. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor control states. Tiered tests, provenance, CI gates, device matrices, and audit logs are evidence and cannot auto-produce or replace a semantic state. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Same-objective corrections remain in the same Issue, branch, and PR, with new evidence/checkpoints appended to the audit trail. Changes to Objective, Semantic Scope, Path Scope, authority, baseline semantics, or other material contract terms require escalation. |
| 6. Supervisor-only merge and SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI, and external actors never self-merge. SEMANTIC_ACCEPTED applies only to the reviewed SHA and is distinct from MERGE_ELIGIBLE. Where integration is authorized, the Supervisor performs merge only after exact-SHA semantic acceptance and baseline merge-eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Strong release automation, signing isolation, artifact provenance, Play upload capability, or device-lab evidence do not create publication authority. Publication remains a Human action unless the Human explicitly changes the semantic rule. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | GitHub persists Work Item, branch/ref and exact HEAD, PR, environment fingerprint, verification evidence, latest applicable Supervisor decision/reviewed SHA, retries/deviations, and unresolved risks so a new authorized session reconstructs state without prior transcript. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | The audit pipeline must verify this ledger before scoring/recommendation. Any unexplained functional regression is a HARD VETO; stronger automation, deeper verification, or a higher analytical score cannot compensate for it. |

Candidate 3 strengthens auditability and verification depth while preserving the baseline workflow semantics and authority boundaries unchanged.

## Strengths

- Highest assurance and traceability.
- Explicit separation of ordinary build, device test and release security domains.
- Strong long-horizon recovery.
- Better fit for regulated/high-risk/team-scale work.

## Known weaknesses

- Highest CI and operational complexity.
- Device matrices can increase time/cost.
- More evidence artifacts and maintenance.
- Can be excessive for small/low-risk applications.

## Evidence basis

- Android test fundamentals: https://developer.android.com/training/testing/fundamentals
- Compose testing: https://developer.android.com/develop/ui/compose/testing
- Lint in CI: https://developer.android.com/studio/write/lint
- Emulator acceleration: https://developer.android.com/studio/run/emulator-commandline
- Firebase Test Lab: https://firebase.google.com/docs/test-lab/android/get-started
- Play App Signing: https://support.google.com/googleplay/android-developer/answer/9842756?hl=en
- Target API policy: https://developer.android.com/google/play/requirements/target-sdk
