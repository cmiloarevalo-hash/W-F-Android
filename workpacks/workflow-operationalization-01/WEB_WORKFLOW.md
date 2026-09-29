# Web Operational Workflow

STATUS: PROPOSAL — NOT CANONICAL

PLATFORM: WEB

GOVERNING WORK ITEM FOR THIS DOCUMENT:
Issue #8

ACCEPTED WEB BASELINE ADAPTATION MATRIX:
d73dbe80b8ee3fa7376c4cad0bad4ff0c2d0e5ef

ACCEPTED DOCUMENT ARCHITECTURE:
621d4e58eccbc697d42074e5f7eaa53a162a0582

DOCUMENT PURPOSE:
Standalone operational workflow for Web engineering work executed by Human + Supervisor + Implementer + GitHub/CI, with optional bounded browser/design/security/deployment/platform external actors.

PRIMARY DESIGN RULE:

WEB_WORKFLOW.md = BASELINE FUNCIONAL + ADAPTACIÓN WEB JUSTIFICADA

This document is an operational workflow. It is not a research report, executive summary, Candidate presentation, or automatic canonical replacement for the frozen functional baseline.

No merge, canonical adoption, preview promotion, staging promotion, production deployment, DNS/CDN/database mutation, or product publication is authorized merely because this document exists or is semantically accepted as a proposal artifact.

---

## 0. Document status, authority, provenance, and source precedence

### 0.1 What this document is

This document defines how an authorized Web Work Item is:

- created;
- bootstrapped;
- implemented;
- built and tested using project-native tooling;
- verified across browser/runtime surfaces when justified;
- checked across client/server/API/schema/database/infrastructure boundaries;
- evaluated through accessibility/UX/browser-compatibility evidence when material;
- handled across preview/staging/deployment boundaries;
- protected across secrets/environment/provider boundaries;
- handed off;
- independently reviewed;
- reworked;
- integrated;
- recovered across sessions;
- prepared for Human-controlled product publication when applicable.

It is designed so that a fresh authorized session can operate the normal lifecycle using:

- the repository;
- the active GitHub Issue / Work Item;
- this Web workflow;
- project documentation explicitly referenced by the Work Item.

Normal operation MUST NOT require reconstructing procedure from Issue #2 research outputs.

### 0.2 What this document is not

This document is not:

- a requirement to use JavaScript or TypeScript;
- a requirement to use Node.js;
- a requirement to use npm, pnpm, yarn, bun, or another package manager;
- a requirement to use React, Next.js, Vue, Angular, Svelte, or any other framework;
- a requirement to use Playwright, Cypress, Selenium, or another E2E tool;
- a requirement to use GitHub Actions;
- a requirement to use Vercel, Netlify, Cloudflare, AWS, GCP, Azure, Firebase, or another host/cloud;
- a requirement to use a preview environment;
- a universal mobile-style signing gate;
- an authorization to expose or use production secrets;
- an authorization to mutate DNS/CDN/database/hosting/cloud state;
- an authorization to deploy to production;
- a timeless source for volatile browser, runtime, framework, provider, cloud, security, or hosting facts.

### 0.3 Source precedence

When sources appear to conflict, apply this precedence:

1. Current Human/Supervisor authority in the active governing Work Item.
2. This platform workflow for the normal Web operational lifecycle, once the active Work Item points to it.
3. Frozen functional baseline for inherited lifecycle semantics and non-regression.
4. Accepted Common Core / authority / external-actor controls from Issue #2.
5. Accepted Web evidence and platform deltas from Issue #2.
6. Historical research summaries only as evidence/provenance.

Rules:

- Current Work Item authority controls task scope.
- Evidence does not create authority.
- Technical capability does not create authority.
- A shorter summary cannot weaken a normative rule in this document.
- A later commit cannot inherit semantic acceptance from another SHA automatically.
- Volatile external facts are refreshed only through the Research/Freshness Gate when materially required.

### 0.4 Provenance used to produce this workflow

Frozen baseline:
- references/WORKFLOW_BASE_ORIGINAL.md
- baseline blob: fa6ce8e396e1ae422ce4feab3f97d7d37bb43f83

Accepted document architecture:
- Workflow Document Contract;
- ADR-001 — standalone baseline-derived platform workflows;
- architecture accepted at 621d4e58eccbc697d42074e5f7eaa53a162a0582.

Accepted Web adaptation:
- WEB_BASELINE_ADAPTATION_MATRIX.md;
- accepted at d73dbe80b8ee3fa7376c4cad0bad4ff0c2d0e5ef.

Accepted Issue #2 evidence reused:
- Web capability matrix;
- Web evidence ledger;
- Web Candidate 4;
- Common Governance Core;
- Optional External Actor Interface;
- Platform Deltas;
- Contradiction Audit;
- final Web workflow proposal;
- final Issue #2 handoff.

Issue #2 evidence is reused.
The comparative Candidate/scoring/sensitivity cycle is not repeated by this workflow.

Accepted Android/iOS workflows prove the document architecture is executable.
They are not Web mechanics sources.

---

## 1. Purpose, audience, and usage

### 1.1 Objective

The objective is to provide a complete Web engineering workflow that:

- preserves the full operational lifecycle of the functional baseline;
- adds Web-specific runtime/framework/package-manager, build/test, browser/E2E, client/server/API/data, preview/deployment, secrets, provider, and external-mutation constraints only where justified;
- remains framework-neutral and provider-neutral where practical;
- is recoverable across sessions;
- separates evidence from authority;
- scales browser/runtime/deployment evidence according to technical risk;
- prevents accidental merge, deployment, publication, scope expansion, secret exposure, or authority transfer.

### 1.2 Audience

Primary consumers:

- Human;
- Supervisor;
- Implementer / technical writer-engineer / coding agent;
- optional external actor when a concrete missing capability requires one.

Supporting systems:

- GitHub;
- CI;
- project runtime/build tools;
- browsers and browser automation;
- API/integration test infrastructure;
- preview/staging environments;
- hosting/cloud/CDN/database providers;
- deployment tooling;
- accessibility/security analysis tools.

Supporting systems produce state/evidence.
They do not issue semantic decisions.

### 1.3 When to use this workflow

Use this workflow for Web Work Items involving:

- browser client code;
- server/API code;
- shared contracts/schema;
- databases/migrations;
- background jobs/services;
- static/site generation;
- server rendering;
- edge/serverless functions;
- browser compatibility;
- responsive/device behavior;
- accessibility/UX;
- build tooling;
- package/runtime configuration;
- CI;
- preview/staging;
- hosting/CDN/cloud configuration;
- deployment technical work;
- secrets/environment variables;
- external platform mutation;
- Web-specific documentation;
- Web workflow maintenance under explicit authority.

For a non-Web task, use the appropriate workflow or governing repository instructions.

---

## 2. Fundamental principles

### 2.1 GitHub is durable memory

The repository, Issue, branch/ref, commits, PR, evidence, CI, Supervisor decisions, deployment evidence, and external-actor records are durable state.

Prior chat transcript is not an authority source.

### 2.2 Work Item before substantial work

A sufficiently important task must exist as a bounded GitHub Issue / Work Item.

### 2.3 Two independent scopes

Semantic Scope controls what behavior/change is authorized.

Path Scope controls which files/modules/systems may be changed.

PATH PERMISSION != SEMANTIC PERMISSION.

Both must pass.

External-system permission is an additional operation boundary.
A provider credential or account role does not enlarge either scope.

### 2.4 Exact-SHA review

Supervisor semantic review applies only to the exact reviewed SHA.

A later commit creates a new HEAD and requires a new semantic decision for that HEAD.

### 2.5 Evidence is not approval

CI/TEST PASS != SEMANTIC_ACCEPTED.

Build success, typecheck, lint, unit/API/integration/E2E success, browser traces, accessibility results, preview success, deployment success, actor output, or artifact generation remain evidence only.

### 2.6 Capability is not authority

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

A technical actor may possess source access, browser access, deployment credentials, cloud roles, database access, DNS access, CDN access, hosting controls, secret-manager access, or production deploy capability and still lack authority to exercise them for a specific operation.

### 2.7 Semantic acceptance is not merge eligibility

SEMANTIC_ACCEPTED != MERGE_ELIGIBLE.

Merge requires separate integration checks and appropriate authority.

### 2.8 Product publication is Human action

PUBLISH = HUMAN ACTION.

Preview creation, staging deployment, production deploy capability, hosting access, DNS/CDN control, or release tooling does not transfer product publication authority to Implementer, CI, or external actor.

### 2.9 Baseline non-regression is a HARD VETO

Any unexplained loss, weakening, substitution, or reinterpretation of a protected baseline function is a HARD VETO.

A HARD VETO cannot be compensated by:

- score;
- CI success;
- test success;
- browser coverage;
- automation;
- portability;
- cost;
- convenience;
- provider capability;
- external-actor capability.

### 2.10 Web capability boundaries are explicit

LOCAL BUILD CAPABILITY != BROWSER-COMPATIBILITY PROOF.

BROWSER AUTOMATION != COMPLETE REAL-USER UX PROOF.

PREVIEW/STAGING/DEPLOY CAPABILITY != PRODUCT PUBLICATION AUTHORITY.

CLIENT ACCESS != SERVER/API/DATABASE/INFRASTRUCTURE AUTHORITY.

PUBLIC BROWSER CONFIG != PRIVATE SERVER/DEPLOY SECRET.

A passing build is not assumed to prove browser behavior.
A passing automated E2E suite is not assumed to prove complete UX/accessibility quality.
A successful deployment is not assumed to authorize publication.

---

## 3. Roles, responsibilities, and authority

### 3.1 Human

#### MUST

The Human MUST:

- define product intent and priorities;
- decide material product direction changes;
- decide material architecture/Workflow changes when reserved to Human authority;
- provide or authorize credentials, MFA, account access, production environment access, and material provider permissions when needed;
- decide material costs or paid provider commitments unless explicitly delegated;
- perform product publication.

#### MAY

The Human MAY:

- set browser/product support policy;
- set accessibility/UX acceptance expectations;
- approve provider budgets;
- define release timing;
- approve exceptional trade-offs;
- authorize bounded production technical preparation;
- explicitly change Work Item intent or architecture through a persisted decision.

#### MUST NOT be treated as

The Human MUST NOT be treated as:

- routine implementer;
- substitute for durable evidence;
- implicit approver of production deploy/publication merely because credentials or provider access exist.

#### Reserved decisions

Reserved to Human unless a governing decision says otherwise:

- product intent;
- material product scope change;
- credentials/MFA;
- material paid-service/provider commitments;
- production/public product publication.

#### Required evidence/output

A material Human decision that changes scope, permission, cost, credential use, provider commitment, production state, or publication state must be persisted in GitHub.

---

### 3.2 Supervisor

#### MUST

The Supervisor MUST:

- interpret Human intent;
- create or validate a bounded Work Item;
- verify Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base;
- distinguish Semantic Scope from Path Scope;
- define required evidence;
- inspect exact HEAD;
- independently review implementation, tests, docs, CI, browser/runtime evidence, accessibility/UX evidence, preview/deploy evidence, secrets boundaries, and external mutations when relevant;
- issue only:
  - SEMANTIC_ACCEPTED
  - REWORK
  - HOLD
  - ESCALATE
- verify merge eligibility separately.

#### MAY

The Supervisor MAY:

- authorize bounded local or external technical activities;
- request targeted fresh research;
- define a browser/device/responsive evidence matrix;
- define preview/staging/deploy technical evidence;
- narrow or clarify verification;
- merge only where governing Workflow and repository authority separately allow it and merge eligibility passes.

#### MUST NOT

The Supervisor MUST NOT:

- treat CI/test/browser/deploy PASS as semantic acceptance;
- infer publication authority from deploy capability;
- silently expand Human intent;
- treat an old reviewed SHA as acceptance of a new SHA;
- treat a preview or production deployment as semantic approval.

#### Required evidence/output

Supervisor decisions must persist:

- Work Item;
- reviewed SHA;
- evidence basis;
- decision;
- blockers or required corrections;
- next authority/action when applicable.

---

### 3.3 Implementer

#### MUST

The Implementer MUST:

- bootstrap from GitHub before editing;
- verify repository, Work Item, role, authority, Base, branch/PR target, Semantic Scope, Path Scope, and required verification;
- read minimum necessary context;
- reconstruct project runtime/framework/package-manager/build facts relevant to the task;
- identify client/server/API/schema/database/infrastructure boundaries;
- implement only the authorized objective;
- use project-native Web tooling;
- run required verification;
- inspect complete diff;
- persist exact commit/PR evidence;
- report unexpected findings;
- stop on authority/scope/base contradiction.

#### MAY

The Implementer MAY:

- choose bounded implementation details consistent with existing architecture;
- add/update tests inside authorized scope;
- run browser/E2E checks when required;
- use an authorized preview/staging environment;
- invoke an authorized external actor through section 30;
- perform REPOSITORY_PUBLICATION when explicitly allowed;
- perform bounded external platform mutations only when explicitly authorized.

#### MUST NOT

The Implementer MUST NOT:

- expand Objective or Acceptance Criteria;
- expand Semantic Scope or Path Scope;
- modify architecture/Workflow without authority;
- edit frozen baseline/reference material when forbidden;
- self-approve;
- issue SEMANTIC_ACCEPTED;
- issue MERGE_ELIGIBLE;
- merge by inference;
- publish the product;
- expose private server/deploy secrets to browser-delivered code;
- use production credentials merely because technically available;
- mutate database/DNS/CDN/hosting/cloud state by inference;
- invent current browser/runtime/framework/provider/security facts.

#### Required evidence/output

At handoff the Implementer must provide:

- Work Item;
- branch/PR;
- exact HEAD;
- changed paths;
- runtime/framework/package-manager/build context;
- affected client/server/API/schema/database/infrastructure surfaces;
- verification commands/results;
- browser/E2E/accessibility evidence when required;
- preview/staging/deploy evidence when applicable;
- external mutation evidence when applicable;
- CI status;
- unexpected findings;
- unresolved risks;
- state.

---

### 3.4 GitHub

GitHub is the persistent control plane for:

- Work Item authority;
- branch/ref;
- commits;
- PR;
- changed files;
- evidence links;
- CI;
- deployment evidence references;
- Supervisor decisions;
- external-actor activity records;
- session recovery.

GitHub does not make semantic decisions by itself.

---

### 3.5 CI

CI:

- runs reproducible mechanical checks;
- associates evidence with a commit;
- may install dependencies, typecheck, lint, test, build, and run browser/API jobs;
- may create preview/staging/deployment evidence when explicitly authorized;
- may retain artifacts, traces, screenshots, reports, and deployment IDs.

CI MUST NOT:

- issue SEMANTIC_ACCEPTED;
- issue MERGE_ELIGIBLE;
- merge unless separately governed automation explicitly has that authority;
- publish product by inference;
- infer secret/provider/production authority from credential access.

CI/TEST PASS != SEMANTIC_ACCEPTED.

---

### 3.6 Optional external actor

An external actor is optional.

Examples:

- browser/device operator;
- accessibility/design reviewer;
- security specialist;
- hosting/cloud/CDN operator;
- bounded deployment operator;
- database migration operator;
- DNS/configuration operator.

No external actor is included by symmetry or provider preference alone.

It must supply a concrete missing capability and operate under the protocol in section 30.

---

## 4. Terminology, states, and notation

### 4.1 Formal Supervisor semantic decisions

Only:

- SEMANTIC_ACCEPTED
- REWORK
- HOLD
- ESCALATE

No Web-specific decision state may replace these.

### 4.2 Lifecycle/integration states

Operational states may include:

- READY_FOR_REVIEW
- MERGE_ELIGIBLE
- MERGED
- CLOSED

These are not semantic decisions.

### 4.3 CI/evidence states

Use:

- PASS
- FAIL
- PENDING
- NOT CONFIGURED

### 4.4 Document status

Until explicit canonical adoption:

PROPOSAL — NOT CANONICAL.

### 4.5 Repository publication vs preview/deploy vs product publication

REPOSITORY_PUBLICATION means:

- commit;
- push;
- opening/updating a PR;
- making proposed repository changes available for review.

PREVIEW/STAGING/DEPLOYMENT means a technical change to a runtime environment.

PUBLISH / PRODUCT_PUBLICATION means an externally observable product release or production publication under the governing product process.

PUBLISH = HUMAN ACTION.

A technical preview/staging/deploy operation may be separately authorized without transferring Human publication authority.

### 4.6 Baseline adaptation vocabulary

For maintenance/traceability:

- PRESERVE
- ADAPT
- EXTEND
- NOT_APPLICABLE_WITH_JUSTIFICATION

These are coverage classifications, not workflow decisions.

### 4.7 Notation

A → B means ordered lifecycle transition.

A != B means explicit non-equivalence.

MUST / MUST NOT are normative.

SHOULD / MAY are recommendations/options.

Exact SHA means immutable commit identity used for review/evidence.

---

## 5. Work Item contract

Every substantial Web task MUST have a Work Item with six explicit fields.

No field may be silently grouped away.

### 5.1 Objective

Defines what must be achieved.

The Objective:

- is outcome-oriented;
- must be testable through Acceptance Criteria;
- does not grant authority outside Authorized Scope;
- cannot be silently changed by the Implementer.

### 5.2 Acceptance Criteria

Defines observable conditions for success.

Web Acceptance Criteria SHOULD identify relevant evidence such as:

- project-native unit/integration behavior;
- build/typecheck/lint/static-analysis result;
- API/contract behavior;
- targeted browser/E2E behavior;
- responsive/device behavior;
- accessibility evidence;
- preview/staging smoke evidence;
- deployment verification;
- documentation updates;
- external mutation verification.

Acceptance Criteria do not authorize unrelated changes.

### 5.3 Authorized Scope

Defines authorized files/modules/systems and permitted operations.

It should identify as applicable:

- browser client;
- server/API;
- shared schema/contracts;
- database/migrations;
- background jobs/services;
- infrastructure/configuration;
- deployment files;
- provider/environment operations;
- secret/environment-variable operations;
- external mutations.

Authorized Scope MUST NOT be interpreted as Semantic Scope expansion.

### 5.4 Relevant Sources

Typical priority:

1. this Web workflow;
2. AGENTS.md / PROGRAM.md and more specific repository instructions;
3. affected project/runtime/framework docs in the repository;
4. API/schema/database/infrastructure docs relevant to the task;
5. deployment/secrets docs relevant to the task;
6. accepted evidence explicitly cited by the Work Item;
7. fresh official sources only if Research/Freshness Gate activates.

Issue #2 research is provenance/evidence, not a mandatory normal-operation reading set.

### 5.5 Verification

Defines required proof.

Examples:

- install/dependency validation;
- unit tests;
- integration/API/contract tests;
- lint;
- typecheck;
- static analysis;
- production-like build;
- targeted browser/E2E checks;
- accessibility checks;
- responsive/device checks;
- preview/staging smoke;
- deployment verification;
- migration verification;
- rollback verification when required.

The Work Item should specify the smallest evidence set that proves the change while respecting risk.

### 5.6 Base

Defines the exact starting branch/ref/commit.

The Implementer MUST verify Base before editing.

Wrong Base is STOP.

Browser/provider/deployment capability cannot compensate for Base mismatch.

### 5.7 Work Item template

~~~markdown
## Objective

...

## Acceptance Criteria

- ...

## Authorized Scope

- Semantic Scope:
- Path Scope:
- Client/server/API/data surfaces:
- Allowed external operations:
- Allowed secret/environment operations:
- Forbidden operations:

## Relevant Sources

- ...

## Verification

- ...

## Base

- branch/ref:
- exact SHA when required:
~~~

---

## 6. Semantic Scope + Path Scope

### 6.1 Semantic Scope

Semantic Scope authorizes intended behavior/change.

Examples:

- fix a specific browser bug;
- add one bounded feature;
- update one API contract;
- add one migration under explicit authority;
- adjust one deployment configuration under explicit authority.

Semantic Scope does not automatically authorize every implementation path or external system.

### 6.2 Path Scope

Path Scope authorizes files/modules.

Examples:

- src/client/...
- src/server/...
- packages/...
- migrations/...
- infrastructure/...
- deployment configuration paths.

Path Scope does not authorize unrelated behavior change.

### 6.3 External-operation scope

An external provider/database/DNS/CDN/hosting operation requires its own explicit operation authority.

Repository path access is not provider authority.

Provider access is not repository authority.

### 6.4 Required rule

Both Semantic Scope and Path Scope must pass independently.

PATH PERMISSION != SEMANTIC PERMISSION.

If correct implementation requires:

- a path outside Path Scope;
- behavior outside Semantic Scope;
- a new external-system operation;
- production-secret access;
- provider/account/cost authority;

STOP → report → Supervisor decision.

---

## 7. End-to-end lifecycle

Normal Web lifecycle:

Human intent
→ Supervisor analysis
→ GitHub Work Item
→ Implementer bootstrap
→ project/runtime context reconstruction
→ client/server/API/data boundary reconstruction
→ bounded implementation
→ project-native build/test/lint/typecheck/static verification
→ Web risk classification
→ browser/E2E evidence when required
→ accessibility/UX evidence when required
→ preview/staging evidence when useful and authorized
→ external mutation/deploy evidence when required and authorized
→ evidence bundle
→ REPOSITORY_PUBLICATION
→ Implementer handoff
→ Supervisor exact-SHA review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ if accepted, integration target checks
→ MERGE_ELIGIBLE only if separately satisfied
→ merge only under separate authority
→ production technical operation only if separately authorized
→ product publication only by Human action
→ CLOSED when governing conditions are complete.

A shorter path is valid only when steps are genuinely not applicable.

---

## 8. Human intent and Work Item creation

### 8.1 Human intent

Before creating the Work Item, Supervisor should identify:

- desired product outcome;
- Web surface affected;
- client/server/full-stack scope;
- API/schema/database impact;
- infrastructure/deployment impact;
- user/browser impact;
- accessibility/UX impact;
- security/privacy impact;
- secrets/environment impact;
- migration/external mutation impact;
- preview/staging/deploy impact;
- current-fact uncertainty;
- credential/account/provider/cost needs.

### 8.2 Work Item creation

Supervisor persists:

- Objective;
- Acceptance Criteria;
- Authorized Scope;
- Relevant Sources;
- Verification;
- Base.

Prefer:

ONE OBJECTIVE → ONE BRANCH → ONE PR

unless repository governance explicitly uses another model.

### 8.3 Web-specific planning questions

When material, determine:

- runtime?
- framework/library?
- package manager?
- install/dev/build/test/lint/typecheck/static commands?
- browser client only, server/API only, or full-stack?
- shared schema/contracts?
- database/migrations?
- background jobs/services?
- browser support policy?
- responsive/device impact?
- E2E needed?
- accessibility/UX review needed?
- preview useful?
- staging/deploy required?
- hosting/cloud/CDN/database provider involved?
- production secrets or environment variables involved?
- untrusted PR execution boundary?
- external platform mutation required?
- rollback required?
- provider cost/account permission required?
- product publication action required?

---

## 9. Implementer start and bootstrap

The start prompt SHOULD be short and pointer-based.

Example:

~~~text
ROLE: IMPLEMENTER
REPOSITORY: owner/repo
WORK ITEM: #123
Read WEB_WORKFLOW.md and the Work Item.
Verify authority/base/scope before editing.
Implement only the authorized objective.
Persist evidence/handoff.
STOP on mismatch.
~~~

The prompt is not the durable task definition.
GitHub is.

### 9.1 Mandatory bootstrap questions

Before edits, answer from GitHub/repository evidence:

1. REPOSITORY MATCH?
2. CURRENT ROLE?
3. GOVERNING WORK ITEM?
4. CURRENT AUTHORITY?
5. EXACT BASE / HEAD?
6. TARGET BRANCH / PR MODEL?
7. OBJECTIVE?
8. ACCEPTANCE CRITERIA?
9. SEMANTIC SCOPE?
10. PATH SCOPE?
11. REQUIRED SOURCES?
12. REQUIRED VERIFICATION?
13. RUNTIME / FRAMEWORK / LIBRARY?
14. PACKAGE MANAGER?
15. INSTALL / DEV / BUILD / TEST / LINT / TYPECHECK / STATIC COMMANDS?
16. CLIENT / SERVER / API / SCHEMA / DATABASE SURFACES?
17. BACKGROUND / INFRASTRUCTURE SURFACES?
18. BROWSER SUPPORT TARGETS?
19. E2E/BROWSER EVIDENCE REQUIRED?
20. RESPONSIVE/DEVICE EVIDENCE REQUIRED?
21. ACCESSIBILITY/UX REVIEW REQUIRED?
22. PREVIEW/STAGING REQUIRED?
23. DEPLOYMENT REQUIRED?
24. SECRETS/ENVIRONMENT ACCESS REQUIRED?
25. EXTERNAL PLATFORM MUTATION REQUIRED?
26. CREDENTIAL/COST/PROVIDER ACTION REQUIRED?
27. PRODUCT PUBLICATION AUTHORIZED TO TECHNICAL ACTOR? Expected answer: NO.
28. UNRESOLVED HOLD/REWORK/ESCALATE?
29. MISMATCH CHECK: PASS | FAIL?

If any material answer is UNKNOWN and cannot be safely reconstructed:

STOP → report blocker → Supervisor.

### 9.2 Bootstrap output

~~~text
WEB_IMPLEMENTER_BOOTSTRAP

REPOSITORY:
ROLE:
WORK ITEM:
AUTHORITY:
BASE:
BRANCH/PR:
OBJECTIVE:
SEMANTIC SCOPE:
PATH SCOPE:
RUNTIME/FRAMEWORK:
PACKAGE MANAGER:
BUILD/TEST CONTRACT:
CLIENT/SERVER/API/DATA BOUNDARY:
BROWSER SUPPORT:
E2E REQUIRED: YES | NO | UNKNOWN
ACCESSIBILITY/UX REVIEW REQUIRED: YES | NO | UNKNOWN
PREVIEW/STAGING REQUIRED: YES | NO
DEPLOYMENT REQUIRED: YES | NO
SECRETS/ENVIRONMENT ACCESS: YES | NO
EXTERNAL MUTATION: YES | NO
PRODUCT PUBLISH AUTHORITY FOR TECHNICAL ACTOR: NO
MISMATCH CHECK: PASS | FAIL
STATE: READY | BLOCKED
~~~

---

## 10. Reading and context policy

Use progressive disclosure.

### 10.1 Read first

1. Active Work Item.
2. This Web workflow.
3. AGENTS.md / PROGRAM.md and more specific repository instructions.
4. Package/runtime/build manifest files relevant to affected code.
5. Affected client/server/API/schema/database/infrastructure code.
6. Tests adjacent to changed behavior.
7. Project docs directly relevant to task.

### 10.2 Read only when needed

- architecture docs;
- API/schema docs;
- database/migration docs;
- hosting/deployment docs;
- security/secrets docs;
- browser support docs;
- accepted Issue #2 evidence;
- external official docs activated by Research/Freshness Gate.

### 10.3 Do not reconstruct history unnecessarily

Normal operation must not require reading full Issue #2 Workpack.

Issue #2 exists as accepted provenance/evidence.

### 10.4 Avoid irrelevant context

Do not load:

- unrelated packages/apps/services;
- old Candidate comparisons;
- unrelated Issue threads;
- entire repository docs by default;
- external sources not needed by task.

Context size is not evidence quality.

---

## 11. Web environment contract

Each Web project should define or allow reconstruction of an environment contract.

The workflow does not freeze current versions.

### 11.1 Required environment facts

Record where materially relevant:

- runtime;
- framework/library;
- package manager;
- dependency lockfile/strategy;
- install command;
- local dev-server command;
- build command;
- unit-test command;
- API/integration/contract-test commands;
- lint command;
- typecheck command;
- static-analysis command;
- production-like build command;
- browser/E2E command;
- browser support policy;
- responsive/device targets;
- frontend/server/API/schema/database boundaries;
- background jobs/services;
- build/deploy artifact;
- preview/staging/production environment model;
- hosting/cloud/CDN/database provider where applicable;
- CI environment;
- secrets/environment-variable model.

### 11.2 Environment facts are project facts

Do not encode:

- latest browser;
- latest runtime;
- latest framework;
- latest package manager;
- current provider limits;
- current cloud/security policy;

as timeless Workflow constants.

When current facts matter, use Research/Freshness Gate.

### 11.3 No forced migration

Existing project choices remain authoritative unless Work Item explicitly changes them.

Do not force:

- JavaScript → TypeScript;
- one framework → another;
- one package manager → another;
- SPA → SSR;
- server → serverless;
- one host/provider → another;
- one E2E tool → another.

### 11.4 Client/server separation

Browser-delivered code is a public execution surface.

Private server/deployment secrets MUST NOT be embedded in browser-delivered code.

Public runtime configuration and private secrets must be distinguished explicitly.

---

## 12. Implementation discipline

### 12.1 Minimal authorized change

Implement the smallest change satisfying the Work Item.

Avoid:

- opportunistic refactors;
- dependency upgrades not required by task;
- framework migrations;
- package-manager migrations;
- build-system rewrites;
- provider migrations;
- infrastructure rewrites;
- unrelated accessibility/UX cleanup;
- unrelated database changes.

### 12.2 Respect project architecture

Before adding structure, identify:

- app/package boundaries;
- client/server split;
- API layer;
- shared contracts/schema;
- database model;
- background jobs/services;
- infrastructure/deployment model;
- test conventions;
- build conventions.

New work should fit current architecture unless Work Item explicitly authorizes change.

### 12.3 Keep contracts explicit

Changes crossing client/server/API/schema boundaries should make compatibility assumptions explicit.

Where possible:

- test contracts;
- version/migrate schema safely;
- preserve backward/forward compatibility as project policy requires;
- avoid hidden cross-layer coupling.

### 12.4 Protect secrets

Never move private secrets into a browser bundle for convenience.

Never expose production credentials to untrusted PR code.

Use least privilege and environment isolation.

---

## 13. Problems discovered during work

### 13.1 Related and inside scope

If issue:

- is directly caused by authorized change;
- is inside Semantic Scope;
- is inside Path Scope;
- requires no authority expansion;

Implementer MAY fix and report it.

### 13.2 Related but outside scope

If correction requires:

- new package/path/service;
- expanded behavior;
- API/schema/database expansion;
- infrastructure change;
- provider change;
- external mutation;
- new secret/account permission;
- material cost;

STOP and request Supervisor decision.

### 13.3 Unrelated defect

Do not fix opportunistically.

Persist/report enough evidence for later triage.

### 13.4 Security or production concern

If work reveals:

- exposed secret;
- vulnerable credential handling;
- privileged token available to untrusted code;
- destructive migration risk;
- unintended production deploy;
- DNS/CDN/hosting misconfiguration;
- unauthorized external mutation;

STOP immediately and escalate.

---

## 14. Web verification model

Verification is risk-tiered.

Work Item defines required minimum.

### 14.1 Base project-native verification

Typical ladder:

1. install/dependency integrity if needed;
2. static analysis/typecheck/lint as configured;
3. unit tests;
4. API/integration/contract tests where relevant;
5. production-like build;
6. targeted browser/E2E;
7. accessibility checks;
8. preview/staging smoke;
9. deployment verification.

Not every task requires every step.

### 14.2 Build evidence

Production-like build evidence is useful when task can affect:

- bundling;
- tree shaking;
- server/client boundary;
- environment variable injection;
- static generation;
- SSR;
- edge/serverless packaging;
- deploy artifact.

Build success remains evidence only.

### 14.3 Browser/E2E risk classifier

Browser/E2E evidence is required or indicated when change affects:

- browser APIs;
- routing/navigation;
- hydration/SSR/client transition;
- forms/user interaction;
- authentication/session behavior;
- storage/cookies;
- rendering/layout;
- feature compatibility across supported browsers;
- embedded WebViews;
- release-critical journeys;
- browser-only failures.

Use smallest matrix justified by project support policy and risk.

### 14.4 Responsive/device evidence

Use responsive/device evidence when change affects:

- viewport/layout breakpoints;
- touch/pointer behavior;
- mobile/desktop interaction differences;
- orientation;
- device-class performance/behavior;
- browser UI interaction;
- embedded/enterprise device context.

A viewport emulation is not automatically equivalent to a physical device.

### 14.5 Browser automation boundary

BROWSER AUTOMATION != COMPLETE REAL-USER UX PROOF.

Automated tests can prove specific interactions and regressions.
They cannot fully replace Human judgment for:

- visual quality;
- usability;
- content clarity;
- nuanced accessibility behavior;
- product desirability.

### 14.6 Accessibility and UX

For material UI changes:

- run project-configured automated accessibility checks when available;
- verify keyboard navigation/focus where relevant;
- verify semantic structure/labels where relevant;
- verify contrast/zoom/reflow as project policy requires;
- require Human/design/accessibility review when qualitative judgment is needed.

### 14.7 API/integration/data evidence

For server/API/schema/database changes, verify as applicable:

- request/response contract;
- authorization;
- error handling;
- migration compatibility;
- data integrity;
- idempotency;
- retry behavior;
- backward compatibility;
- rollback or forward-fix strategy.

---

## 15. Provider-neutral browser/runtime/preview/deploy evidence adapter

This adapter represents a capability boundary, not a mandatory provider.

### 15.1 Allowed implementations

Depending on project and authority:

- local browser;
- real-browser automation;
- project E2E runner;
- CI browser matrix;
- remote browser/device service;
- preview environment;
- staging environment;
- hosting/cloud/CDN deployment adapter;
- database/service sandbox;
- another authorized provider.

No one provider is mandatory.

### 15.2 Required adapter inputs

When platform evidence is required, record:

- governing Work Item;
- exact repository SHA;
- build/artifact identity;
- runtime/build environment;
- target browser/runtime;
- browser/device/responsive profile;
- client/server/API/data surfaces;
- target preview/staging/deploy environment;
- target provider/resource identifiers when applicable;
- test selection;
- retry policy;
- timeout;
- expected result;
- secret/credential authority if applicable.

### 15.3 Required adapter outputs

Return as applicable:

- pass/fail/skip;
- browser/runtime metadata;
- run ID;
- traces/screenshots/videos only when required/permitted;
- accessibility report;
- deployment ID/URL;
- artifact identity/hash;
- API/database/migration evidence;
- environment/provider metadata;
- retry history;
- deviations;
- unresolved warnings.

### 15.4 Adapter boundary

A provider result cannot issue:

- SEMANTIC_ACCEPTED;
- MERGE_ELIGIBLE;
- merge;
- product publication.

Browser/deployment evidence remains evidence.

### 15.5 Preview boundary

Preview environments:

- are optional;
- must bind to exact ref/artifact when possible;
- must use intended environment configuration;
- must not silently receive production-only secrets;
- are evidence surfaces, not product-publication approval.

### 15.6 Staging/deployment boundary

Staging or deployment operation requires explicit target/environment authority.

Technical deployment success does not create product-publication authority.

---

## 16. CI, evidence, and checkpoint discipline

### 16.1 CI goals

CI should provide reproducible evidence bound to exact SHA.

Typical Web CI may include:

- dependency setup;
- lint;
- typecheck;
- static analysis;
- unit tests;
- API/integration/contract tests;
- production-like build;
- targeted browser/E2E;
- accessibility checks;
- artifact collection;
- preview/staging deployment evidence when authorized.

### 16.2 CI exactness

Evidence should identify:

- commit SHA;
- workflow/job;
- runtime/toolchain;
- relevant package/app/service;
- browser/runtime matrix when used;
- environment when used;
- pass/fail state;
- artifact/run/deployment references.

### 16.3 CI failure

If required CI fails:

- do not ignore it;
- determine whether failure is caused by change;
- fix within scope or report blocker;
- rerun only under allowed operations.

### 16.4 CI absence

If CI is NOT CONFIGURED:

- do not claim CI PASS;
- run required project-native verification in authorized environment;
- report CI: NOT CONFIGURED.

### 16.5 Checkpoints

Persist checkpoint when:

- switching phase;
- context may be lost;
- external actor is invoked;
- fresh research changes rationale;
- preview/staging/deploy begins;
- external mutation begins;
- migration crosses irreversible boundary;
- Supervisor needs intermediate decision.

Checkpoint should include exact SHA and state.

---

## 17. Repository publication procedure

REPOSITORY_PUBLICATION is not preview deployment, production deployment, or product publication.

### 17.1 Before commit

Implementer MUST:

- review all changed paths;
- confirm Semantic Scope;
- confirm Path Scope;
- confirm no unintended configuration/migration/infrastructure files changed;
- run required verification;
- confirm secrets are not introduced;
- confirm no baseline/reference violation.

### 17.2 Commit

Use focused commit.

Avoid unrelated changes.

### 17.3 Push / branch

Push only to authorized branch.

Wrong target is STOP.

### 17.4 Pull request

Open/update authorized PR.

PR should identify:

- Work Item;
- purpose;
- exact scope;
- verification;
- environment assumptions;
- known risks;
- preview/staging/deploy state if relevant;
- evaluation/merge status.

Opening PR does not create semantic acceptance or merge eligibility.

---

## 18. Implementer handoff

Required fields:

~~~text
WEB_IMPLEMENTER_HANDOFF

WORK ITEM:
ROLE:
BRANCH:
PR:
HEAD:
BASE:

OBJECTIVE RESULT:
PASS | INCOMPLETE | BLOCKED

CHANGED PATHS:
- ...

RUNTIME/FRAMEWORK:
PACKAGE MANAGER:
BUILD/TEST CONTRACT:

AFFECTED SURFACES:
CLIENT:
SERVER/API:
SCHEMA/DATABASE:
BACKGROUND/INFRASTRUCTURE:

VERIFICATION:
- command/check:
- result:

BROWSER/E2E:
REQUIRED: YES | NO
MATRIX:
RUN/REPORT REF:
RESULT:

ACCESSIBILITY/UX:
REQUIRED: YES | NO
EVIDENCE:
HUMAN REVIEW:

PREVIEW/STAGING:
REQUIRED: YES | NO
ENVIRONMENT:
DEPLOYMENT ID/URL:
ARTIFACT/REF:
RESULT:

PRODUCTION DEPLOY:
AUTHORIZED: YES | NO
PERFORMED: YES | NO

EXTERNAL MUTATION:
USED: YES | NO
ACTIVITY REF:
TARGET:
RESULT:

SECRETS/ENVIRONMENT:
PRIVATE SECRET EXPOSED TO CLIENT: NO
SPECIAL ACCESS USED: YES | NO

CI:
PASS | FAIL | PENDING | NOT CONFIGURED

EXTERNAL ACTOR:
USED: YES | NO
ACTIVITY REF:

UNEXPECTED FINDINGS:
- ...

RISKS / UNCERTAINTIES:
- ...

MISMATCH CHECK:
PASS | FAIL

STATE:
READY_FOR_REVIEW | BLOCKED
~~~

Rules:

- report facts, not self-approval;
- include exact HEAD;
- do not claim SEMANTIC_ACCEPTED;
- never include secret values;
- stop after handoff unless later authority authorizes more work.

---

## 19. Supervisor exact-SHA review

### 19.1 Required review inputs

- governing Work Item;
- exact HEAD;
- branch/PR;
- diff;
- changed files;
- architecture compatibility;
- Acceptance Criteria;
- runtime/framework/package-manager/build facts;
- client/server/API/schema/database/infrastructure boundaries;
- verification evidence;
- CI;
- browser/E2E evidence when required;
- accessibility/UX evidence when required;
- preview/staging/deploy evidence when relevant;
- secret/environment handling;
- external mutation evidence;
- external-actor records;
- unresolved warnings.

### 19.2 Review questions

1. Does implementation satisfy Objective?
2. Does each Acceptance Criterion pass?
3. Did Implementer stay inside Semantic Scope?
4. Did Implementer stay inside Path Scope?
5. Are runtime/build facts sufficient?
6. Are client/server/API/data boundaries correct?
7. Is browser evidence sufficient for project support policy?
8. Is responsive/device evidence required and sufficient?
9. Is browser automation being overclaimed as UX proof?
10. Is accessibility evidence sufficient?
11. Are public/private config and secrets separated?
12. Are preview/staging/deploy operations within explicit authority?
13. Are external mutations within explicit authority and safely evidenced?
14. Did technical capability become implicit Workflow authority?
15. Is product publication still Human-only?
16. Does reviewed SHA match PR HEAD?
17. Are CI/test/deployment results evidence rather than approval?
18. Is any HARD VETO present?
19. Do unresolved findings require REWORK/HOLD/ESCALATE?

### 19.3 New commit after review

If HEAD changes after review, prior semantic decision does not automatically apply.

New exact-SHA review is required.

---

## 20. Formal Supervisor decisions

Only four semantic decisions exist.

### 20.1 SEMANTIC_ACCEPTED

Exact reviewed SHA satisfies Work Item intent and Acceptance Criteria.

It does NOT mean:

- MERGE_ELIGIBLE automatically;
- merged;
- canonical;
- staging promoted;
- production deployed;
- product published.

### 20.2 REWORK

Correction is required while objective generally remains valid.

REWORK must identify:

- reviewed SHA;
- defect;
- required result;
- scope;
- evidence required.

### 20.3 HOLD

Objective cannot currently progress because blocker is unresolved.

Examples:

- required browser/provider unavailable;
- required secret/account permission unavailable;
- external service blocks proof;
- migration cannot be safely executed;
- deployment environment unavailable;
- Human decision pending.

### 20.4 ESCALATE

Human/material decision required.

Examples:

- objective/scope change;
- architecture decision;
- provider/cost commitment;
- production credential/account decision;
- destructive migration decision;
- publication decision;
- material risk trade-off.

---

## 21. REWORK continuity

### 21.1 Same objective

When Objective and authorized contract remain valid:

- continue same Issue;
- continue same branch/PR unless Supervisor says otherwise;
- make focused correction commit;
- rerun affected verification;
- publish new handoff;
- obtain new exact-SHA review.

### 21.2 Exact-SHA invalidation

If SHA A received REWORK and Implementer creates SHA B:

- SHA A remains historical evidence;
- SHA B is new review target;
- no semantic status transfers automatically.

If SHA A was SEMANTIC_ACCEPTED and any new commit creates SHA B:

- SHA B is not semantically accepted until reviewed.

### 21.3 Scope-changing rework

If correction requires:

- new Objective;
- expanded Semantic Scope;
- expanded Path Scope;
- architecture change;
- new provider/account/secret permission;
- new external mutation;
- new paid-service commitment;
- changed publication authority;

STOP → Supervisor/Human decision.

---

## 22. Current-decision rule

Current valid semantic decision is:

the latest Supervisor decision explicitly associated with the current exact HEAD.

Do not use:

- older decision for another SHA;
- handoff as decision;
- CI status as decision;
- browser report as decision;
- deployment result as decision;
- external actor result as decision.

If current HEAD has no applicable decision:

state is not semantically accepted.

---

## 23. Integration and merge eligibility

After SEMANTIC_ACCEPTED, integration still requires separate checks.

Typical sequence:

READY_FOR_REVIEW
→ SEMANTIC_ACCEPTED
→ verify target branch/base
→ verify required CI/evidence
→ verify no newer conflicting change
→ verify merge authority
→ MERGE_ELIGIBLE
→ merge
→ post-merge checks if required
→ CLOSED

### 23.1 Merge eligibility checks

As applicable:

- exact reviewed HEAD still equals PR HEAD;
- target branch remains expected;
- required CI passes;
- approvals exist;
- no blocking HOLD/ESCALATE;
- no conflict or target divergence invalidates assumptions;
- repository rules allow merge;
- merge authority is present.

SEMANTIC_ACCEPTED != MERGE_ELIGIBLE.

---

## 24. Merge boundary

Implementer MUST NOT self-merge.

External actor MUST NOT gain merge authority from technical capability.

Where governing Workflow authorizes Supervisor merge, Supervisor may merge only after:

- exact-SHA semantic acceptance;
- merge-eligibility checks;
- target-state verification.

If merge authority is not demonstrable:

STOP.

---

## 25. Product publication, preview, staging, and deployment boundary

Product publication is distinct from repository publication and technical deployment.

PUBLISH = HUMAN ACTION.

### 25.1 Preview

Preview is optional.

When authorized:

- bind to exact ref/artifact;
- target intended preview environment;
- restrict secrets;
- return deployment ID/URL;
- verify expected behavior;
- record expiry/cleanup where applicable.

Preview does not create semantic approval or publication authority.

### 25.2 Staging

Staging is an environment, not an authority state.

A staging deploy must identify:

- target environment;
- exact ref/artifact;
- credential/secret boundary;
- deployment result;
- validation result.

### 25.3 Production technical deployment

A production technical deployment may be a separately authorized operation.

Even when technically authorized, it does not transfer Human publication authority.

If governing product process treats production deployment itself as publication, the technical actor must not perform it without Human publication action.

### 25.4 Hosting/cloud/CDN/database/provider access

Access to:

- host;
- cloud;
- CDN;
- DNS;
- database;
- secret manager;
- deployment platform;
- feature-flag platform;

is technical capability only.

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

### 25.5 Secrets/environment boundary

Distinguish:

- browser-public configuration;
- server-private secrets;
- CI credentials;
- deployment credentials;
- environment-scoped values;
- local developer secrets.

Rules:

- private server/deploy secrets MUST NOT enter browser bundles;
- untrusted PR code MUST NOT silently receive privileged production credentials;
- least privilege applies;
- secret values must not be copied into handoffs/logs.

Short-lived/OIDC authentication may be preferred where supported, but it is not a universal requirement.

### 25.6 Publication

Actual product publication remains Human action.

If the distinction between technical deployment and publication is unclear:

STOP → Human/Supervisor decision.

---

## 26. Implementer session recovery

A fresh Implementer does not reconstruct state from prior chat.

Read GitHub.

### 26.1 Minimum recovery tuple

Recover:

- repository;
- active Work Item;
- role;
- current authority;
- branch/ref;
- exact HEAD;
- PR;
- Objective;
- Acceptance Criteria;
- Semantic Scope;
- Path Scope;
- Verification;
- latest applicable Supervisor decision;
- reviewed SHA;
- runtime/framework/package-manager/build contract;
- client/server/API/schema/database boundaries;
- browser support/evidence state;
- accessibility/UX state;
- preview/staging/deploy state;
- secrets/environment constraints;
- external mutation state;
- external-actor activity state;
- unresolved REWORK/HOLD/ESCALATE;
- next authorized action.

### 26.2 Recovery rule

If current HEAD differs from SHA named in latest semantic decision:

do not assume acceptance.

### 26.3 Recovery template

~~~text
WEB_IMPLEMENTER_RECOVERY

REPOSITORY:
WORK ITEM:
ROLE:
AUTHORITY:
BRANCH/REF:
HEAD:
PR:
OBJECTIVE:
SEMANTIC SCOPE:
PATH SCOPE:
VERIFICATION:
RUNTIME/FRAMEWORK:
PACKAGE MANAGER:
BUILD/TEST CONTRACT:
CLIENT/SERVER/API/DATA:
BROWSER EVIDENCE STATE:
ACCESSIBILITY/UX STATE:
PREVIEW/STAGING/DEPLOY STATE:
SECRETS/ENVIRONMENT STATE:
EXTERNAL MUTATION STATE:
LATEST SUPERVISOR DECISION:
REVIEWED SHA:
EXTERNAL ACTIVITY:
BLOCKER / REWORK:
NEXT AUTHORIZED ACTION:
MISMATCH CHECK: PASS | FAIL
~~~

---

## 27. Supervisor session recovery

### 27.1 Minimum Supervisor recovery set

- Human intent/current governing Issue;
- active Work Item;
- exact PR HEAD;
- target branch;
- Work Item contract;
- repository instructions;
- latest Implementer handoff;
- verification evidence;
- CI;
- runtime/build facts;
- client/server/API/data boundaries;
- browser/accessibility evidence;
- preview/staging/deploy evidence;
- secrets/environment constraints;
- external mutations;
- external actor records;
- latest Supervisor decision/reviewed SHA;
- unresolved blocker/REWORK/HOLD/ESCALATE.

### 27.2 Supervisor mismatch rule

If repository, Work Item, actor, authority, target, or SHA mismatches:

STOP.

Do not reinterpret another project's task into current one.

---

## 28. Human role

Human is not merely emergency fallback.

Human owns decisions requiring human product/account authority.

Typical Human-only or Human-reserved actions:

- credentials/MFA;
- production account/security confirmation;
- material scope/product change;
- architecture/Workflow adoption where required;
- paid provider commitment;
- destructive/high-impact external mutation decisions;
- production/publication decisions;
- PUBLISH / product publication.

Workflow should automate permitted technical work while minimizing Human interruption.

Do not ask Human to perform routine mechanical work an authorized technical actor can safely perform.

---

## 29. Research/Freshness Gate + Strategic Rationale

Issue #2 research is accepted evidence library.

Do not repeat broad research by default.

### 29.1 When Research/Freshness Gate activates

Activate when material decision depends on current external fact, such as:

- browser compatibility;
- browser API support;
- runtime/framework/package-manager behavior;
- current provider capability;
- current hosting/deployment limitation;
- current CDN/cloud/database behavior;
- security guidance materially affecting implementation;
- provider pricing/quota when cost authority matters;
- deprecation/removal changing feasible architecture.

Do not activate for curiosity.

### 29.2 Research behavior

When activated:

- prefer official/primary sources;
- record date/version scope;
- distinguish fact from inference;
- avoid timeless wording for volatile facts;
- cite evidence in Work Item or rationale;
- stop if research reveals architecture/authority change requiring decision.

### 29.3 Evidence categories

Use:

- PROJECT FACT
- EXTERNAL VERIFIED FACT
- EMPIRICAL OBSERVATION
- INFERENCE
- RECOMMENDATION
- UNKNOWN

### 29.4 Supervisor verification

Supervisor reviews whether:

- research was required;
- sources are appropriate;
- conclusions follow from evidence;
- authority remains unchanged.

### 29.5 Strategic Rationale

Persist STRATEGIC_RATIONALE when material technical choice affects architecture, browser support, provider use, verification, security, deployment, data migration, or maintainability.

~~~text
STRATEGIC_RATIONALE

DECISION:
CONTEXT:
OPTIONS CONSIDERED:
PROJECT FACTS:
EXTERNAL FACTS:
INFERENCES:
WHY THIS OPTION:
RISKS:
FRESHNESS / VERSION SCOPE:
AUTHORITY IMPACT:
NONE | REQUIRES DECISION
~~~

Research informs authority decisions.
It does not create authority.

---

## 30. Optional external-actor protocol

An external actor exists only for a concrete missing capability.

Every invocation MUST have a durable GitHub activity record.

Required lifecycle:

request
→ authority
→ execution
→ evidence
→ result
→ stop/escalation

### 30.1 Required activity record

~~~text
EXTERNAL_ACTOR_ACTIVITY

ACTIVITY_ID:
GOVERNING_WORK_ITEM:
ACTOR_TYPE:
CAPABILITY:
OBJECTIVE:
PRECONDITIONS:
AUTHORIZED_OPERATIONS:
FORBIDDEN_OPERATIONS:
EXPECTED_BASELINE:
EVIDENCE_REQUIRED:
RESULT:
STOP_CONDITIONS:
ESCALATION_PATH:
STATUS:
~~~

### 30.2 Capability

Define one concrete capability, for example:

- browser/device matrix;
- accessibility/design review;
- security review;
- preview/staging deployment;
- hosting/cloud/CDN operation;
- database migration;
- DNS/configuration mutation;
- bounded production technical deployment that does not transfer publication authority.

### 30.3 Preconditions

Include:

- governing Work Item;
- exact ref/SHA;
- artifact hash where applicable;
- runtime/build environment;
- browser matrix;
- target environment/provider/resource;
- credential authority;
- cost/quota authority;
- observable external baseline;
- rollback prerequisites when applicable.

### 30.4 Authorized operations

Enumerate exact allowed operations.

Default deny outside list.

### 30.5 Forbidden operations

At minimum, unless separately authorized:

- Workflow modification;
- Objective change;
- Acceptance Criteria change;
- Semantic Scope expansion;
- Path Scope expansion;
- baseline/reference modification;
- unrelated source changes;
- self-approval;
- SEMANTIC_ACCEPTED;
- MERGE_ELIGIBLE;
- merge;
- product publication;
- unauthorized production deploy;
- unauthorized secret/account/billing change;
- new paid-service/provider commitment;
- unauthorized retry/workaround after STOP.

### 30.6 Expected baseline / SHA gate

Activity must bind to:

- Work Item;
- exact SHA/ref;
- artifact identity/hash where applicable;
- runtime/build configuration;
- browser/environment matrix;
- target provider/resource;
- current Acceptance Criteria relevant to activity.

If baseline changes:

STOP or obtain renewed authority.

### 30.7 Evidence returned

Return only evidence required:

- run/deployment/migration ID;
- environment/browser metadata;
- pass/fail/skip;
- logs/reports/artifact references;
- traces/screenshots when appropriate;
- before/after state for mutations;
- rollback result when applicable;
- retries/deviations;
- unresolved warnings.

### 30.8 STOP conditions

STOP when:

- input SHA differs;
- required credential/account/cost permission is missing;
- operation exceeds authority/scope;
- Objective/Acceptance Criteria/Semantic Scope/Path Scope would need to change;
- target environment/provider differs;
- evidence is invalid/incomplete;
- mutation baseline is not observable;
- rollback/forward-fix is required but unavailable where necessary;
- publication would be required;
- retry could create unsafe/duplicate external effect.

### 30.9 Escalation

Return:

- exact blocker;
- evidence;
- requested decision;
- no unauthorized workaround.

### 30.10 Durable result and closure

Persist RESULT and STATUS.

Provider-only or chat-only trace is insufficient.

### 30.11 External platform mutation protocol

Potential external mutations include:

- database migrations;
- DNS;
- CDN/cache;
- hosting configuration;
- environment variables;
- cloud resources;
- API/provider configuration;
- feature flags;
- deployment rollback.

Every mutation requires:

- exact target;
- governing Work Item;
- exact ref/artifact where relevant;
- observable before state;
- authorized operation;
- expected after state;
- evidence;
- rollback/forward-fix strategy where applicable;
- STOP conditions.

External mutation authority does not imply repository, semantic, merge, or publication authority.

### 30.12 Historical AI Studio Issue #53 compatibility rule

Frozen baseline contains a specific historical compatibility rule for earlier Issue #53 / AI Studio quota state.

That historical state is NOT a reusable Web operational rule.

It is intentionally not imported into normative Web operation.

Its reusable safety functions are preserved through:

- HOLD;
- current-decision rule;
- external-actor gate;
- recovery;
- PUBLISH = HUMAN ACTION;
- TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

This is the only baseline area classified NOT_APPLICABLE_WITH_JUSTIFICATION by accepted Web matrix.

---

## 31. Technical permission != Workflow authority

Exact invariant:

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

### 31.1 Repository/product-code writes

Actor may write repository/product code only when governing Work Item authorizes:

- semantic change;
- path;
- operation.

Provider/browser/deploy/secret access does not expand repository write authority.

### 31.2 External actor escalation

Escalating task to external actor does not transfer:

- Supervisor authority;
- Human authority;
- semantic-decision authority;
- merge authority;
- publication authority.

### 31.3 Credentials/provider roles

Possession of:

- deployment token;
- cloud role;
- hosting role;
- CDN token;
- DNS permission;
- database credential;
- secret-manager access;
- provider admin role;

does not imply permission to exercise every available operation.

### 31.4 Cost

Technical access to paid provider does not authorize cost.

Material provider cost requires governing permission.

---

## 32. Web-specific platform deltas

Web remains Web-specific.

Do not force mobile symmetry.

### 32.1 Runtime/framework/package manager

Runtime/framework/library/package manager are project facts.

Workflow does not mandate one stack.

### 32.2 Build/test/lint/typecheck/static analysis

Use project-native commands.

A project may have some or all of:

- lint;
- formatting check;
- typecheck;
- static analysis;
- unit tests;
- API/integration tests;
- build;
- E2E.

No universal command name is assumed.

### 32.3 Browser/runtime evidence

Browser evidence uses project support targets and risk.

No one browser matrix is universal.

No one E2E tool is mandatory.

### 32.4 Responsive/device evidence

Responsive/device checks are risk-triggered.

Emulated viewport evidence is useful but may require real device/browser verification for material behavior.

### 32.5 Client/server/API/schema/database boundaries

Web tasks may cross several execution/data surfaces.

Authority and verification must make those boundaries explicit.

### 32.6 Preview/staging/deploy

Preview and staging are technical evidence environments.

Deployment is a technical operation.

Neither creates semantic approval or publication authority.

### 32.7 Hosting/cloud/CDN/provider

Provider-neutral governance is preferred where practical.

Provider-specific adapters are acceptable when project selects them.

No provider becomes canonical Workflow dependency by example.

### 32.8 Secrets/environment

No universal mobile signing gate exists.

Instead, protect:

- browser/server separation;
- secret exposure;
- environment scoping;
- CI privilege;
- deployment privilege;
- provider credentials.

### 32.9 External mutations

Database/DNS/CDN/hosting/config/environment/cloud mutations are external operations and require explicit authority/evidence.

### 32.10 Accessibility/UX/browser compatibility

Automated evidence is valuable but incomplete for qualitative UX/accessibility judgment.

Current compatibility facts remain freshness-gated.

### 32.11 Non-symmetry exclusions

Do not import Android mechanics as Web requirements:
- Gradle/AGP;
- compileSdk/targetSdk/minSdk;
- APK/AAB;
- Android API/ABI;
- Android emulator/Gradle Managed Device;
- Firebase Test Lab;
- Play Console/Play signing;
- Compose/View/Java migration rules.

Do not import iOS mechanics as Web requirements:
- macOS/Xcode as universal requirement;
- Xcode project/workspace/scheme/configuration model;
- Apple Simulator/physical-device semantics;
- certificates/provisioning profiles/entitlements;
- archive/export semantics;
- App Store Connect/TestFlight;
- Swift/Objective-C/SwiftUI/UIKit migration rules.

These names appear here only to prohibit cross-platform leakage.

---

## 33. Operational Definition of Done

A Web Work Item is ready for Supervisor review only when applicable checks are complete.

The Web workflow itself is operationally complete only if all tests in section 34 pass.

### 33.1 Work Item implementation DoD

For a normal Work Item:

- repository/Work Item/role/authority/Base match;
- Objective addressed;
- Acceptance Criteria evidenced;
- Semantic Scope respected;
- Path Scope respected;
- runtime/build facts sufficient;
- client/server/API/data boundaries explicit;
- implementation bounded;
- required build/test/lint/typecheck/static evidence complete;
- required browser/E2E evidence complete;
- required accessibility/UX evidence complete;
- required preview/staging/deploy evidence complete;
- secrets/environment handled safely;
- required external mutations evidenced;
- required CI state reported;
- external actor record complete if used;
- full diff reviewed;
- REPOSITORY_PUBLICATION correct;
- exact HEAD identified;
- handoff persisted;
- no self-approval;
- no product publication by technical actor.

---

## 34. Acceptance tests for this workflow

### TEST A — Baseline coverage

1. Read accepted Web Baseline Adaptation Matrix.
2. Verify all 71 classified rows have implemented target.
3. Verify all six Work Item child fields are explicit.
4. Verify only baseline 29.12 is NOT_APPLICABLE_WITH_JUSTIFICATION.
5. Verify no normative row is silently grouped away.

Expected: PASS.

Failure is HARD VETO.

### TEST B — Happy path

Representative scenario:

1. Human states bounded Web intent.
2. Supervisor creates six-field Work Item.
3. Implementer bootstraps and verifies Base/scope.
4. Implementer changes authorized Web code.
5. Project-native build/test/lint/typecheck evidence passes as required.
6. Risk classifier selects targeted browser/E2E evidence.
7. Browser evidence passes.
8. Preview is created only if useful/authorized.
9. Implementer publishes commit/PR.
10. Handoff names exact SHA.
11. Supervisor reviews exact SHA.
12. Supervisor issues SEMANTIC_ACCEPTED.
13. Integration checks separately establish MERGE_ELIGIBLE.
14. Authorized merge occurs.
15. Product publication, if any, remains Human action.

Expected:
lifecycle can run from this document without reading Issue #2.

### TEST C — REWORK exact-SHA invalidation

1. Supervisor reviews SHA A.
2. Supervisor issues REWORK.
3. Implementer fixes same objective in same Issue/branch/PR.
4. New HEAD is SHA B.
5. Prior review of SHA A does not apply to SHA B.
6. Verification reruns as required.
7. New handoff names SHA B.
8. Supervisor reviews SHA B.

Expected:
no semantic acceptance carries automatically across SHA change.

### TEST D — Authority adversarial

Cases:

1. Implementer has production hosting credentials.
   Expected: cannot product-publish by inference.

2. External actor can deploy production.
   Expected: cannot self-approve or publish product.

3. CI is green.
   Expected: cannot issue SEMANTIC_ACCEPTED.

4. Implementer can edit authorized infrastructure path.
   Expected: cannot make unrelated semantic or provider mutation.

5. Actor has database/DNS/CDN credentials.
   Expected: cannot mutate without explicit operation authority.

6. Preview/staging deployment succeeds.
   Expected: does not imply production/publication approval.

7. Supervisor issued SEMANTIC_ACCEPTED.
   Expected: merge eligibility still checked separately.

### TEST E — STOP / escalation

Cases:

- wrong repository;
- wrong Work Item;
- wrong Base;
- wrong PR target;
- missing Path Scope;
- implementation requires architecture change;
- production secret access required but unauthorized;
- paid provider required but cost unauthorized;
- destructive migration lacks rollback/decision;
- current browser/provider/security fact is material but unknown;
- external actor baseline mismatches;
- publication would require technical actor to exceed authority.

Expected:
STOP / HOLD / ESCALATE as appropriate.

### TEST F — Session recovery

Fresh Implementer reconstructs:

- Issue;
- branch/ref;
- HEAD;
- PR;
- scope;
- environment;
- client/server/API/data boundaries;
- browser evidence;
- deploy state;
- secret constraints;
- latest decision;
- next action.

Fresh Supervisor reconstructs equivalent durable review state.

Expected:
no prior chat transcript required.

### TEST G — External-actor durability

Create representative deployment/platform activity.

Verify GitHub records:

request
→ authority
→ execution
→ evidence
→ result
→ stop/escalation.

Expected:
future authorized session can reconstruct what happened and why.

### TEST H — Web platform delta

Cases:

1. Production-like build passes.
   Expected: do not claim browser compatibility automatically.

2. Browser automation passes.
   Expected: do not claim complete UX/accessibility proof.

3. One hosting/preview provider is unavailable.
   Expected: workflow remains valid if another authorized capability fits; provider is not canonical.

4. Preview/staging/deploy succeeds.
   Expected: product publication remains Human-only.

5. Client code can access environment variable.
   Expected: private server/deploy secret must not be exposed to browser bundle.

6. Database/DNS/CDN mutation is technically possible.
   Expected: explicit operation authority and durable evidence are required.

7. Existing framework/package manager differs from examples.
   Expected: no forced migration.

### TEST I — Standalone use

Remove Issue #2 research artifacts from normal execution scenario.

Provide only:

- repository;
- active Work Item;
- this document;
- project docs explicitly referenced by Work Item.

Expected:
Implementer and Supervisor can run normal lifecycle.

Issue #2 remains provenance, not procedure dependency.

### TEST J — Summary regression

Create short summary/checklist from this workflow.

Verify summary does not become normative source and does not weaken:

- six-field Work Item;
- Semantic Scope + Path Scope;
- exact-SHA review;
- decision vocabulary;
- REWORK continuity;
- SEMANTIC_ACCEPTED != MERGE_ELIGIBLE;
- PUBLISH = HUMAN ACTION;
- session recovery;
- HARD VETO;
- TECHNICAL CAPABILITY != WORKFLOW AUTHORITY;
- browser/UX evidence boundaries;
- secrets/environment boundaries;
- deployment/publication boundary;
- external-actor durability.

If invariant disappears/weakens:

REWORK / HARD VETO.

---

## 35. Execution templates and checklists

### 35.1 Supervisor Work Item checklist

~~~text
WEB WORK ITEM CREATION

HUMAN INTENT:
OBJECTIVE:
ACCEPTANCE CRITERIA:
AUTHORIZED SEMANTIC SCOPE:
AUTHORIZED PATH SCOPE:
CLIENT/SERVER/API/DATA SURFACES:
ALLOWED EXTERNAL OPERATIONS:
ALLOWED SECRET/ENVIRONMENT OPERATIONS:
FORBIDDEN OPERATIONS:
RELEVANT SOURCES:
RUNTIME/FRAMEWORK:
PACKAGE MANAGER:
BUILD/TEST CONTRACT:
BROWSER SUPPORT:
E2E TRIGGER:
ACCESSIBILITY/UX TRIGGER:
PREVIEW/STAGING TRIGGER:
DEPLOYMENT TRIGGER:
EXTERNAL MUTATION TRIGGER:
CI REQUIREMENT:
CREDENTIAL/COST REQUIREMENT:
BASE:
BRANCH/PR MODEL:
STOP CONDITIONS:
~~~

### 35.2 Implementer bootstrap checklist

~~~text
WEB IMPLEMENTER BOOTSTRAP

REPOSITORY MATCH: YES | NO
WORK ITEM MATCH: YES | NO
ROLE MATCH: YES | NO
AUTHORITY VERIFIED: YES | NO
BASE VERIFIED: YES | NO
TARGET VERIFIED: YES | NO
OBJECTIVE UNDERSTOOD: YES | NO
SEMANTIC SCOPE VERIFIED: YES | NO
PATH SCOPE VERIFIED: YES | NO
SOURCES LOADED: YES | NO
VERIFICATION UNDERSTOOD: YES | NO
RUNTIME/FRAMEWORK KNOWN: YES | NO
PACKAGE MANAGER KNOWN: YES | NO
BUILD/TEST CONTRACT SUFFICIENT: YES | NO | UNKNOWN
CLIENT/SERVER/API/DATA BOUNDARIES KNOWN: YES | NO
BROWSER/E2E REQUIRED: YES | NO | UNKNOWN
ACCESSIBILITY/UX REQUIRED: YES | NO | UNKNOWN
PREVIEW/STAGING REQUIRED: YES | NO
DEPLOYMENT REQUIRED: YES | NO
SECRETS/ENVIRONMENT ACCESS REQUIRED: YES | NO
EXTERNAL MUTATION REQUIRED: YES | NO
CREDENTIAL/COST ACTION REQUIRED: YES | NO
PRODUCT PUBLISH AUTHORITY FOR TECHNICAL ACTOR: NO
MISMATCH CHECK: PASS | FAIL
STATE: READY | BLOCKED
~~~

### 35.3 Web environment contract template

~~~text
WEB ENVIRONMENT CONTRACT

APP/PACKAGE/SERVICE:
RUNTIME:
FRAMEWORK/LIBRARY:
PACKAGE MANAGER:
LOCKFILE/DEPENDENCY STRATEGY:
INSTALL COMMAND:
DEV COMMAND:
BUILD COMMAND:
UNIT TEST COMMAND:
API/INTEGRATION COMMAND:
LINT COMMAND:
TYPECHECK COMMAND:
STATIC ANALYSIS COMMAND:
PRODUCTION-LIKE BUILD:
E2E/BROWSER COMMAND:
BROWSER SUPPORT:
RESPONSIVE/DEVICE TARGETS:
CLIENT/SERVER/API/SCHEMA/DATABASE:
BACKGROUND/INFRASTRUCTURE:
BUILD/DEPLOY ARTIFACT:
PREVIEW/STAGING/PRODUCTION MODEL:
HOSTING/CLOUD/CDN/DATABASE PROVIDERS:
CI ENVIRONMENT:
SECRETS/ENVIRONMENT MODEL:
NOTES / UNKNOWN:
~~~

Unknown values are allowed if not material.
Do not invent them.

### 35.4 Web risk classifier template

~~~text
WEB RISK CLASSIFIER

CHANGE AFFECTS:
[ ] pure server/domain logic
[ ] browser client behavior
[ ] browser API compatibility
[ ] rendering/hydration/routing
[ ] responsive/device behavior
[ ] accessibility/UX
[ ] API/contract
[ ] schema/database/migration
[ ] background jobs/services
[ ] build/bundling
[ ] secrets/environment
[ ] preview/staging
[ ] production deployment
[ ] DNS/CDN/hosting/cloud
[ ] current browser/framework/provider policy

BASE PROJECT-NATIVE EVIDENCE SUFFICIENT:
YES | NO

BROWSER/E2E REQUIRED:
YES | NO

RESPONSIVE/REAL DEVICE REQUIRED:
YES | NO

ACCESSIBILITY/HUMAN UX REVIEW REQUIRED:
YES | NO

PREVIEW/STAGING EVIDENCE REQUIRED:
YES | NO

DEPLOYMENT EVIDENCE REQUIRED:
YES | NO

EXTERNAL MUTATION REQUIRED:
YES | NO

RATIONALE:
...
~~~

### 35.5 Browser/runtime evidence template

~~~text
WEB BROWSER / RUNTIME EVIDENCE

WORK ITEM:
SHA:
APP/PACKAGE/SERVICE:
BUILD ARTIFACT:
ARTIFACT HASH:
RUNTIME:
BROWSER:
BROWSER VERSION/CHANNEL IF MATERIAL:
DEVICE/VIEWPORT:
TEST SELECTION:
RUN ID:
RESULT:
TRACE/REPORT REF:
RETRIES/DEVIATIONS:
UNRESOLVED WARNING:
~~~

### 35.6 Preview/staging/deploy evidence template

~~~text
WEB PREVIEW / STAGING / DEPLOY EVIDENCE

WORK ITEM:
SHA:
ARTIFACT:
ARTIFACT HASH:
ENVIRONMENT:
PROVIDER:
TARGET RESOURCE:
DEPLOYMENT ID:
URL:
AUTHORIZED OPERATION:
SECRETS/ENVIRONMENT CONTEXT:
SMOKE/VERIFICATION:
RESULT:
ROLLBACK REQUIRED: YES | NO
ROLLBACK REF:
PRODUCT PUBLICATION AUTHORIZED TO TECHNICAL ACTOR: NO
~~~

### 35.7 External mutation evidence template

~~~text
WEB EXTERNAL MUTATION EVIDENCE

WORK ITEM:
SHA/ARTIFACT:
TARGET SYSTEM:
TARGET RESOURCE:
BEFORE STATE REF:
AUTHORIZED MUTATION:
EXPECTED AFTER STATE:
ROLLBACK/FORWARD-FIX:
EXECUTION ID:
RESULT:
AFTER STATE REF:
UNRESOLVED WARNING:
PUBLICATION AUTHORITY TRANSFERRED: NO
~~~

### 35.8 Implementer handoff template

Use section 18.

### 35.9 Supervisor review template

~~~text
WEB_SUPERVISOR_REVIEW

WORK ITEM:
PR:
REVIEWED SHA:
BASE:
DIFF/SCOPE: PASS | FAIL
ACCEPTANCE CRITERIA: PASS | FAIL
RUNTIME/BUILD CONTRACT: SUFFICIENT | INSUFFICIENT
CLIENT/SERVER/API/DATA BOUNDARIES: PASS | FAIL
BUILD/TEST/LINT/TYPECHECK: PASS | FAIL | N/A
BROWSER/E2E: PASS | FAIL | N/A
ACCESSIBILITY/UX: PASS | FAIL | N/A
PREVIEW/STAGING/DEPLOY: PASS | FAIL | N/A
SECRETS/ENVIRONMENT: PASS | FAIL | N/A
EXTERNAL MUTATION: PASS | FAIL | N/A
CI: PASS | FAIL | PENDING | NOT CONFIGURED
AUTHORITY BOUNDARIES: PASS | FAIL
PUBLICATION BOUNDARY: PASS | FAIL
EXTERNAL ACTOR RECORD: PASS | FAIL | N/A
HARD VETO: NONE | PRESENT
FINDINGS:
DECISION:
SEMANTIC_ACCEPTED | REWORK | HOLD | ESCALATE
~~~

### 35.10 REWORK template

~~~text
WEB_REWORK

WORK ITEM:
REVIEWED SHA:
PROBLEM:
REQUIRED RESULT:
SCOPE:
SEMANTIC SCOPE CHANGED: NO | YES -> ESCALATE
PATH SCOPE CHANGED: NO | YES -> AUTHORITY REQUIRED
EXTERNAL OPERATION AUTHORITY CHANGED: NO | YES -> AUTHORITY REQUIRED
EVIDENCE REQUIRED:
NEXT EXPECTED HEAD:
STOP CONDITIONS:
~~~

### 35.11 Recovery template

Use sections 26 and 27.

### 35.12 External actor template

Use section 30.1.

---

## 36. Provenance, maintenance, and lossless derivation

### 36.1 This document is derived, not invented from scratch

The document preserves functional baseline and applies Web adaptations justified by accepted evidence.

### 36.2 Maintenance rule

When this workflow changes:

1. identify governing Work Item;
2. classify change relative to accepted architecture;
3. verify baseline functions remain covered;
4. verify Web platform deltas remain valid;
5. activate Research/Freshness Gate only for material volatile facts;
6. run acceptance tests;
7. run internal-reference integrity check;
8. obtain exact-SHA Supervisor review.

### 36.3 Lossless derivation rule

No later:

- synopsis;
- handoff;
- checklist;
- presentation;
- README excerpt;
- generated prompt;

may silently replace this document as normative Web workflow.

A summary MAY point to this document.

A summary MUST NOT weaken it.

### 36.4 Architecture changes

If maintaining Web requires changing:

- Workflow Document Contract;
- baseline adaptation classifications;
- ADR decision;
- role authority model;
- state vocabulary;
- publication boundary;

STOP platform work and return to architecture authority.

Do not patch architecture defects only inside Web.

### 36.5 Current facts

Do not hardcode volatile platform/provider facts into Workflow semantics.

Keep current versions/policies in:

- project configuration;
- Work Item;
- evidence;
- Strategic Rationale;
- release/deployment checklist;

as appropriate.

---

# Appendix A — Baseline implementation trace

This appendix demonstrates implementation of the accepted Web Baseline Adaptation Matrix.

The matrix remains the authoritative section-by-section adaptation record.
This appendix is an execution cross-check, not a second matrix authority.

| Baseline item | Classification | Implemented here |
|---|---|---|
| Document header / status / provenance | ADAPT | §0 |
| Estado de procedencia | EXTEND | §0, §36 |
| 1. Objetivo | ADAPT | §1 |
| 2. Principio fundamental | PRESERVE | §2 |
| 3. Responsabilidades | PRESERVE | §3 |
| 3.1 Chat Web GPT | PRESERVE | §3.2 |
| 4. Agente implementador | EXTEND | §3.3 |
| 5. GitHub | PRESERVE | §3.4–3.5 |
| 6. Documentación del proyecto | ADAPT | §10, §36 |
| 7. Unidad de trabajo: GitHub Issue | PRESERVE | §5 |
| Objective | PRESERVE | §5.1 |
| Acceptance Criteria | EXTEND | §5.2 |
| Authorized Scope | PRESERVE | §5.3 |
| Relevant Sources | ADAPT | §5.4 |
| Verification | ADAPT | §5.5 |
| Base | PRESERVE | §5.6 |
| 8. Dos tipos de scope | PRESERVE | §6 |
| Semantic Scope | PRESERVE | §6.1 |
| Path Scope | PRESERVE | §6.2 |
| 9. Flujo completo | ADAPT | §7 |
| Fase A — intención | PRESERVE | §8.1 |
| Fase B — creación del Work Item | PRESERVE | §8.2 |
| 10. Inicio del Agente implementador | PRESERVE | §9 |
| 11. Bootstrap del Agente implementador | EXTEND | §9.1–9.2 |
| 12. Política de lectura | ADAPT | §10 |
| 13. Implementación | EXTEND | §12 |
| 14. Problemas descubiertos durante el trabajo | PRESERVE | §13 |
| 15. Verificación local | ADAPT | §14–15 |
| 16. Publicación | ADAPT | §17 |
| 17. Handoff del Agente implementador | EXTEND | §18 |
| 18. Revisión de Chat Web GPT | EXTEND | §19 |
| 19. Significado de las decisiones | PRESERVE | §20 |
| SEMANTIC_ACCEPTED | PRESERVE | §20.1 |
| REWORK | PRESERVE | §20.2 |
| HOLD | PRESERVE | §20.3 |
| ESCALATE | PRESERVE | §20.4 |
| 20. REWORK | PRESERVE | §21 |
| 21. Decisión vigente | PRESERVE | §22 |
| 22. CI | ADAPT | §16 |
| 23. Integración | PRESERVE | §23 |
| 24. Merge | PRESERVE | §24 |
| 25. Cambio de sesión del Agente implementador | EXTEND | §26 |
| 26. Cambio de sesión de Chat Web GPT | EXTEND | §27 |
| 27. Rol del humano | EXTEND | §28, §25 |
| 28. Reglas esenciales | EXTEND | §2 |
| 29. AI_STUDIO_OPERATOR — fallback excepcional por escalamiento verificado | ADAPT | §30 |
| 29.1 Permission Matrix | ADAPT | §30.4–30.5 |
| 29.2 Gate universal de escalamiento AI Studio | ADAPT | §30.2–30.3 |
| 29.3 Inicio: AI_STUDIO_REQUEST y modos técnicos | ADAPT | §30.1–30.4 |
| 29.4 SHA Gate y evidencia | EXTEND | §30.6–30.7 |
| 29.5 Ventana única de intervención | ADAPT | §30.5 |
| 29.6 Clasificación, seguridad operacional y recuperación | ADAPT | §30.7–30.10 |
| 29.7 Publicación — exclusiva del Humano | PRESERVE | §25 |
| 29.8 RESEARCH_GATE y SPIKE_READ_ONLY | ADAPT | §29 |
| 29.9 Regla absoluta de no escritura de repositorio/product-code | ADAPT | §30.5 |
| 29.10 AI_STUDIO_REPORT y STOP obligatorio | ADAPT | §30.7–30.10 |
| 29.11 Fallback de mutación externa de plataforma | ADAPT | §30.11, §32.9 |
| 29.12 Compatibilidad operacional inmediata — Issue #53 | NOT_APPLICABLE_WITH_JUSTIFICATION | §30.12, Appendix B |
| 30. RESEARCH_GATE + STRATEGIC_RATIONALE | PRESERVE | §29 |
| 30.1 Cuándo se activa RESEARCH_GATE | ADAPT | §29.1 |
| 30.2 Investigación y evidencia | ADAPT | §29.2–29.3 |
| 30.3 Verificación del Supervisor | PRESERVE | §29.4 |
| 30.4 STRATEGIC_RATIONALE | PRESERVE | §29.5 |
| 30.5 Aplicación por rol y límites de autoridad | PRESERVE | §29.5, §31 |
| 31. TECHNICAL PERMISSION != WORKFLOW AUTHORITY | PRESERVE | §31 |
| 31.1 Escritura de repositorio/product-code | PRESERVE | §31.1 |
| 31.2 Escalación AI Studio | ADAPT | §31.2 |
| Resultado | ADAPT | Result |
| Apéndice A — Provenance de mejoras consolidadas | ADAPT | Appendix B |
| Apéndice B — Handover canónico | ADAPT | §0, §36 |
| Apéndice C — Matriz completa de trazabilidad del baseline | EXTEND | Appendix A, §33–34 |

Coverage:

- accepted matrix rows: 71;
- rows represented in this trace: 71;
- missing rows: 0;
- silently grouped normative Work Item fields: 0;
- NOT_APPLICABLE_WITH_JUSTIFICATION: exactly 1, baseline 29.12 historical Issue #53 compatibility rule.

---

# Appendix B — Accepted Web evidence provenance

This appendix preserves provenance without making Issue #2 an execution dependency.

Accepted evidence used conceptually includes:

1. Web Capability Matrix
   - framework-neutral governance;
   - project build/test contract;
   - browser/E2E;
   - accessibility;
   - preview;
   - secrets;
   - frontend/backend boundaries;
   - provider-neutral deployment.

2. Web Evidence
   - browser compatibility;
   - browser automation;
   - CI evidence;
   - deployment-environment gates;
   - OIDC/least privilege;
   - untrusted PR credential isolation;
   - WCAG/human-evaluation boundary;
   - preview as evidence surface.

3. Web Candidate 4
   - framework-neutral, risk-tiered workflow;
   - project-native build/test adapter;
   - browser/E2E risk trigger;
   - accessibility/human UX boundary;
   - preview/deploy boundary;
   - secrets/security controls.

4. Common Governance Core
   - six-field Work Item;
   - Semantic Scope + Path Scope;
   - exact-SHA Supervisor review;
   - formal decision vocabulary;
   - same-objective REWORK;
   - SEMANTIC_ACCEPTED != MERGE_ELIGIBLE;
   - PUBLISH = HUMAN ACTION;
   - GitHub recovery;
   - HARD VETO.

5. External Actor Interface
   - TECHNICAL CAPABILITY != WORKFLOW AUTHORITY;
   - durable GitHub activity;
   - request → authority → execution → evidence → result → stop/escalation;
   - actor does not self-approve, merge, or publish.

6. Platform Deltas
   - project-selected runtime/build system;
   - browser/E2E/real-browser/device evidence;
   - provider-specific deployment;
   - no universal mobile-style signing gate;
   - high provider neutrality.

7. Adversarial Audit
   - publication-authority defect history preserved;
   - Human publication invariant restored;
   - evidence cannot override authority.

8. Issue #8 architecture and Web matrix
   - standalone document requirement;
   - source precedence;
   - lossless derivation;
   - complete 71-row matrix;
   - short BUILD → REVIEW → focused REWORK closure loop.

---

# Result

This workflow operationalizes Web using the full inherited lifecycle plus justified Web adaptation.

Normal execution is:

Human
→ Supervisor
→ bounded GitHub Work Item
→ Implementer bootstrap
→ runtime/client-server context reconstruction
→ bounded implementation
→ project-native build/test/lint/typecheck
→ browser/E2E/accessibility evidence when risk requires
→ preview/staging/deployment evidence when explicitly authorized
→ external mutation evidence when explicitly authorized
→ evidence bundle
→ REPOSITORY_PUBLICATION
→ Implementer handoff
→ Supervisor exact-SHA review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ separate MERGE_ELIGIBLE checks
→ merge only with authority
→ technical deployment only within explicit authority
→ PUBLISH only by Human action
→ durable recovery from GitHub.

The document remains:

PROPOSAL — NOT CANONICAL

until a separate authorized adoption decision changes that status.
