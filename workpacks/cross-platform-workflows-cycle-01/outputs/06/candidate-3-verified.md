# Web Candidate 3 — Verified

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Maximize security, auditability and browser/UX evidence.

## Verification tiers
T0: dependency/runtime/environment sanity.
T1: lint/type/unit/integration/build.
T2: browser matrix E2E with traces/screenshots.
T3: accessibility automated checks plus required human assessment for applicable WCAG/UX criteria.
T4: controlled preview, security review and backend/schema integration checks.
T5: protected deployment with environment approvals, least-privilege secrets and post-deploy verification.

## Security
- browser code has no private secret;
- CI permissions minimized;
- untrusted PR workflows do not receive privileged deployment credentials;
- OIDC preferred over long-lived cloud keys where supported;
- production deployment is separate from implementation authority.

## Evidence
Persist command/version, browser matrix, test report, trace/screenshot refs, preview URL/commit, accessibility findings, deployment ID and unresolved warnings.

Strengths: strongest assurance.
Weaknesses: highest cost/complexity and potentially excessive for low-risk sites.

## Baseline functional non-regression ledger

This Verified candidate adds stronger evidence and security controls without changing baseline authority or turning verification into approval.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 3 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Web Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Verification tiers, browser matrix, accessibility/human-review requirements, preview/security checks and deployment evidence populate that contract without replacing it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope and Path Scope remain independent constraints across frontend, backend, schema/data and deployment surfaces. Deeper verification or security tooling never expands authorized behavior or writable paths. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review applies only to the exact reviewed commit SHA. Any later commit creates a new HEAD requiring new semantic review; traces, screenshots, accessibility findings, security checks or deployment IDs cannot transfer acceptance automatically. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. T0–T5 verification results, CI, browser evidence, security findings and human accessibility/UX assessment are evidence only and cannot replace the semantic decision state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections inside the same Objective and authorized scope continue in the same Issue, branch and PR. Discoveries requiring authority, Objective, Semantic Scope, Path Scope or baseline changes must escalate instead of being absorbed into a verification tier. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI, browser automation, security checks and deployment tooling never self-merge. Exact-SHA SEMANTIC_ACCEPTED remains distinct from MERGE_ELIGIBLE; authorized merge remains a Supervisor action after baseline integration checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Protected deployment environments, approvals, OIDC, production credentials and post-deploy verification do not create publication authority. Production deployment/publication remains separately authorized and **PUBLISH = HUMAN ACTION**. |
| 8. GitHub-based session recovery | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | A new session reconstructs from GitHub the Work Item, branch/ref and exact HEAD, PR, latest applicable Supervisor decision/reviewed SHA, checkpoint state, unresolved warnings and the persisted command/version, browser matrix, reports, traces/screenshots, preview reference, accessibility findings and deployment evidence needed for audit. Prior chat is not authoritative continuity. |
| 9. Baseline functional non-regression gate / HARD VETO | PRESERVED AS-IS | Candidate 3 remains eligible only if every protected baseline function is preserved or explicitly justified. Stronger T0–T5 verification, security, audit evidence or deployment controls cannot compensate for an unexplained baseline regression; that regression is a **HARD VETO**. |

Web semantics remain unchanged: browser matrices are risk-driven, browser automation does not equal human UX approval, accessibility automation is complemented by human assessment where required, preview is a controlled evidence environment rather than approval, browser code contains no private secrets, CI/deployment credentials remain least-privilege, and production authority remains separate.

