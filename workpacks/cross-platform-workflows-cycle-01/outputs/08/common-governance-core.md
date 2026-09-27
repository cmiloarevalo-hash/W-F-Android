# TASK 08 — Common governance core

STATUS: PROPOSAL — NOT CANONICAL

## Smallest justified common core

1. **Authorized Work Item**
   - objective, scope, roles, write boundaries and STOP conditions are explicit;
   - technical capability never expands authority.

2. **Durable repository control plane**
   - issue/task + branch/ref + state + checkpoints are reconstructable without chat memory;
   - stable governance is concise; task-specific evidence is loaded progressively.

3. **Environment contract**
   - record the project-native toolchain/runtime/build/test commands;
   - pin/record versions that affect reproducibility;
   - do not freeze "latest" as a permanent rule.

4. **Bounded implementation**
   - operate only inside authorized paths/operations;
   - secrets, network and external systems are least-privilege.

5. **Risk-tiered verification**
   - start with the smallest checks that prove the change;
   - escalate to device/browser/release-specific evidence when the change requires it;
   - tests/CI are evidence, not approval.

6. **Evidence discipline**
   - distinguish project fact, external fact, empirical observation, external statistic, analytical score, inference, recommendation and unknown;
   - material current claims carry source/date/version scope.

7. **Evidence bundle**
   - commit/ref;
   - environment/toolchain identity;
   - checks run and outcomes;
   - artifacts/run IDs;
   - unresolved warnings/uncertainty.

8. **Independent review boundary**
   - Implementer does not self-approve, merge or make proposals canonical;
   - release/deployment authority remains separately explicit.

9. **Candidate/proposal boundary**
   - exploratory designs remain CANDIDATE/PROPOSAL until an authorized adoption process.

10. **Optional external actor**
   - no actor is mandatory;
   - any actor is capability-specific, least-authority and evidence-returning.

## Common lifecycle

```text
AUTHORIZED WORK ITEM
→ reconstruct minimal context
→ define acceptance evidence
→ implement within scope
→ project-native host/static verification
→ risk classifier
→ platform-specific verification adapter when required
→ evidence bundle
→ checkpoint/review
→ separately authorized merge/release/deployment
```

## What is intentionally not common

The core does not mandate:
- Kotlin, Swift, JavaScript/TypeScript;
- Compose, SwiftUI or a web framework;
- Gradle, Xcode, npm or a specific package manager;
- Firebase, Xcode Cloud, Playwright or any CI provider;
- local vs cloud execution;
- a single device/browser matrix;
- a single distribution model.

Those belong to platform/project deltas.
