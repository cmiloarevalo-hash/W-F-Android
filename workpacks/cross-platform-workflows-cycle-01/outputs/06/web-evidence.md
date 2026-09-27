# TASK 06 — Web evidence

Status: EXPERIMENTAL RESEARCH — NOT CANONICAL
Access date: 2026-09-27

## Claim ledger

| ID | Claim | Class | Evidence | Notes |
|---|---|---|---|---|
| W-01 | MDN Baseline tracks cross-browser availability across Safari, Chrome, Edge and Firefox on desktop/mobile; it is not a substitute for accessibility, usability, performance or security testing. | EXTERNAL_FACT | https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility | HIGH |
| W-02 | Playwright supports Chromium, Firefox, WebKit and branded Chrome/Edge channels; its browser binaries are version-coupled to Playwright. | EXTERNAL_FACT | https://playwright.dev/docs/browsers | HIGH |
| W-03 | Playwright documents CI execution, dependency installation and artifact/report capture; CI stability recommendations may differ from local parallel execution. | EXTERNAL_FACT | https://playwright.dev/docs/ci | HIGH |
| W-04 | GitHub deployment environments can gate deployments, restrict branches, require approvals and delay secret access until protection rules pass. | EXTERNAL_FACT | https://docs.github.com/en/actions/concepts/workflows-and-actions/deployment-environments | HIGH |
| W-05 | GitHub documents OIDC as a mechanism to authenticate CI to cloud providers without long-lived cloud credentials. | EXTERNAL_FACT | https://docs.github.com/en/actions/how-tos/secure-your-work/security-harden-deployments | HIGH |
| W-06 | GitHub warns pull_request_target requires hardening and least-privilege secret/token handling. | EXTERNAL_FACT | https://docs.github.com/en/actions/reference/security/securely-using-pull_request_target | HIGH |
| W-07 | WCAG 2.2 is a W3C Recommendation; many success criteria are testable but some require human evaluation. | EXTERNAL_FACT | https://www.w3.org/TR/wcag/ ; https://www.w3.org/WAI/WCAG22/Understanding/intro | HIGH |
| W-08 | Framework choice is not a prerequisite for defining governance, CI evidence, browser compatibility, deployment gates or secrets policy. | INFERENCE | W-01..W-07 | HIGH architectural inference |
| W-09 | Browser automation should not be equated with real-user UX/design approval. | INFERENCE | W-01, W-07 | HIGH |
| W-10 | Preview environments are useful evidence surfaces but remain deployments and should inherit authorization/secrets boundaries appropriate to their risk. | INFERENCE | W-04..W-06 | HIGH |

## Framework-neutral layers

1. **Governance/control plane**: Work Item, scope, durable state, evidence.
2. **Application build/test contract**: project-specific package manager/runtime/framework commands.
3. **Browser verification**: browser matrix, E2E traces/screenshots, accessibility checks.
4. **Preview/deployment domain**: ephemeral/staging/production environment with secrets and approvals.
5. **Human UX/design review**: visual/interaction judgement not reducible to automated pass/fail.

## Frontend/backend/full-stack boundary

A workflow must record which surfaces a task can modify:
- browser client only;
- API/backend only;
- shared schema/contracts;
- database/migrations;
- infrastructure/deployment.

Browser-delivered code must never contain server-side secrets.

## Compatibility

Use project support targets plus current compatibility evidence. MDN Baseline is useful but not sufficient for:
- older enterprise browsers/webviews;
- accessibility tech;
- performance;
- application-specific behavior.

## Testing ladder

1. static/type/lint checks;
2. unit tests;
3. integration/API/contract tests;
4. production-like build;
5. targeted browser/E2E tests;
6. accessibility checks + required human review;
7. preview smoke/design review;
8. deployment verification.

## Provider neutrality

Core workflow should not require a specific hosting provider, framework or cloud. Provider-specific adapters are acceptable when the project chooses them explicitly.
