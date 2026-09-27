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
