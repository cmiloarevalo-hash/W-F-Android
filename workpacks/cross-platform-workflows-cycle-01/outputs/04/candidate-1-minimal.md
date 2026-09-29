# iOS Candidate 1 — Minimal

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Keep the smallest credible iOS workflow.

## Flow
```text
Issue/task
→ minimal context
→ implement
→ Swift unit tests
→ xcodebuild affected scheme
→ targeted simulator/UI tests when needed
→ evidence summary
→ review
→ separate release gate
```

## Environment
- one known-good macOS/Xcode lane;
- project-pinned package/dependency state;
- xcodebuild as automation surface;
- Linux may be used only for non-iOS Swift/package work when actually compatible.

## Testing
- Swift Testing for new unit/integration logic where suitable;
- XCTest retained for existing tests and UI automation;
- simulator test only when the change crosses UI/platform boundaries;
- physical device reserved for behavior simulators cannot prove.

## Release
Signing, provisioning, TestFlight and App Store upload remain manual/authorized actions. Production distribution credentials are not present in normal implementation CI.

## External actor
None by default. A Mac operator may be introduced only when the Implementer lacks macOS/Xcode capability, with source-write and release authority forbidden unless separately authorized.

## Baseline functional non-regression ledger

Candidate 1 remains the **MINIMAL** iOS workflow. Minimality reduces ceremony, not baseline governance or Apple platform boundaries.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 1 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every iOS Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. macOS/Xcode, scheme, simulator/device and release details populate the contract without replacing it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes the intended behavior/change and Path Scope authorizes files/modules. Both must pass independently; permission to edit a path never authorizes an unrelated semantic change. |
| 3. Exact-SHA Supervisor semantic review | PRESERVED AS-IS | Supervisor semantic review is valid only for the exact reviewed commit SHA. A new commit creates a new HEAD and requires a new semantic decision for that HEAD. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Swift tests, xcodebuild, simulator/device checks or CI success are evidence only and cannot replace the semantic decision. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections that keep the same Objective remain in the same Issue, branch and PR. A material change to Objective, Semantic Scope, Path Scope, authority or baseline semantics requires escalation rather than silent scope expansion. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer never self-merges. SEMANTIC_ACCEPTED applies only to the reviewed SHA and is not MERGE_ELIGIBLE. Where integration is authorized, the Supervisor merges only after exact-SHA semantic acceptance plus baseline merge-eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Xcode archive/export, code signing, TestFlight upload, App Store Connect access or release tooling do not create publication authority. **PUBLISH = HUMAN ACTION** unless explicitly changed by the Human. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | A new authorized session reconstructs from GitHub the governing Work Item/Issue, branch/ref and exact HEAD, active PR, latest applicable Supervisor decision and reviewed SHA, checkpoint/evidence, environment/release constraints and unresolved blockers. Prior chat transcript is not authoritative continuity. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | Candidate 1 is eligible only if all protected baseline functions remain preserved or explicitly justified. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO** that cannot be offset by simplicity, speed, CI success or later scoring. |

iOS-specific semantics remain unchanged: native app build/test uses macOS/Xcode where required; Linux is limited to compatible non-iOS Swift/package/domain work; simulator and physical-device evidence remain distinct; signing/provisioning stay protected; TestFlight/App Store remain separately authorized.

## Strengths
Low ceremony and cost; clear Apple boundary.

## Weaknesses
Less portable CI definition, thinner long-horizon evidence, more manual device/release judgment.
