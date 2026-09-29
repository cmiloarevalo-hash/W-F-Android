# TASK 08 — Common governance core

STATUS: PROPOSAL — NOT CANONICAL

## Smallest justified common core

1. **Authorized Work Item**
   - preserves the mandatory fields: Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, Base;
   - Semantic Scope and Path Scope remain independent constraints;
   - technical capability never expands authority.

2. **Durable repository control plane**
   - governing Issue/Work Item, branch/ref, exact HEAD, active PR, checkpoints/evidence, latest applicable Supervisor decision/reviewed SHA and unresolved REWORK/HOLD/ESCALATE are reconstructable from GitHub without chat memory;
   - stable governance is concise; task-specific evidence is loaded progressively.

3. **Environment contract**
   - record the project-native toolchain/runtime/build/test commands;
   - pin/record versions that affect reproducibility;
   - do not freeze "latest" as a permanent rule.

4. **Bounded implementation**
   - operate only inside authorized Semantic Scope, Path Scope and operations;
   - secrets, network and external systems are least-privilege;
   - changes to Objective, authority, scope or baseline semantics require escalation rather than silent expansion.

5. **Risk-tiered verification**
   - start with the smallest checks that prove the change;
   - escalate to device/browser/release-specific evidence when the change requires it;
   - tests/CI are evidence, not approval.

6. **Evidence discipline**
   - distinguish project fact, external fact, empirical observation, external statistic, analytical score, inference, recommendation and unknown;
   - material current claims carry source/date/version scope.

7. **Evidence bundle**
   - exact commit/ref;
   - environment/toolchain identity;
   - checks run and outcomes;
   - artifacts/run IDs;
   - unresolved warnings/uncertainty.

8. **Independent review boundary**
   - Implementer does not self-approve, merge or make proposals canonical;
   - Supervisor semantic review is bound to the exact reviewed SHA;
   - a new commit creates a new HEAD and requires a new semantic decision;
   - SEMANTIC_ACCEPTED is not MERGE_ELIGIBLE;
   - where integration is authorized, merge remains Supervisor-only after exact-SHA semantic acceptance and merge-eligibility checks;
   - this Workpack itself authorizes no merge.

9. **Publication boundary**
   - build, sign, upload, deploy, release-tool access, credentials or technical capability do not create publication authority;
   - **PUBLISH = HUMAN ACTION**.

10. **Candidate/proposal boundary**
   - exploratory designs remain CANDIDATE/PROPOSAL until an authorized adoption process.

11. **Optional external actor**
   - no actor is mandatory;
   - any actor is capability-specific, least-authority and evidence-returning;
   - every invocation uses the bounded actor contract and a durable GitHub activity record under the governing Work Item;
   - TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

## Baseline functional non-regression preservation contract

This Common Core is eligible only if the protected baseline functions remain explicit. The status vocabulary is the accepted TASK 01 vocabulary.

| Protected baseline guarantee | Status | Common Core preservation |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification and Base. Platform-specific toolchain/device/browser/release details populate these fields without replacing them. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes behavior; Path Scope authorizes files/modules. Both are independently enforced. Path permission never grants unrelated semantic authority. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review applies only to the exact reviewed SHA. Any later commit creates a new HEAD and invalidates prior semantic acceptance for that new HEAD; CI/test success cannot carry acceptance forward. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the Supervisor decision states. Automated evidence, score, tool output or actor result cannot substitute for the semantic/governance state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Same-objective corrections normally continue in the same Issue, branch and PR. A change to Objective, authority, Semantic Scope, Path Scope, baseline semantics or other material contract terms escalates rather than silently expanding the Work Item. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | Implementer, CI and external actors never self-merge. Where integration is authorized, the Supervisor may merge only after exact-SHA SEMANTIC_ACCEPTED plus merge-eligibility checks. This Workpack grants no merge authority. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Technical ability to build, sign, upload, deploy or publish never transfers publication authority. **PUBLISH = HUMAN ACTION** across Android, iOS and Web. |
| 8. GitHub-based session recovery | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Recovery identifies governing Issue/Work Item, branch/ref and exact HEAD, active PR, latest applicable Supervisor decision/reviewed SHA, checkpoint/evidence, platform environment contract and unresolved REWORK/HOLD/ESCALATE. Prior chat is not authoritative continuity. |
| 9. Baseline functional non-regression gate / HARD VETO | PRESERVED AS-IS | Any unexplained loss, weakening, substitution or reinterpretation of a protected baseline function is a **HARD VETO**. Score, portability, automation, CI/test success, cost or external-actor capability cannot compensate for the veto. |

## Common lifecycle

```text
AUTHORIZED WORK ITEM
→ reconstruct GitHub authority + exact HEAD
→ define acceptance evidence
→ implement within Semantic Scope + Path Scope
→ project-native host/static verification
→ risk classifier
→ platform-specific verification adapter when required
→ optional bounded external-actor activity when required
→ evidence bundle
→ exact-SHA independent Supervisor review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ merge only if separately authorized and MERGE_ELIGIBLE
→ technical release/deployment operation only within explicit authority
→ PUBLISH = HUMAN ACTION
```

## What is intentionally not common

The core does not mandate:
- Kotlin, Swift, JavaScript/TypeScript;
- Compose, SwiftUI or a web framework;
- Gradle, Xcode, npm or a specific package manager;
- Firebase, Xcode Cloud, Playwright or any CI provider;
- local vs cloud execution;
- a single device/browser matrix;
- a single signing mechanism;
- a single distribution/deployment model.

Those remain platform/project deltas and are not erased to force symmetry.
