# Web Candidate 2 — Portable

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Provider/framework-neutral contracts for long-lived portability.

## Adapters
- BUILD_TEST: runtime/package-manager/framework-specific commands.
- BROWSER_TEST: configured browser matrix and artifacts.
- PREVIEW: ephemeral URL + commit identity + expiry.
- DEPLOY: environment, artifact, authorization, evidence.
- EXTERNAL_ACTOR: optional bounded capability.

## Workflow
Portable governance and evidence schemas remain stable while adapters can be replaced.

Browser support is declared by project policy; MDN Baseline informs compatibility but does not replace testing.

Secrets:
- client receives only public/config values intended for exposure;
- server/deploy secrets live in protected runtime/environment stores;
- cloud auth may use short-lived/OIDC mechanisms where available.

Strengths: highest portability and recovery.
Weaknesses: adapter abstraction adds maintenance and cannot erase application-stack differences.

## Baseline functional non-regression ledger

This Portable candidate keeps the same baseline authority while expressing Web execution through replaceable provider/framework-neutral adapters.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 2 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Web Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. BUILD_TEST, BROWSER_TEST, PREVIEW and DEPLOY adapter selections are recorded inside that contract and do not replace it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope controls intended behavior/change and Path Scope controls files/modules. Swappable adapters or providers do not enlarge either scope, and path permission never grants unrelated semantic authority. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review is bound to the exact reviewed commit SHA. A replacement adapter, provider change or any later commit creates a new HEAD that requires a new semantic decision; portable evidence schemas do not transfer approval across SHAs. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Adapter output, browser reports, preview URLs and deployment evidence are inputs to review only and cannot substitute for the state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Same-objective corrections continue in the same Issue, branch and PR. A provider/framework substitution may remain REWORK only when Objective and authorized Semantic/Path Scope are unchanged; otherwise it escalates. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | Neither the Implementer nor BUILD_TEST/BROWSER_TEST/PREVIEW/DEPLOY adapters self-merge. Exact-SHA SEMANTIC_ACCEPTED remains distinct from MERGE_ELIGIBLE, and authorized integration remains a Supervisor action after baseline checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Provider-neutral DEPLOY capability, preview creation, cloud credentials or deployment automation do not grant publication authority. Production deployment/publication remains separately authorized and **PUBLISH = HUMAN ACTION**. |
| 8. GitHub-based session recovery | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | A new session reconstructs from GitHub the Work Item, branch/ref and exact HEAD, PR, latest applicable Supervisor decision/reviewed SHA, checkpoint/evidence state, declared browser policy and the selected BUILD_TEST/BROWSER_TEST/PREVIEW/DEPLOY adapter contracts. Prior chat is not authoritative continuity. |
| 9. Baseline functional non-regression gate / HARD VETO | PRESERVED AS-IS | Candidate 2 remains eligible only if all protected baseline functions are preserved or explicitly justified. Portability, provider substitution, recovery quality or adapter reuse cannot compensate for an unexplained baseline regression; that regression is a **HARD VETO**. |

Web semantics remain unchanged: framework/provider neutrality is preserved, MDN/browser policy informs but does not replace testing, browser automation does not equal human UX approval, preview/deployment remain evidence surfaces rather than approval, private server/deploy secrets stay out of browser code, and production authority remains separate.

