# Web Candidate 4 — Presentation proposal

STATUS: PROPOSAL — NOT CANONICAL

## Name
**Framework-Neutral, Risk-Tiered Web Workflow**

## Core
```text
AUTHORIZED TASK
→ identify frontend/backend/full-stack boundary
→ project-native build/test adapter
→ static + unit + integration
→ risk trigger
   ├─ targeted browser/E2E
   ├─ accessibility/human UX review
   └─ preview environment when useful
→ evidence bundle
→ independent review
→ protected deployment adapter if authorized
```

## Governance
- Work Item defines scope/authority.
- Framework/runtime/package manager/hosting are project choices, not governance.
- GitHub/repository state provides durable continuity.
- CI evidence is not approval.

## Baseline functional non-regression ledger

Candidate 4 is a synthesis proposal, not an exception to the accepted Workflow baseline. This ledger is an eligibility condition independent of analytical score.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 4 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Every Web Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base. Frontend/backend/full-stack boundaries, project-native commands, browser targets, accessibility/UX review, preview and deployment needs populate the contract without replacing it. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Semantic Scope authorizes intended behavior/change and Path Scope authorizes files/modules. Frontend, backend, schema/data and deployment paths remain independently constrained; path permission never authorizes unrelated behavior. |
| 3. Exact-SHA Supervisor review | PRESERVED AS-IS | Supervisor semantic review applies only to the exact reviewed commit SHA. Any later commit creates a new HEAD requiring a new semantic decision; CI, browser/E2E, accessibility, preview or deployment evidence cannot carry semantic acceptance forward automatically. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor decision states. Build/test success, browser traces, accessibility findings, preview results, deployment checks and analytical scores are evidence only and cannot replace the semantic state machine. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections that keep the same Objective and authorized scope continue in the same Issue, branch and PR. Changes to Objective, authority, Semantic Scope, Path Scope, baseline semantics or other material contract terms require escalation rather than silent expansion. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI, browser automation, deployment adapters and optional external actors never self-merge. Exact-SHA SEMANTIC_ACCEPTED remains distinct from MERGE_ELIGIBLE; where integration is authorized, merge remains a Supervisor action after baseline eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Preview creation, deployment tooling, production credentials or technical ability to deploy do not create publication authority. Production publication remains separately authorized and **PUBLISH = HUMAN ACTION**. |
| 8. GitHub-based session recovery | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | A new authorized session reconstructs from GitHub the governing Work Item/Issue, branch/ref and exact HEAD, active PR, latest applicable Supervisor decision/reviewed SHA, checkpoint/evidence state, unresolved blockers, project-native build/test contract, browser policy and deployment constraints. Prior chat is not authoritative continuity. |
| 9. Baseline functional non-regression gate / HARD VETO | PRESERVED AS-IS | Candidate 4 remains eligible only if every protected baseline function is preserved or explicitly justified. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO** that higher analytical score, richer browser evidence, portability, automation or cost cannot offset. |

The ledger preserves Web semantics: framework/provider neutrality, browser automation distinct from human UX approval, accessibility automation distinct from human assessment, preview/deployment as evidence rather than approval, frontend/backend/secrets boundaries, and separate deployment/publication authority.

## Application contract
Record the project-native:
- runtime/package manager;
- install/build/lint/type/test commands;
- frontend/backend/schema boundaries;
- browser support targets;
- deployment artifacts.

No framework is mandated.

## Browser verification
Use project support targets. MDN Baseline may inform compatibility but cannot replace application/browser/accessibility testing.

Use E2E only at the smallest matrix justified by risk. Playwright is an example implementation, not a workflow dependency.

## Accessibility and design review
Automated checks are evidence, not complete WCAG/UX proof. Material UI changes require explicit human/design review where qualitative judgment is needed.

## Preview boundary
Preview is optional and tied to an exact commit/artifact. It must not silently receive production secrets or become an unreviewed production deployment.

## Secrets/security
- no private server/deploy secret in browser bundle;
- least-privilege CI token;
- untrusted PR code isolated from privileged deployment credentials;
- short-lived/OIDC cloud auth preferred where supported;
- production environment protected separately.

## Deployment adapter
Inputs: reviewed artifact/ref, target environment, authorization.
Outputs: deployment ID/URL, artifact identity, checks.
Production deployment/rollback authority remains explicit.

## Optional external actor
A design, browser/device, security or deployment operator may be added only under the standard bounded actor contract.

## Explicitly rejected legacy assumptions
This proposal does not require:
- Google AI Studio;
- Firebase;
- Google Cloud;
- npm specifically;
- a particular JS framework;
- a particular hosting/preview provider.

Those may be selected by a concrete application Work Item, but are not generic workflow rules.

## Evidence trace
- compatibility: W-01.
- browser automation: W-02/W-03.
- deployment/secrets gates: W-04/W-05/W-06.
- accessibility/human review: W-07/W-09.
- provider-neutral governance: W-08/W-10.
