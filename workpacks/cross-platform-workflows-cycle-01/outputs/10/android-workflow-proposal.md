# Android Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Risk-Tiered Portable Android Workflow

## Purpose
Provide a reproducible Android engineering workflow that keeps authority, verification, secrets and release controls explicit without requiring a specific CI vendor, coding-agent vendor or device-lab provider.

## Core flow

AUTHORIZED WORK ITEM
→ reconstruct minimal durable context
→ record acceptance criteria and environment contract
→ bounded implementation
→ host verification: relevant unit tests + lint + build
→ risk classifier
→ device/emulator evidence only when Android semantics require it
→ evidence bundle
→ independent review/checkpoint
→ separately authorized merge/release

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

## Security/release boundary
Ordinary implementation/test contexts do not receive production signing authority by default.

Release requires:
- current Google Play / target API / account policy freshness check;
- identified AAB/release artifact;
- protected upload/signing material;
- explicit release authority;
- retained artifact/signing evidence.

Build/sign capability does not grant Play rollout authority.

## Optional external actor
Extension point: Android device-test or release operator.

Contract:
- CAPABILITY: exact device/release capability.
- PRECONDITIONS: authorized provider/account, artifact hashes, matrix, quota/cost authorization if applicable.
- AUTHORIZED OPERATIONS: only the named run/retrieve/release operation.
- FORBIDDEN OPERATIONS: unrelated source changes, scope/authority changes, baseline changes, unapproved publication.
- EXPECTED BASELINE: ref + artifact hashes + configuration.
- EVIDENCE RETURNED: run ID, device metadata, reports/logs, status.
- STOP CONDITIONS: missing authorization/credential/budget, inconsistent artifact, unsupported environment.
- ESCALATION PATH: Supervisor/Human.

## Unresolved human decisions
A concrete Android project must still decide:
- supported API/form-factor/device matrix;
- CI provider and emulator/device availability;
- whether/which remote device lab is authorized;
- signing custody and release operator;
- allowed cost/quota for broad matrices;
- exact release channels.

## Evidence
Detailed basis:
- outputs/02/android-evidence.md
- outputs/03/android-comparison.md
- outputs/03/android-sensitivity.md
- outputs/09/source-freshness-audit.md
