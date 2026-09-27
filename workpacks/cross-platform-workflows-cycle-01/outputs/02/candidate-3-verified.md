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
