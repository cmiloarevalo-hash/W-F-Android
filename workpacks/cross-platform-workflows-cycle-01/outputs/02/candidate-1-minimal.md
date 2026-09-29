# Android Candidate 1 — Minimal

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent

Minimize operational complexity while preserving the Workpack invariants and a credible Android verification floor.

## Actors

- Human: product/release decisions and exceptional permissions.
- Supervisor: scope/evidence review.
- Implementer: code/research work within authorized scope.
- GitHub: authority, durable state and review surface.
- CI: deterministic build/test/lint evidence.
- External actor: **none by default**.

## Core workflow

```text
ISSUE / TASK
→ reconstruct minimal repo context
→ plan change
→ implement in bounded branch/scope
→ ./gradlew test
→ ./gradlew lint
→ relevant assemble/build task
→ targeted instrumented/UI test only when change risk requires it
→ review diff + evidence
→ checkpoint / PR
→ human/Supervisor review
```

## Toolchain contract

For a concrete app:
- use the repository Gradle wrapper;
- pin AGP/Kotlin/Compose/dependency versions in repository configuration;
- declare/verify the Java toolchain;
- install the Android SDK components required by compileSdk/build tools;
- prefer stable toolchain versions compatible with the repository.

Current reference point (not a permanent pin): AGP 9.4.0 release notes list Gradle 9.6.0 and JDK 17 compatibility and support API 37.

## Verification policy

Default PR/change gate:
1. local/unit tests relevant to changed code;
2. Android lint;
3. compile/assemble relevant variant;
4. targeted UI/instrumented test when the change crosses Android framework/UI boundaries.

A full emulator/API/device matrix is not a default requirement.

## Sandbox model

### Local or cloud host sandbox
Allowed capabilities:
- Gradle sync/dependency resolution as authorized;
- compile/build;
- JVM tests;
- lint;
- artifact creation without production secrets.

### Device testing
Use an available emulator/device only when required. Do not assume a generic container can run an accelerated emulator.

## Release boundary

Implementation stops before production publication unless separately authorized.

Release requires:
- current Play target/policy check;
- release artifact;
- protected upload/signing material;
- human/authorized release action.

Production keystore passwords/private material never enter source files.

## Context recovery

Keep only:
- active Issue/task;
- concise repository instructions;
- build/test commands;
- checkpoint/evidence summary.

Avoid adding elaborate workflow documents unless the project demonstrates a need.

## Optional external actor

None by default.

If device testing cannot be performed by the Implementer environment, an optional device-test operator may be added only with:

- CAPABILITY: execute provided APK/test APK on specified emulator/device.
- PRECONDITIONS: exact artifacts + test matrix + authorization.
- AUTHORIZED OPERATIONS: run tests and return reports.
- FORBIDDEN OPERATIONS: source edits, signing, Play publication, scope changes.
- EXPECTED BASELINE: artifact hashes + declared test configuration.
- EVIDENCE RETURNED: result bundle/logs/device metadata.
- STOP CONDITIONS: unavailable device, auth/cost requirement, inconsistent artifact.
- ESCALATION PATH: Supervisor/Human.

## Baseline functional non-regression ledger

This Candidate 1 remains the minimal Android workflow, but minimality does not remove baseline control functions. The following guarantees are mandatory eligibility conditions before any scoring or recommendation.

| Baseline guarantee | Status | Preserved behavior in Candidate 1 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Android task is governed by one Work Item that explicitly records Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Android-specific build/test details populate the contract but do not replace it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes the intended behavior/change and Path Scope authorizes the files/modules. Both must pass independently; permission to edit a path never authorizes an unrelated semantic change. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review is bound to the exact reviewed commit SHA. Any new commit creates a new HEAD and requires a new semantic decision for that HEAD. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Unit tests, lint, build, emulator/device checks, or CI success are evidence only and cannot substitute for the Supervisor decision. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections that keep the same Objective continue in the same Issue, branch, and PR. If Objective, Semantic Scope, Path Scope, authority, or another material contract element changes, the work escalates instead of silently stretching the existing Work Item. |
| 6. Supervisor-only merge and SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer never self-merges. SEMANTIC_ACCEPTED applies only to the reviewed SHA and is not itself MERGE_ELIGIBLE. Where merge is authorized, the Supervisor verifies the exact accepted SHA plus the baseline integration/eligibility conditions before merging. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Android build, signing, AAB generation, upload capability, Play Console access, or release automation do not create publication authority. Publication remains a Human action unless the Human explicitly changes that semantic rule. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | A new Supervisor or Implementer session reconstructs from GitHub artifacts: governing Issue/Work Item, branch/ref and exact HEAD, active PR, latest applicable Supervisor decision and reviewed SHA, checkpoint/evidence, and unresolved blockers. Prior chat transcript is not authoritative continuity. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | Before Candidate 1 is eligible for scoring or recommendation, this ledger must be complete and any unexplained loss, weakening, substitution, or reinterpretation of a protected baseline function is a HARD VETO that score cannot offset. |

Candidate 1 preserves these controls with the smallest operational ceremony; it does not weaken them to achieve minimality.

## Strengths

- Small cognitive and operational surface.
- Low provider lock-in.
- Fast default loop.
- Easy to adopt in small teams/repositories.

## Known weaknesses

- Less systematic device coverage.
- Less structured long-horizon evidence.
- Greater reliance on risk judgment to decide when instrumented/device testing is needed.
- Release/audit automation intentionally limited.

## Evidence basis

- Kotlin-first: https://developer.android.com/kotlin/first
- Android architecture/UDF: https://developer.android.com/topic/architecture/ui-layer
- Local vs instrumented testing: https://developer.android.com/training/testing/fundamentals
- Gradle test commands: https://developer.android.com/studio/test/command-line
- Lint in CI: https://developer.android.com/studio/write/lint
- Signing boundary: https://developer.android.com/build/build-variants
