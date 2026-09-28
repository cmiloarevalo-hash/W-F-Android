# Web Candidate 1 — Minimal

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Small framework-neutral workflow with a credible verification floor.

```text
Issue/task
→ identify frontend/backend scope
→ implement
→ lint/type/unit
→ integration/build
→ targeted browser E2E
→ optional preview
→ human UX review when visual behavior changes
→ review/deployment gate
```

Rules:
- use repository-native commands; do not impose npm/framework choices;
- never put secrets in browser code;
- run browser tests only where behavior warrants them;
- deployment and production secrets remain separately authorized;
- preview is optional evidence, not approval.

Strengths: simple, low lock-in, low ceremony.
Weaknesses: thinner audit trail and less systematic cross-browser/security coverage.

## Baseline functional non-regression ledger

This Minimal candidate keeps the baseline governance floor without adding verification ceremony beyond what the Web change requires.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 1 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Web Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Frontend/backend scope, repository-native commands, browser targets, preview/deployment needs and human UX review populate that contract without replacing it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes the intended behavior/change and Path Scope authorizes files/modules. Frontend, backend, shared contracts, data or deployment paths remain independently constrained; path access never authorizes unrelated behavior. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review applies only to the exact reviewed commit SHA. A later commit creates a new HEAD requiring a new semantic decision; lint, tests, browser E2E or preview evidence cannot carry acceptance forward automatically. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Build/test success, browser checks, preview results and human UX findings are evidence only and do not replace the decision state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections that retain the same Objective and authorized scope continue in the same Issue, branch and PR. A change to Objective, authority, Semantic Scope, Path Scope or baseline semantics requires escalation rather than silent expansion. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI and browser/deployment tooling never self-merge. Exact-SHA SEMANTIC_ACCEPTED remains distinct from MERGE_ELIGIBLE; where integration is authorized, merge remains a Supervisor action after baseline eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Preview creation, deployment tooling, production credentials or technical ability to deploy do not create publication authority. Production deployment/publication remains separately authorized and **PUBLISH = HUMAN ACTION**. |
| 8. GitHub-based session recovery | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | A new session reconstructs from GitHub the Work Item, branch/ref and exact HEAD, active PR, latest applicable Supervisor decision/reviewed SHA, checkpoint evidence, unresolved blockers and the minimal Web build/test/browser/deployment context needed for the task. Prior chat is not authoritative continuity. |
| 9. Baseline functional non-regression gate / HARD VETO | PRESERVED AS-IS | Candidate 1 is eligible only when every protected baseline function is preserved or explicitly justified. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO** that simplicity, test success, preview evidence or cost cannot offset. |

Web semantics remain unchanged: repository-native commands are retained, browser E2E is targeted, automated checks do not replace human UX review, preview remains optional evidence rather than approval, client code receives no private secrets, and deployment/publication authority remains separate.

