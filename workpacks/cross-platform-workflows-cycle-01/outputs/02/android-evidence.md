# TASK 02 — Android evidence

Status: EXPERIMENTAL RESEARCH — NOT CANONICAL  
Work Item: Issue #2  
Access date for external sources: 2026-09-27

## Scope

Android-specific evidence used to design Candidates 1–3. This file does not modify the frozen workflow baseline and does not select a preferred candidate.

## Claim ledger

| ID | Claim | Class | Evidence | Confidence / notes |
|---|---|---|---|---|
| A-01 | Android development remains Kotlin-first; Google recommends starting new Android apps with Kotlin. | EXTERNAL_FACT | https://developer.android.com/kotlin/first | HIGH |
| A-02 | Jetpack Compose is the recommended/preferred UI toolkit for modern Android UI, while Views remain supported. | EXTERNAL_FACT | https://developer.android.com/topic/architecture/ui-layer ; https://developer.android.com/distribute/aep/aep-req-jetpack-compose | HIGH; candidate workflows must not assume every existing app is Compose-only |
| A-03 | Android architecture guidance emphasizes UI/data separation, screen-level state holders such as ViewModel, and unidirectional data flow for testability/maintainability. | EXTERNAL_FACT | https://developer.android.com/topic/architecture/ui-layer ; https://developer.android.com/develop/ui/compose/architecture | HIGH |
| A-04 | AGP 9.4.0 is a September 2026 release; its compatibility table lists Gradle 9.6.0 and JDK 17, and supports API level 37. | EXTERNAL_FACT | https://developer.android.com/build/releases/agp-9-4-0-release-notes | HIGH; version-sensitive and must be rechecked when applied to a real repository |
| A-05 | Android recommends explicitly specifying the Java toolchain to make builds more consistent across machines/CI. | EXTERNAL_FACT | https://developer.android.com/build/jdks | HIGH |
| A-06 | Compose BOM is the recommended mechanism for aligning stable Compose library versions; current example uses BOM 2026.09.00. | EXTERNAL_FACT | https://developer.android.com/develop/ui/compose/bom | HIGH; current version is volatile |
| A-07 | Android local tests run on the development machine/server and are generally small/fast; instrumented tests run on physical/emulated Android devices. | EXTERNAL_FACT | https://developer.android.com/training/testing/fundamentals | HIGH |
| A-08 | Android Gradle supports `./gradlew test` for local tests and `./gradlew connectedAndroidTest` for connected instrumented tests. | EXTERNAL_FACT | https://developer.android.com/studio/test/command-line | HIGH |
| A-09 | Android lint is not automatically run as part of every build; Android explicitly recommends running lint in CI. | EXTERNAL_FACT | https://developer.android.com/studio/write/lint | HIGH |
| A-10 | Compose provides dedicated UI test APIs; Android guidance also recommends instrumented testing and CI integration. | EXTERNAL_FACT | https://developer.android.com/develop/ui/compose/testing | HIGH |
| A-11 | Gradle Managed Devices are an Android-supported mechanism for automated virtual-device testing; device-level tests remain materially heavier than host-side tests. | EXTERNAL_FACT / INFERENCE | https://developer.android.com/studio/test/command-line ; https://developer.android.com/reference/tools/gradle-api/9.5/com/android/build/api/dsl/TestOptions | HIGH for capability; "heavier" is an inference from device requirement |
| A-12 | Android Emulator acceleration for x86/x86_64 relies on a usable hypervisor (for example KVM on Linux). | EXTERNAL_FACT | https://developer.android.com/studio/run/emulator-commandline | HIGH; therefore cloud/container execution must verify virtualization rather than assume it |
| A-13 | Firebase Test Lab can run Android instrumentation tests on remote virtual/physical devices and supports scripted/CI invocation through gcloud. | EXTERNAL_FACT | https://firebase.google.com/docs/test-lab/android/get-started ; https://firebase.google.com/docs/test-lab/android/command-line | HIGH |
| A-14 | Firebase/Test Lab is optional infrastructure with project/auth/quota/billing considerations; it is not a prerequisite for Android development. | EXTERNAL_FACT / INFERENCE | https://firebase.google.com/docs/test-lab/android/firebase-console ; https://firebase.google.com/docs/test-lab/android/command-line | HIGH that project/auth are required for those paths; optionality is architectural inference |
| A-15 | The Android build system produces APK/AAB artifacts; release signing is a separate concern and credentials should not be embedded in build files. | EXTERNAL_FACT | https://developer.android.com/build ; https://developer.android.com/build/build-variants | HIGH |
| A-16 | New Google Play apps use Android App Bundles; Play App Signing separates upload key from the app-signing key and the upload key must remain protected. | EXTERNAL_FACT | https://developer.android.com/build ; https://support.google.com/googleplay/android-developer/answer/9842756?hl=en | HIGH |
| A-17 | From 2026-08-31, new apps and updates submitted to Google Play generally must target Android 16 / API 36+, with documented form-factor exceptions. | EXTERNAL_FACT | https://developer.android.com/google/play/requirements/target-sdk | HIGH; release-policy claim must be rechecked before publication |
| A-18 | Play package-name registration has a future effective date of 2026-09-30; on this research date (2026-09-27), it is an imminent requirement rather than one already in force. | EXTERNAL_FACT | https://support.google.com/googleplay/android-developer/answer/16984799?hl=en | HIGH; date-sensitive |
| A-19 | Community reports indicate large emulator/API matrices can create CI time/storage/cost friction. | COMMUNITY_EVIDENCE | https://www.reddit.com/r/androiddev/comments/1giq5y8 | LOW/MEDIUM; anecdotal, used only as operational-friction evidence |
| A-20 | A 2026 community report describes reducing flakiness by moving logic into host-testable code and minimizing emulator dependence. | COMMUNITY_EVIDENCE | https://www.reddit.com/r/AndroidTesting/comments/1upxhmr/my_tests_were_a_mess_for_years_going/ | LOW; single experience report, not a platform fact |

## Build/toolchain implications

1. **Pin and verify rather than chase "latest".** A real repository should pin the Gradle wrapper, AGP, JDK/toolchain and relevant Kotlin/Compose dependencies. Compatibility must be checked from current official tables.
2. **Do not conflate IDE with build authority.** Android Studio is useful, but the Gradle wrapper and documented build/test tasks provide a more reproducible automation surface.
3. **Prefer stable dependencies for workflow baselines.** Alpha/beta toolchains may be tested experimentally but should not silently become the default workflow requirement.
4. **Architecture affects test economics.** Keeping business/state logic outside Android UI/framework surfaces increases the portion that can run as fast host-side tests.

## Verification ladder

A portable Android workflow can expose increasing assurance:

1. static/config checks;
2. local unit tests;
3. lint;
4. debug/release compilation or assembly as appropriate;
5. Compose/View UI tests where applicable;
6. instrumented tests on emulator/device;
7. selected device/API matrix;
8. release artifact/signing validation;
9. Play policy/release checks immediately before publication.

Not every task needs every rung. The workflow should select the smallest verification set that proves the requested change, while preserving mandatory project/release gates.

## Local and cloud execution boundary

### Host-side sandbox
Suitable when provisioned with:
- compatible JDK;
- Android SDK/Build Tools;
- Gradle wrapper/dependency access;
- writable build/cache paths as authorized.

Good targets:
- compilation;
- local JVM tests;
- lint;
- many static analyses;
- AAB/APK generation without production secrets.

### Device-capable sandbox
Instrumented/UI tests need:
- emulator plus virtualization/hypervisor support, or
- attached physical device, or
- remote device-lab integration.

Therefore "cloud sandbox supports Android" must be decomposed into:
- can build host-side?
- can run accelerated emulator?
- can reach an authorized remote device lab?
- can safely handle test credentials?

## Signing and Play boundary

- Debug signing is not release signing.
- Release/upload keys are secrets and must not live in source or plaintext build configuration.
- Play App Signing means the upload key and app-signing key are distinct concepts.
- Publication, Play Console actions, identity/account requirements, production rollout and policy acceptance remain human/authorized release boundaries unless explicitly delegated by a Work Item.
- Release policy is volatile; target API and developer-verification requirements must be rechecked at release time.

## Firebase / Google Cloud optionality

Firebase Test Lab is useful for broad device coverage but is not a mandatory core dependency. A portable workflow should expose a provider-neutral "device test provider" interface and allow:
- local emulator / Gradle Managed Device;
- attached device;
- Firebase Test Lab;
- another authorized device farm.

If Firebase is selected, its project, billing/quota, credentials and data handling must be explicitly authorized.

## Evidence-driven candidate separation

- Candidate 1 will minimize operational surfaces and external dependencies.
- Candidate 2 will define provider-neutral execution contracts and durable context.
- Candidate 3 will add stronger CI/device-matrix/security/audit gates and optional cloud device testing.

This is a structural separation, not a cosmetic rename.
