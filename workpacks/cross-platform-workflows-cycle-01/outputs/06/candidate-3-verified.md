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
