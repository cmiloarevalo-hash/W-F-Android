# SUPERVISOR REVIEW PACKET — Android

STATUS: READY_FOR INDEPENDENT SUPERVISOR REVIEW  
Proposal: `outputs/03/android-candidate-4-presentation.md`  
This packet is not self-approval.

## 1. Material assumptions

1. Most Android changes can be meaningfully separated into host-verifiable work and device-dependent work.
2. A project can maintain a risk classifier that decides when device evidence is required.
3. Gradle wrapper + pinned toolchain metadata are a sufficiently portable automation surface for the core build/test loop.
4. Provider-neutral device-test contracts are useful despite provider-specific differences in catalogs, retries and artifacts.
5. Production signing/Play release should remain a distinct security/authority domain.
6. Firebase Test Lab is optional; physical/device coverage may be supplied by another authorized provider.
7. A concise durable repository/task record is preferable to accumulating all historical context in every agent prompt.

## 2. Trade-offs

### Assurance vs operational cost
Candidate 3 provides strongest default assurance but risks excessive device/runtime cost and ceremony. Candidate 4 keeps its tiered controls but makes the device tier risk-triggered.

### Portability vs abstraction cost
Candidate 2's adapter model lowers provider lock-in but adds schemas/contracts. Candidate 4 limits adapters to host, device and release boundaries rather than abstracting every tool.

### Simplicity vs traceability
Candidate 1 is easiest to operate. Candidate 4 retains its small host loop but requires structured evidence for higher-risk paths.

## 3. Unresolved issues

- No empirical CI duration/cost measurements exist for a concrete Android repository.
- No concrete device/API matrix can be chosen without app minSdk/target audience/hardware requirements.
- No release provider/account/signing model is authorized for a real application.
- Emulator availability depends on actual runner virtualization.
- Current Play rules are time-sensitive and require revalidation at release.
- The upcoming 2026-09-30 Play package-name registration requirement is not yet effective on the 2026-09-27 research date.

None of these unresolved items blocks a workflow proposal because Candidate 4 keeps them as project-specific/release-time decisions.

## 4. Baseline differences

Frozen baseline:
`references/WORKFLOW_BASE_ORIGINAL.md`

Material differences:
- The baseline is a web-project workflow explicitly naming `AI_STUDIO_OPERATOR`; Android Candidate 4 has **no mandatory external actor** and uses a capability-specific optional actor contract.
- The baseline contains historical web/Google/Firebase/npm/AI Studio specifics that AGENTS.md explicitly says must not be copied mechanically into Android.
- Android Candidate 4 introduces Android-specific host/device/release separation, Gradle/JDK/SDK environment contract, emulator/device capability gates, AAB/signing/Play boundaries.
- The current Workpack repository-access rule (GitHub integration/API only) governs this research execution; Candidate 4 itself remains portable and does not claim that all future Android implementers must lack local sandboxes.

Preserved governance concepts:
- Supervisor vs Implementer separation;
- GitHub/persistent issue state;
- explicit scope/authority;
- evidence/checkpoints;
- independent review;
- no self-approval.

## 5. Semantic risks that could propagate

1. **Host build conflation:** later tasks might treat "cloud sandbox" as device-capable. Candidate 4 explicitly forbids that assumption.
2. **Firebase creep:** because Firebase is first-party and convenient, later synthesis could accidentally make it mandatory. Keep it an adapter.
3. **Score-as-fact:** 90.0/85.8/73.8 are analytical scores only.
4. **Latest-version freezing:** AGP/Play requirements are current-state evidence, not permanent workflow constants.
5. **Device-matrix maximalism:** "more devices" is not automatically better; matrix must be risk-based.
6. **Release authority leakage:** ability to build/sign/upload must not be interpreted as authorization to publish.
7. **Compose absolutism:** Compose is preferred for new native UI, not a mandate to rewrite existing View applications.
8. **Workpack-access leakage:** the no-local-clone contract is specific to this Workpack execution and must not be mistaken for a universal Android architecture requirement.

## 6. Sensitivity summary

Baseline analytical totals:
- Minimal 73.8
- Portable 85.8
- Verified 90.0

One-at-a-time weight perturbations: ordering unchanged.  
Simplicity/cost scenario: Verified 86.25 vs Portable 84.38.  
Plausible score uncertainty around simplicity/cost nearly removes the gap.

Stability: **CONDITIONALLY_STABLE**.

## 7. Supervisor decision requested

Review whether Candidate 4:
- keeps the Android device-test trigger sufficiently concrete;
- avoids overengineering the adapter model;
- preserves release/security separation;
- correctly treats Firebase and external actors as optional;
- cleanly distinguishes Workpack-specific repository access from proposed Android workflow capability.

Allowed Supervisor outcomes remain:
`PASS | REWORK | HOLD | ESCALATE`.

Until an independent decision, Candidate 4 remains **PROPOSAL — NOT CANONICAL**.
