# Web Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Framework-Neutral, Risk-Tiered Web Workflow

## Purpose
Provide durable governance, browser/security evidence and protected deployment boundaries without requiring a particular framework, package manager, cloud, preview provider or coding-agent vendor.

## Core flow

AUTHORIZED WORK ITEM
→ classify frontend/backend/full-stack scope
→ project-native build/test adapter
→ static/type/lint + unit + integration + production-like build
→ risk trigger
   → browser/E2E matrix when needed
   → accessibility and human UX review when needed
   → preview environment when useful
→ evidence bundle
→ independent review/checkpoint
→ protected deployment adapter only when authorized

## Application contract
Record project-selected:
- runtime and package manager;
- install/build/type/lint/test commands;
- frontend/backend/schema/database boundaries;
- browser support targets;
- deployment artifact and environment model.

No framework or package manager is mandated.

## Browser verification
Use the project’s support policy and current compatibility evidence.

Browser/E2E automation should use the smallest matrix that proves the change. Playwright is one possible implementation, not a workflow dependency.

Automated browser checks are not equivalent to complete real-user UX evidence.

## Accessibility/design boundary
Automated accessibility testing is evidence, not complete WCAG/UX approval. Material interaction/visual changes require appropriate human/design/accessibility review where qualitative judgment is necessary.

## Preview boundary
Preview environments:
- are optional;
- are tied to an exact ref/artifact;
- must respect secrets and authorization boundaries;
- are evidence surfaces, not production approval.

## Secrets/deployment
- private server/deployment secrets never belong in browser-delivered code;
- CI permissions remain least-privilege;
- untrusted PR code remains isolated from privileged deployment credentials;
- short-lived/OIDC cloud authentication is preferred where supported;
- production deployment is a separately authorized action.

## Optional external actor
Extension point: browser/device, design/accessibility, security or deployment operator.

Contract:
- CAPABILITY: exact missing review/test/deploy capability.
- PRECONDITIONS: ref/artifact/environment/authorization.
- AUTHORIZED OPERATIONS: named operation only.
- FORBIDDEN OPERATIONS: scope/authority changes, unrelated source edits, unapproved production action.
- EXPECTED BASELINE: ref + artifact + browser/environment configuration.
- EVIDENCE RETURNED: run/deployment ID, URL, reports, traces/screenshots, findings.
- STOP CONDITIONS: credential/billing requirement not authorized, baseline mismatch, invalid evidence.
- ESCALATION PATH: Supervisor/Human.

## Explicit non-requirements
This proposal does not generically require:
- Google AI Studio;
- Firebase;
- Google Cloud;
- npm;
- React/Next/Vue/Angular or another framework;
- Vercel/Netlify/Cloudflare or another host;
- a particular E2E tool.

## Unresolved human decisions
A concrete web project must decide:
- framework/runtime/package manager;
- browser support matrix;
- accessibility/design review level;
- preview strategy;
- backend/database boundaries;
- deploy provider/environment protections;
- production release authority and cost.

## Evidence
Detailed basis:
- outputs/06/web-evidence.md
- outputs/07/web-comparison.md
- outputs/07/web-sensitivity.md
- outputs/09/source-freshness-audit.md
