# Web Workflow Proposal

STATUS: PROPOSAL — NOT CANONICAL

## Proposal
Framework-Neutral, Risk-Tiered Web Workflow

## Purpose
Provide durable governance, browser/security evidence and protected deployment boundaries without requiring a particular framework, package manager, cloud, preview provider or coding-agent vendor.

## Baseline governance preservation — mandatory

This proposal preserves the accepted baseline guarantees exactly:

1. **Work Item contract** — every Work Item retains Objective + Acceptance Criteria + Authorized Scope + Relevant Sources + Verification + Base.
2. **Semantic Scope + Path Scope** — both are independent constraints; path permission never grants semantic permission.
3. **Exact-SHA Supervisor review** — semantic decisions apply only to the exact reviewed SHA; a new commit requires a new review.
4. **Supervisor decision state machine** — only `SEMANTIC_ACCEPTED | REWORK | HOLD | ESCALATE`; tests, CI, scores and actor output are evidence, not substitute decisions.
5. **Same-objective REWORK continuity** — corrections remain in the same Issue/branch/PR when objective and scope remain valid; scope/authority changes escalate.
6. **Supervisor-only merge boundary** — Implementer never self-merges and `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`.
7. **Publication authority** — `PUBLISH = HUMAN ACTION`. Build, sign, upload, deploy, credentials or release-tool capability do not transfer publication authority.
8. **GitHub session recovery** — a new authorized session must reconstruct Work Item, branch/ref + exact HEAD, PR, latest Supervisor decision/reviewed SHA, evidence/state and unresolved REWORK/HOLD/ESCALATE from durable GitHub artifacts.
9. **Baseline functional non-regression gate** — before recommendation/adoption, every protected guarantee must be preserved explicitly. Any unexplained loss, weakening, substitution or reinterpretation is a **HARD VETO**.

A HARD VETO cannot be compensated by analytical score, CI/test success, automation, portability, cost, convenience or external-actor capability.

Authority invariant:

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`


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
→ exact-SHA independent review/checkpoint
→ merge only after separate merge-eligibility checks
→ publication only by Human action

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
- must respect secrets and authority boundaries;
- are evidence surfaces, not production approval or publication.

## Secrets / deployment / publication
- private server/deployment secrets never belong in browser-delivered code;
- CI permissions remain least-privilege;
- untrusted PR code remains isolated from privileged deployment credentials;
- short-lived/OIDC cloud authentication is preferred where supported;
- production deployment capability remains a technical capability only.

Publication invariant:

`PUBLISH = HUMAN ACTION`

Deploy credentials, hosting roles, CI permissions, upload ability or ordinary Work Item permission do not transfer publication authority to Implementer, CI or an external actor.

## Optional external actor
Extension point: browser/device, design/accessibility, security or pre-publication deployment operator.

Contract:
- CAPABILITY: exact missing review/test/build/stage capability.
- PRECONDITIONS: governing Work Item, exact ref/SHA/artifact/environment/authority.
- AUTHORIZED OPERATIONS: named technical operation only.
- FORBIDDEN OPERATIONS: scope/authority changes, unrelated source edits, self-approval, merge, semantic decisions and production publication.
- EXPECTED BASELINE: governing Work Item + exact ref/SHA + artifact + browser/environment configuration.
- EVIDENCE RETURNED: run/staging ID, URL, reports, traces/screenshots and findings.
- STOP CONDITIONS: credential/billing requirement not authorized, baseline mismatch, invalid evidence, scope contradiction or attempted publication.
- ESCALATION PATH: Supervisor/Human.

### Durable external-actor activity — mandatory

Every external-actor invocation MUST create or update a durable GitHub activity/record under the governing Work Item, per Issue #2 comment `5879863384`.

Minimum record:
- ACTIVITY_ID / reference;
- GOVERNING_WORK_ITEM;
- ACTOR_TYPE;
- CAPABILITY;
- OBJECTIVE;
- PRECONDITIONS;
- AUTHORIZED_OPERATIONS;
- FORBIDDEN_OPERATIONS;
- EXPECTED_BASELINE / exact ref or SHA when applicable;
- EVIDENCE_REQUIRED;
- RESULT / evidence returned;
- STOP_CONDITIONS;
- ESCALATION_PATH;
- STATUS / closure state.

Required reconstructable lifecycle:

`request → authority → execution → evidence → result → stop/escalation`

The durable activity record is evidence/continuity only. It does not create Workflow authority, expand scope, authorize merge, issue semantic decisions or authorize publication.


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
- technical credential custody and cost;
- the Human production publication action.

## Platform delta preserved
Web remains distinct through project-selected runtime/build tooling, browser/E2E and accessibility evidence, preview/deploy environments and provider-specific deployment. No universal mobile-style signing gate is invented.

## Evidence
Detailed basis:
- outputs/06/web-evidence.md
- outputs/07/web-comparison.md
- outputs/07/web-sensitivity.md
- outputs/08/platform-deltas.md
- outputs/09/contradiction-audit.md
- outputs/09/source-freshness-audit.md
