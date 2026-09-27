# Android Candidate 2 — Portable

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent

Maximize provider independence, reproducibility and context recovery while keeping Android-specific device/release requirements explicit.

## Architecture

The workflow is split into provider-neutral contracts:

```text
TASK CONTRACT
→ HOST BUILD ADAPTER
→ VERIFICATION ADAPTERS
→ DEVICE TEST ADAPTER (optional per change)
→ EVIDENCE BUNDLE
→ REVIEW GATE
→ RELEASE ADAPTER (separately authorized)
```

The contracts are stored as repository documentation/scripts/config, while the backing provider can change.

## Host build adapter

Required inputs:
- repository ref;
- JDK/toolchain version;
- Android SDK/compileSdk/build-tools requirements;
- Gradle wrapper;
- dependency/network policy.

Required outputs:
- build result;
- unit-test result;
- lint result;
- generated artifact hashes/paths where applicable.

Provider choices may include a developer workstation, self-hosted sandbox, or cloud CI runner, provided the environment contract is satisfied.

## Device test adapter

Common interface:
- app/test artifacts;
- device model/API/ABI/form factor;
- test selection;
- timeout/retry policy;
- evidence output.

Possible implementations:
- local emulator;
- Gradle Managed Device;
- attached physical device;
- Firebase Test Lab;
- another authorized device farm.

The workflow does not make Firebase mandatory.

## Test strategy

Base gate:
- `./gradlew test`
- `./gradlew lint`
- relevant assemble/build task.

Risk-driven gate:
- Compose/View UI tests for changed UI behavior;
- instrumented tests for framework/device integration;
- device/API matrix for compatibility-sensitive changes.

Nightly/pre-release matrices may be broader than per-PR matrices to contain cost/time.

## Toolchain portability

- Pin Gradle wrapper.
- Pin/record AGP and dependency versions.
- Explicit Java toolchain.
- Prefer repository-owned deterministic commands over IDE-only operations.
- Keep provider secrets/config outside core build logic.
- Treat current AGP/Kotlin/Compose versions as mutable evidence, not permanent workflow assumptions.

## Durable context

Persist:
- task specification and acceptance criteria;
- current state/checkpoint;
- environment contract;
- evidence ledger;
- unresolved decisions;
- source freshness metadata.

A new authorized agent should be able to continue without chat transcript.

## Release adapter

Release is separate from ordinary implementation.

Interface:
- unsigned/release-ready AAB input;
- authorized signing/upload mechanism;
- Play policy freshness check;
- protected credentials;
- publication target/track;
- returned release evidence.

Default state is manual/disabled unless a Work Item explicitly authorizes release actions.

## Optional external actor

A device-lab or release operator can be attached without changing core workflow:

- CAPABILITY: device test or authorized release operation.
- PRECONDITIONS: explicit artifacts, credentials/permissions and task authorization.
- AUTHORIZED OPERATIONS: only named adapter operation.
- FORBIDDEN OPERATIONS: source changes, authority/scope changes, unrelated cloud actions.
- EXPECTED BASELINE: artifact hashes/config/ref.
- EVIDENCE RETURNED: machine-readable result plus provider metadata.
- STOP CONDITIONS: billing/credential/policy changes, unsupported matrix, inconsistent artifact.
- ESCALATION PATH: Supervisor/Human.

## Strengths

- High provider portability.
- Strong session/agent recovery.
- Separates host builds, device tests and release concerns.
- Firebase/Google Cloud remain optional adapters.

## Known weaknesses

- More design/documentation than Candidate 1.
- Adapter abstraction can become overengineering for a very small project.
- Provider differences (device catalogs, artifacts, retry semantics) cannot be fully abstracted.

## Evidence basis

- Java toolchain consistency: https://developer.android.com/build/jdks
- Gradle test automation: https://developer.android.com/studio/test/command-line
- Emulator acceleration constraints: https://developer.android.com/studio/run/emulator-commandline
- Firebase Test Lab scripted tests: https://firebase.google.com/docs/test-lab/android/command-line
- Play/signing boundary: https://support.google.com/googleplay/android-developer/answer/9842756?hl=en
