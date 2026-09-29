# Web Baseline Adaptation Matrix

STATUS: PROPOSAL — NOT CANONICAL
GOVERNING WORK ITEM: Issue #8
ACTIVITY: WEB-BASELINE-ADAPTATION-1
AUTHORITY: Issue #8 comment 5883378701
ARCHITECTURE HEAD: 621d4e58eccbc697d42074e5f7eaa53a162a0582
ANDROID EXEMPLAR: 8a2b03061da73b3d5b41e7ad72e8f9ccf40b56e3 — document-architecture reference only
IOS EXEMPLAR: 88f311c349c2bc9cd4c554fbe8bf7762bd970656 — document-architecture reference only

## Purpose

This matrix is the lossless section-by-section bridge from the frozen functional baseline to a future standalone `WEB_WORKFLOW.md`.

It does not implement `WEB_WORKFLOW.md`.

Primary rule:

`WEB_WORKFLOW.md = BASELINE FUNCIONAL + ADAPTACIÓN WEB JUSTIFICADA`

Rules:
- every frozen-baseline Markdown heading counted by the accepted architecture is represented;
- all six Work Item child fields are explicit rows;
- no silent grouping/omission;
- classifications are limited to `PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION`;
- accepted Issue #2 Web/shared research is reused;
- no Candidate/scoring/sensitivity research is repeated;
- Android/iOS are document-architecture exemplars only, never Web mechanics sources;
- volatile browser/runtime/framework/provider facts remain behind the Research/Freshness Gate;
- a future Web workflow must trace to this matrix and the accepted Workflow Document Contract.

## Accepted evidence codes

- BASE = `references/WORKFLOW_BASE_ORIGINAL.md`, blob `fa6ce8e396e1ae422ce4feab3f97d7d37bb43f83`
- W6-CAP = `outputs/06/web-capability-matrix.md`, blob `a59fe085407282175be849305374617b03e95200`
- W6 = `outputs/06/web-evidence.md`, blob `0087886f217bbb1ef2a61c5af365aed52547f9e7`
- W7 = `outputs/07/web-candidate-4-presentation.md`, blob `631b62c2dc76ace3a11235f1212098f0c0161999`
- CORE = `outputs/08/common-governance-core.md`, blob `8c8e46ebd54ed8110848e3d7035171692d53050c`
- ACTOR = `outputs/08/external-actor-interface.md`, blob `8f742c1f362b5ac726c1429f7bbc075d2f0926db`
- DELTA = `outputs/08/platform-deltas.md`, blob `8d327278ec87c20cf2589e771163f9ab80359056`
- AUDIT = `outputs/09/contradiction-audit.md`, blob `bbb963b21c94950998a5dc3b9db0ebdcb17ec4c6`
- FINAL-W = `outputs/10/web-workflow-proposal.md`, blob `ae3b6b468a0c0158362036fee91a4bf4be57fdfd`
- ISSUE8 = Issue #8 Human/Supervisor authority, especially comment `5883378701`

## Coverage matrix

| Baseline section/subsection | Classification | Preserved operational function | Web-specific delta | Accepted evidence/source | Target future WEB_WORKFLOW section | Unresolved decision |
|---|---|---|---|---|---|---|
| Document header / status / provenance | ADAPT | Declare workflow identity, canonical status and provenance. | Web workflow must identify Web platform, Issue #8 authority, accepted architecture and accepted Web evidence chain. | BASE + ISSUE8 | Document status / authority / provenance | Canonical adoption remains separate. |
| Estado de procedencia | EXTEND | Retain provenance and supersession history. | Add accepted Issue #2 Web/shared evidence and Issue #8 architecture/adaptation authorities without rewriting history. | BASE + AUDIT + ISSUE8 | Provenance / maintenance | None. |
| 1. Objetivo | ADAPT | State collaborative workflow objective. | Objective becomes a standalone Web operational workflow preserving the baseline lifecycle while remaining framework/runtime/provider neutral. | BASE + W7 + FINAL-W | Purpose / audience / usage | None. |
| 2. Principio fundamental | PRESERVE | GitHub/documents are durable memory; chat is not authority. | No Web-specific semantic change. | BASE + CORE | Fundamental principles | None. |
| 3. Responsabilidades | PRESERVE | Separate Human, Supervisor, Implementer, GitHub/evidence responsibilities. | Web build/browser/deployment/secrets duties populate role responsibilities without changing authority. | BASE + CORE | Roles / responsibilities / authority | None. |
| 3.1 Chat Web GPT | PRESERVE | Supervisor plans, scopes, reviews and decides; does not self-implement the reviewed task normally. | Runtime/browser/preview/deploy/accessibility evidence are review inputs only. | BASE + CORE + W7 | Supervisor role contract | None. |
| 4. Agente implementador | EXTEND | Implement authorized change, verify, diff, commit/PR and report; no self-approval. | Add runtime/package-manager/build-tool reconstruction, client/server/API boundaries, browser/E2E/accessibility verification, secrets/environment handling and bounded preview/deploy responsibilities. | BASE + W6 + W7 + FINAL-W | Implementer role contract | Project-native commands and deployment model are project facts. |
| 5. GitHub | PRESERVE | Persistent control plane for Issue, branch, commit, PR, diff, CI and decisions. | No Web-specific semantic change. | BASE + CORE | GitHub / evidence systems | None. |
| 6. Documentación del proyecto | ADAPT | Distinguish product documentation from workflow documentation. | Web workflow may reference project runtime/framework/API/database/deployment docs but remains separate from product documentation. | BASE + ISSUE8 | Reading/context policy + provenance | Exact project doc paths are project-specific. |
| 7. Unidad de trabajo: GitHub Issue | PRESERVE | Six-field Work Item contract. | Runtime/framework/package-manager, client/server/API, browser, accessibility, preview/deploy and secrets requirements populate the six fields without replacing them. | BASE + CORE + W7 | Work Item contract | None. |
| Objective | PRESERVE | Define what the Work Item must achieve. | Web stack details may refine context but cannot replace or silently expand the authorized outcome. | BASE + CORE | Work Item contract — Objective | None. |
| Acceptance Criteria | EXTEND | Define observable conditions proving the Objective is satisfied. | Add Web-specific evidence when needed: build/test/lint/typecheck, browser/runtime/E2E, accessibility/human UX, API/integration, preview/staging/deployment checks. | BASE + CORE + W6 + W7 | Work Item contract — Acceptance Criteria | Concrete criteria remain Work Item-specific. |
| Authorized Scope | PRESERVE | Define authorized file/module/system boundary independently from semantic authority. | Frontend/backend/schema/database/infrastructure/deployment paths may be scoped explicitly; path/system access never grants unrelated semantic authority. | BASE + CORE + W6 | Work Item contract — Authorized Scope | None. |
| Relevant Sources | ADAPT | Identify documentation/evidence the Implementer must read. | Point to future standalone Web workflow, project stack/API/deployment docs and only materially required accepted/current sources; Issue #2 remains provenance. | BASE + CORE + ISSUE8 | Work Item contract — Relevant Sources | Project-specific source paths. |
| Verification | ADAPT | Define exact checks/evidence required before handoff. | Use project-native install/build/test/lint/typecheck/static-analysis, client/server/API/integration checks, and risk-triggered browser/E2E/accessibility/preview/deploy evidence. | BASE + W6 + W7 + FINAL-W | Work Item contract — Verification | Exact commands/browser matrix/environments are project-specific. |
| Base | PRESERVE | Bind the task to the branch/commit from which authorized work starts. | Preserve exact ref/SHA semantics; browser/deploy/provider capability cannot compensate for repository-base mismatch. | BASE + CORE | Work Item contract — Base | None. |
| 8. Dos tipos de scope | PRESERVE | Semantic Scope and Path Scope are independently required. | No Web-specific semantic change. | BASE + CORE | Semantic Scope + Path Scope | None. |
| Semantic Scope | PRESERVE | Authorize behavior/change, not paths. | No Web-specific semantic change. | BASE + CORE | Semantic Scope | None. |
| Path Scope | PRESERVE | Authorize files/modules/systems, not behavior. | No Web-specific semantic change. | BASE + CORE | Path Scope | None. |
| 9. Flujo completo | ADAPT | Preserve end-to-end Human→Supervisor→Issue→Implementer→review lifecycle. | Insert Web environment reconstruction, project-native verification, risk-triggered browser/E2E/accessibility evidence, optional preview/staging and protected deploy capability before handoff/review. | BASE + W7 + CORE | End-to-end lifecycle | None. |
| Fase A — intención | PRESERVE | Human intent is analyzed for objective, architecture, risk, scope and verification. | Web risk includes client/server/API/data boundaries, browser compatibility, accessibility/UX, secrets, external mutations and deploy/publication impact when material. | BASE + W7 | Human intent / Supervisor preparation | None. |
| Fase B — creación del Work Item | PRESERVE | Create bounded Work Item, ideally one objective/branch/PR. | Web environment, browser matrix, client/server/API scope, secrets and preview/deploy verification populate the same six-field contract. | BASE + CORE | Work Item creation | None. |
| 10. Inicio del Agente implementador | PRESERVE | Use a short pointer-based prompt; GitHub holds durable detail. | No Web-specific semantic change. | BASE | Implementer start | None. |
| 11. Bootstrap del Agente implementador | EXTEND | Answer material authority/scope/base/context/test questions before edits. | Add runtime/framework/package manager/build tools, client/server/API/database surfaces, dev server, browser targets, secrets/environment, preview/deploy and external-platform mutation questions. | BASE + W6 + W7 + FINAL-W | Implementer bootstrap | Concrete project environment facts resolved per Work Item. |
| 12. Política de lectura | ADAPT | Use progressive disclosure and read only necessary context. | Read future Web workflow first, then project stack/API/schema/deployment/browser docs and affected sources/tests; Issue #2 remains provenance. | BASE + ISSUE8 | Reading / context policy | None. |
| 13. Implementación | EXTEND | Make the minimal authorized change; no opportunistic refactor/infrastructure. | Respect existing runtime/framework/library/package-manager/client/server/data architecture; do not force migrations. Protect browser/server secret boundaries and external-system authority. | BASE + W6 + W7 | Implementation discipline | Project architecture constrains details. |
| 14. Problemas descubiertos durante el trabajo | PRESERVE | In-scope related issue may be fixed; unrelated issue reported; scope expansion stops. | No Web-specific semantic change. | BASE | Discovered-problem handling | None. |
| 15. Verificación local | ADAPT | Run relevant checks, correct, rerun and inspect full diff. | Base Web evidence uses project-native build/test/lint/typecheck/static checks; add API/integration/E2E/browser/accessibility/preview/deploy evidence by risk. | BASE + W6 + W7 + FINAL-W | Verification model | Exact commands/browser/environment matrix are project-specific. |
| 16. Publicación | ADAPT | Commit/push/PR publication of proposed repository change for review. | Use REPOSITORY_PUBLICATION for GitHub commit/push/PR. Preview/staging/deployment/product publication remain separate capabilities and authority domains. | BASE + CORE + AUDIT | Repository handoff / PR publication | None. |
| 17. Handoff del Agente implementador | EXTEND | Compact durable report with Work Item, PR, commit, verification, CI and state. | Add runtime/build context, browser/API/E2E/accessibility evidence, preview URL/artifact/deployment IDs and external mutation evidence when applicable. | BASE + W6 + W7 | Implementer handoff | None. |
| 18. Revisión de Chat Web GPT | EXTEND | Independent review of Issue, diff, architecture, tests, docs, PR, SHA and CI. | For Web, review client/server/API boundaries, browser support evidence, accessibility/UX evidence, secrets, preview/staging/deploy evidence and Human publication boundary when relevant. | BASE + W7 + CORE | Supervisor exact-SHA review | None. |
| 19. Significado de las decisiones | PRESERVE | Closed Supervisor semantic state vocabulary. | No Web-specific decision states. | BASE + CORE | Formal decisions | None. |
| SEMANTIC_ACCEPTED | PRESERVE | Exact reviewed SHA satisfies Work Item intent; not automatic merge. | No Web-specific semantic change. | BASE + CORE | SEMANTIC_ACCEPTED | None. |
| REWORK | PRESERVE | Correction required within same objective. | No Web-specific semantic change. | BASE + CORE | REWORK | None. |
| HOLD | PRESERVE | Objective blocker cannot currently be resolved. | Web examples may include unavailable browser/provider/environment, missing secret/account permission, external service dependency or deployment constraint; semantics unchanged. | BASE + W6 | HOLD | None. |
| ESCALATE | PRESERVE | Human/material decision required. | Web examples may include provider/cost commitment, production secret/account permission, architecture/scope or publication decision; semantics unchanged. | BASE + W7 | ESCALATE | None. |
| 20. REWORK | PRESERVE | Same-objective correction stays same Issue/branch/PR; new SHA requires new review. | Use focused Web REWORK; no broad research cycle by default. | BASE + CORE + ISSUE8 | REWORK procedure | None. |
| 21. Decisión vigente | PRESERVE | Latest Supervisor decision explicitly associated with current HEAD is valid. | No Web-specific semantic change. | BASE + CORE | Current-decision rule | None. |
| 22. CI | ADAPT | CI produces reproducible exact-SHA mechanical evidence; PASS != approval. | Use project-native install/build/test/lint/typecheck/static checks, API/integration jobs, targeted browser/E2E, accessibility, preview or deployment evidence only when justified and authorized. | BASE + W6 + W7 + CORE | CI / evidence discipline | Concrete CI/browser/provider commands are project-specific. |
| 23. Integración | PRESERVE | READY_FOR_REVIEW→SEMANTIC_ACCEPTED→target checks→MERGE_ELIGIBLE→MERGED→CLOSED. | No Web-specific semantic change. | BASE + CORE | Integration / merge eligibility | None. |
| 24. Merge | PRESERVE | Supervisor-only merge after exact-SHA acceptance and eligibility checks when separately authorized. | No Web-specific semantic change. | BASE + CORE | Merge boundary | Repository-specific merge authority still governs. |
| 25. Cambio de sesión del Agente implementador | EXTEND | Fresh Implementer reconstructs from GitHub, not transcript. | Also recover runtime/framework/package-manager/build contract, browser support/evidence state, client/server/API/data boundaries, preview/deploy state, secrets/environment and external mutation status. | BASE + CORE + W7 | Implementer session recovery | None. |
| 26. Cambio de sesión de Chat Web GPT | EXTEND | Fresh Supervisor reconstructs product/work item/scope/HEAD/evidence/latest decision. | Also recover Web environment, browser/accessibility evidence, preview/deploy evidence, secrets/environment constraints and unresolved external platform mutations. | BASE + CORE + W7 | Supervisor session recovery | None. |
| 27. Rol del humano | EXTEND | Human owns intent, priorities, permissions, credentials, trade-offs and publication. | Preserve PUBLISH = HUMAN ACTION for production deployment/publication. Technical deploy/staging/hosting capability does not transfer publication authority. | BASE + CORE + AUDIT + W7 | Human role + product publication boundary | Concrete production/publication action per project. |
| 28. Reglas esenciales | EXTEND | Retain durable memory, Issue authority, role separation, dual scope, exact-SHA review, evidence≠approval, REWORK continuity and recovery. | Add HARD VETO non-regression, PUBLISH = HUMAN ACTION, TECHNICAL CAPABILITY != WORKFLOW AUTHORITY and Web platform-delta preservation. | BASE + CORE + AUDIT + DELTA | Fundamental principles / invariants | None. |
| 29. AI_STUDIO_OPERATOR — fallback excepcional por escalamiento verificado | ADAPT | Preserve function: optional subordinate external capability, never a new authority source. | Replace provider-specific AI Studio role with optional browser/design/accessibility/security/hosting/deploy/platform-mutation actor for a concrete missing Web capability. | BASE + ACTOR + W6 + W7 | Optional external-actor protocol | Provider chosen only when project need/authority exists. |
| 29.1 Permission Matrix | ADAPT | Explicit allowed/forbidden capabilities and Human/Supervisor boundaries. | Use capability-specific Web actor authority matrix; browser/deploy/hosting/secrets access never grants Workflow or publication authority. | BASE + ACTOR + CORE | External actor authority matrix | Exact actor capability per activity. |
| 29.2 Gate universal de escalamiento AI Studio | ADAPT | External escalation only after bounded need/blocker and Supervisor verification. | Invoke browser/design/security/deploy/provider capability only when required and explicitly authorized; no provider-by-default. | BASE + ACTOR + W7 | External actor invocation gate | None. |
| 29.3 Inicio: AI_STUDIO_REQUEST y modos técnicos | ADAPT | Persist request, objective, baseline, operations, evidence and stop conditions. | Use durable external-actor activity record; provider-specific modes are not universal Web semantics. | BASE + ACTOR | External actor activity start | Exact actor/provider mode if selected. |
| 29.4 SHA Gate y evidencia | EXTEND | Bind external activity to expected SHA/baseline and evidence. | Add artifact/build identity, runtime/build environment, browser matrix, target environment, deployment ID/URL and external configuration baseline where applicable. | BASE + ACTOR + W6 + W7 | External actor baseline/evidence gate | Exact browser/environment matrix per Work Item. |
| 29.5 Ventana única de intervención | ADAPT | External action is bounded in time/scope and returns control. | Represent one persisted bounded invocation; repeat requires renewed authority/evidence when ref/artifact/environment/external state changes materially. | BASE + ACTOR | External actor bounded execution | None. |
| 29.6 Clasificación, seguridad operacional y recuperación | ADAPT | Classify result/blocker safely, protect secrets and reconstruct activity. | Use generic Web actor result/evidence/STOP/recovery rules; protect deployment credentials, environment variables, API keys and external service state. | BASE + ACTOR + W6 | External actor result / recovery | None. |
| 29.7 Publicación — exclusiva del Humano | PRESERVE | Product publication belongs exclusively to Human. | Exact invariant PUBLISH = HUMAN ACTION; preview/staging/deploy/hosting credentials or production deploy capability never transfer publication authority. | BASE + CORE + AUDIT + W7 | Product publication boundary | None. |
| 29.8 RESEARCH_GATE y SPIKE_READ_ONLY | ADAPT | Use read-only research spike for unresolved external facts/capabilities before unsafe action. | Apply only when current browser compatibility, runtime/framework/provider behavior, hosting policy, deployment capability or security guidance is materially required; reuse Issue #2 otherwise. | BASE + W6 + W7 + ISSUE8 | Research / freshness gate | Current external fact only when triggered. |
| 29.9 Regla absoluta de no escritura de repositorio/product-code | ADAPT | External operator defaults to no unauthorized repository/product mutation. | Generic Web actor may write only when activity + Work Item explicitly authorize it; default deny outside enumerated operations. Production publication remains Human-only. | BASE + ACTOR | External actor forbidden operations | Exact actor write capability if ever authorized. |
| 29.10 AI_STUDIO_REPORT y STOP obligatorio | ADAPT | External actor returns structured report and stops. | Persist RESULT/evidence/STATUS and mandatory STOP/escalation after bounded Web activity. | BASE + ACTOR | External actor result / STOP | None. |
| 29.11 Fallback de mutación externa de plataforma | ADAPT | External platform mutation requires exact target/scope, baseline, before/after evidence, rollback when applicable, and stop conditions. | Web may require bounded DNS/CDN/hosting/configuration/migration/environment changes under explicit authority; no code/merge/publication authority follows. | BASE + ACTOR + W7 | External platform mutation protocol | Specific external mutation only by Work Item. |
| 29.12 Compatibilidad operacional inmediata — Issue #53 | NOT_APPLICABLE_WITH_JUSTIFICATION | Historical compatibility rule for a specific prior Issue/HOLD must remain traceable but is not a reusable platform-workflow function. | Do not import Issue #53/AI Studio quota state into Web. Equivalent future provider/quota blockers use generic HOLD/current-decision/recovery/external-actor rules. | BASE + AUDIT | Provenance appendix only | None; normative omission justified because safety function is preserved elsewhere. |
| 30. RESEARCH_GATE + STRATEGIC_RATIONALE | PRESERVE | Require research when a material unknown/current fact can change architecture/implementation; record rationale. | Web facts are platform/project-specific; gate semantics remain unchanged. | BASE + W7 + ISSUE8 | Research / freshness gate | None. |
| 30.1 Cuándo se activa RESEARCH_GATE | ADAPT | Trigger on material uncertainty/current external fact, not curiosity. | Examples: browser compatibility, runtime/framework/package-manager behavior, provider deployment capability/policy, CDN/cloud constraints or current security guidance when material. | BASE + W6 + W7 | Research trigger | Only concrete triggered fact. |
| 30.2 Investigación y evidencia | ADAPT | Prefer primary/official sources; separate fact/inference/recommendation/unknown. | Use browser/runtime/framework/provider/W3C/hosting official sources when fresh research is triggered; accepted Issue #2 evidence otherwise. | BASE + W6 + W7 | Research evidence discipline | None. |
| 30.3 Verificación del Supervisor | PRESERVE | Supervisor independently evaluates research relevance/quality before authority changes. | No Web-specific semantic change. | BASE | Supervisor research review | None. |
| 30.4 STRATEGIC_RATIONALE | PRESERVE | Persist why a material technical/architecture choice is justified. | Web-specific rationale references accepted evidence and project facts without freezing volatile platform/provider data. | BASE + W7 | Strategic rationale | None. |
| 30.5 Aplicación por rol y límites de autoridad | PRESERVE | Research informs decisions but does not transfer authority or scope. | No Web-specific semantic change. | BASE + CORE | Research authority boundary | None. |
| 31. TECHNICAL PERMISSION != WORKFLOW AUTHORITY | PRESERVE | Technical access/capability never equals Workflow authority. | Exact accepted invariant retained. | BASE + CORE + ACTOR + AUDIT | Technical permission / authority boundary | None. |
| 31.1 Escritura de repositorio/product-code | PRESERVE | Repository/product writes require explicit Semantic + Path Scope authority. | Browser/provider/deploy/secret/tool access does not expand repository write authority. | BASE + CORE + ACTOR | Repository write authority | None. |
| 31.2 Escalación AI Studio | ADAPT | External technical escalation remains subordinate to Workflow authority. | Generalize AI Studio to optional browser/design/security/deploy/platform actor; escalation never creates semantic/merge/publication authority. | BASE + ACTOR + W7 | External actor escalation boundary | None. |
| Resultado | ADAPT | Summarize operational system without replacing normative sections. | Web result summarizes Human→Supervisor→Issue→Implementer→project-native verification→browser/accessibility/preview/deploy evidence→review while preserving provider neutrality and authority boundaries. | BASE + W7 | Result / workflow synopsis | None. |
| Apéndice A — Provenance de mejoras consolidadas | ADAPT | Preserve provenance of inherited/adopted rules. | Trace baseline plus accepted Issue #2 Web/shared artifacts and Issue #8 architecture authorities; do not rewrite history. | BASE + AUDIT + ISSUE8 | Provenance appendix | None. |
| Apéndice B — Handover canónico | ADAPT | Prevent ambiguous coexistence of old/new normative sources and record handover status. | Until explicit adoption, future Web workflow remains PROPOSAL — NOT CANONICAL; handover/adoption requires later authority. | BASE + ISSUE8 | Status / adoption appendix | Future canonical adoption decision. |
| Apéndice C — Matriz completa de trazabilidad del baseline | EXTEND | Provide complete baseline coverage proof. | Use this Web adaptation matrix and future workflow cross-check as acceptance evidence; include accepted Issue #2 controls without erasing baseline mapping. | BASE + CORE + AUDIT + ISSUE8 | Baseline traceability appendix / DoD | None. |

## Coverage self-check

Frozen baseline Markdown headings counted for coverage:
71

Counting rule:
- 1 structural document heading is represented by `Document header / status / provenance`;
- 64 additional baseline headings outside the six-field Work Item template are explicitly classified;
- 6 Work Item child headings are explicit normative rows:
  - Objective
  - Acceptance Criteria
  - Authorized Scope
  - Relevant Sources
  - Verification
  - Base

Matrix classified rows:
71

Normative operational headings/subheadings:
70

Structural metadata headings:
1

Work Item child fields explicitly mapped:
6 / 6

Missing headings/subheadings:
0

Silently grouped normative subsections:
0

## Classification summary

- PRESERVE: 31
- ADAPT: 26
- EXTEND: 13
- NOT_APPLICABLE_WITH_JUSTIFICATION: 1
- TOTAL: 71

The only `NOT_APPLICABLE_WITH_JUSTIFICATION` row is:
- `29.12 Compatibilidad operacional inmediata — Issue #53`

Reason:
that baseline rule persisted a specific historical Issue #53 / AI Studio quota/HOLD compatibility state. It is not a reusable Web platform mechanic. Its safety function remains explicit through generic `HOLD`, current-decision, recovery, external-actor gating, STOP/escalation and Human publication rules.

No other baseline section/subsection is omitted.

## Web-specific insertions required by accepted evidence

The future `WEB_WORKFLOW.md` must operationalize at least:

### 1. Project environment contract

Record material project facts such as:
- runtime;
- framework/library;
- package manager;
- package/runtime version source;
- install command;
- local dev-server command;
- build command;
- unit/integration test commands;
- lint/typecheck/static-analysis commands;
- client/server/API/schema/database boundaries;
- browser support policy;
- build/deploy artifact and environment model.

No runtime, framework, package manager, test tool, host or cloud provider is mandatory.

### 2. Verification ladder

Use project-native verification and escalate by risk:
1. install/build/static/type/lint;
2. unit tests;
3. API/integration/contract tests;
4. production-like build;
5. targeted browser/E2E tests;
6. accessibility checks + Human review when qualitative judgment is required;
7. preview/staging smoke/design review when useful;
8. deployment verification when explicitly authorized.

Browser automation is evidence, not semantic approval or complete real-user UX proof.

### 3. Browser/runtime matrix

Select the smallest matrix justified by:
- project support targets;
- compatibility risk;
- feature/browser API use;
- responsive/device impact;
- embedded WebView/enterprise constraints where applicable;
- release-critical journeys.

Possible evidence:
- real-browser automation;
- screenshots/traces/reports;
- responsive viewport/device profiles;
- manual real-browser/device checks when automation is insufficient.

No single browser automation tool is mandatory.

### 4. Client/server/API/E2E boundary

Every Work Item must preserve explicit authority across:
- browser client;
- server/API;
- shared schema/contracts;
- database/migrations;
- background jobs/services;
- infrastructure/deployment.

Browser-delivered code must not contain private server/deployment secrets.

A path or credential on one surface does not authorize changes to another.

### 5. Preview/staging/deployment boundary

Preview/staging environments are optional evidence surfaces.

They must:
- bind to exact ref/artifact when applicable;
- use the intended target environment;
- respect secrets/permissions;
- return deployment ID/URL and verification evidence;
- not silently become production publication.

Technical preview/staging/deploy capability does not create publication authority.

`PUBLISH = HUMAN ACTION`.

### 6. Hosting/cloud/CDN/provider boundary

Hosting, CDN, cloud, edge, database and deployment providers are capability-specific project choices.

Provider-neutral governance is preferred where practical.

Provider-specific adapters are acceptable under explicit project/Work Item authority.

No provider identity creates Workflow authority.

### 7. Secrets/environment variables

The future workflow must distinguish:
- browser-exposed public configuration;
- private server-side secrets;
- CI/deploy credentials;
- environment-scoped variables;
- untrusted PR execution;
- privileged deployment context.

Use least privilege.

Do not expose private server/deploy secrets in browser-delivered bundles.

Short-lived/OIDC authentication is a possible control where supported, not a universal requirement.

### 8. External platform mutations

Potential Web external mutations include:
- database migrations;
- DNS;
- CDN/cache rules;
- hosting configuration;
- environment variables;
- cloud resources;
- API/provider configuration;
- deployment rollback.

Each requires explicit scope/authority, observable baseline, evidence and rollback/STOP behavior where applicable.

Technical access alone is insufficient.

### 9. Accessibility / UX / browser compatibility

Automated accessibility and browser checks are evidence.

Material interaction/visual/accessibility changes may require Human/design/accessibility review because qualitative judgment is not reducible to automated PASS.

Current compatibility facts belong behind Research/Freshness Gate.

### 10. Web non-symmetry rules

Do not import Android mechanics:
- no Gradle/AGP;
- no compileSdk/targetSdk/minSdk;
- no APK/AAB;
- no Android API/ABI;
- no Android emulator/Gradle Managed Device;
- no Firebase Test Lab requirement;
- no Play Console/Play signing;
- no Compose/View/Java migration rule.

Do not import iOS mechanics:
- no macOS/Xcode universal requirement;
- no Xcode project/workspace/scheme/configuration model;
- no Apple Simulator/physical-device semantics;
- no Apple certificates/provisioning profiles/entitlements;
- no archive/export semantics;
- no App Store Connect/TestFlight;
- no Swift/Objective-C/SwiftUI/UIKit migration rule.

Do not invent a universal mobile-style signing gate for generic Web deployment.

## Decisions intentionally deferred to future Web Work Items/projects

The architecture does not invent:
- runtime/framework/library;
- package manager;
- exact runtime/package versions;
- install/dev/build/test/lint/typecheck/static-analysis commands;
- client/server/API/schema/database boundaries;
- browser support matrix;
- responsive/device matrix;
- E2E/browser automation tool;
- accessibility/design review level;
- preview strategy;
- staging/production environment model;
- hosting/cloud/CDN/database provider;
- deployment artifact;
- secrets/environment-variable custody;
- CI/provider identity;
- OIDC/credential strategy;
- migration/rollback procedure;
- external platform mutation authority;
- deployment protection rules;
- provider cost/quota;
- current browser/framework/provider policy;
- concrete Human production-publication action.

These remain project/Work Item facts under explicit authority and, for volatile external facts, the Research/Freshness Gate.

## Research decision

Fresh research triggered:
NO

Reason:
the accepted Issue #2 Web evidence is sufficient to classify the baseline and define the durable Web deltas required by this matrix. No current volatile fact is needed to complete this architecture/adaptation artifact.

Any future concrete Web Work Item that depends on current browser/runtime/framework/provider/security requirements must activate the Research/Freshness Gate at that time.

## Acceptance condition for future WEB_WORKFLOW.md

The future standalone workflow fails the baseline-coverage gate if:
- any of the 71 rows above lacks a target implementation;
- a classification changes without explicit authority/evidence;
- any of the six Work Item fields is grouped away;
- an accepted invariant is compressed away;
- `PUBLISH = HUMAN ACTION` is weakened;
- `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY` is weakened;
- `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE` is weakened;
- exact-SHA review or GitHub recovery is weakened;
- durable external-actor activity is omitted;
- Issue #2 becomes a normal execution dependency;
- Android/iOS mechanics are copied into Web;
- Web browser/client-server/deployment/secrets boundaries are erased to force symmetry;
- current browser/runtime/framework/provider facts are frozen as timeless workflow semantics.

Any unexplained loss, weakening, substitution or reinterpretation is a HARD VETO.
