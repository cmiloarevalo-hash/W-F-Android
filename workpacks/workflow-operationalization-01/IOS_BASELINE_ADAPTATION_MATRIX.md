# iOS Baseline Adaptation Matrix

STATUS: PROPOSAL — NOT CANONICAL
GOVERNING WORK ITEM: Issue #8
ACTIVITY: IOS-BASELINE-ADAPTATION-1
AUTHORITY: Issue #8 comment 5883208238
ARCHITECTURE HEAD: 621d4e58eccbc697d42074e5f7eaa53a162a0582
ANDROID EXEMPLAR: 8a2b03061da73b3d5b41e7ad72e8f9ccf40b56e3 — document-architecture reference only, NOT an iOS mechanics source

## Purpose

This matrix is the lossless section-by-section bridge from the frozen functional baseline to a future standalone `IOS_WORKFLOW.md`.

It does not implement `IOS_WORKFLOW.md`.

Primary rule:

`IOS_WORKFLOW.md = BASELINE FUNCIONAL + ADAPTACIÓN IOS JUSTIFICADA`

Rules:
- every frozen-baseline Markdown heading counted by the accepted architecture is represented;
- all six Work Item child fields are explicit rows;
- no silent grouping/omission;
- classifications are limited to `PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION`;
- accepted Issue #2 iOS/shared research is reused;
- no Candidate/scoring/sensitivity research is repeated;
- Android is used only as proof of document architecture, never as an iOS mechanics source;
- volatile Apple/toolchain/policy facts remain behind the Research/Freshness Gate;
- a future iOS workflow must trace to this matrix and the accepted Workflow Document Contract.

## Accepted evidence codes

- BASE = `references/WORKFLOW_BASE_ORIGINAL.md`, blob `fa6ce8e396e1ae422ce4feab3f97d7d37bb43f83`
- I4-CAP = `outputs/04/ios-capability-matrix.md`, blob `0aea770ed17345a5300ecea716aea874cf3ebe56`
- I4 = `outputs/04/ios-evidence.md`, blob `0bbed9a8beba1ad84056e01b1b01ae0a2badb8a0`
- I5 = `outputs/05/ios-candidate-4-presentation.md`, blob `e0c3b4c46d868b0f9e5ad9aa2326620ac5ce7948`
- CORE = `outputs/08/common-governance-core.md`, blob `8c8e46ebd54ed8110848e3d7035171692d53050c`
- ACTOR = `outputs/08/external-actor-interface.md`, blob `8f742c1f362b5ac726c1429f7bbc075d2f0926db`
- DELTA = `outputs/08/platform-deltas.md`, blob `8d327278ec87c20cf2589e771163f9ab80359056`
- AUDIT = `outputs/09/contradiction-audit.md`
- FINAL-I = `outputs/10/ios-workflow-proposal.md`, blob `64cacc2c9e5d766145a0c901550422b1922e8bc1`
- ISSUE8 = Issue #8 Human/Supervisor architecture authority, especially comments `5883204207` and `5883208238`

## Coverage matrix

| Baseline section/subsection | Classification | Preserved operational function | iOS-specific delta | Accepted evidence/source | Target future IOS_WORKFLOW section | Unresolved decision |
|---|---|---|---|---|---|---|
| Document header / status / provenance | ADAPT | Declare workflow identity, canonical status and provenance. | iOS workflow must identify iOS platform, Issue #8 authority, accepted architecture and accepted iOS evidence chain. | BASE + ISSUE8 | Document status / authority / provenance | Canonical adoption remains separate. |
| Estado de procedencia | EXTEND | Retain provenance and supersession history. | Add Issue #2 accepted iOS/shared evidence and Issue #8 architecture/adaptation authorities without rewriting history. | BASE + AUDIT + ISSUE8 | Provenance / maintenance | None. |
| 1. Objetivo | ADAPT | State collaborative workflow objective. | Objective becomes a standalone iOS operational workflow preserving the baseline lifecycle while respecting the macOS/Xcode native boundary. | BASE + I5 + FINAL-I | Purpose / audience / usage | None. |
| 2. Principio fundamental | PRESERVE | GitHub/documents are durable memory; chat is not authority. | No iOS-specific semantic change. | BASE + CORE | Fundamental principles | None. |
| 3. Responsabilidades | PRESERVE | Separate Human, Supervisor, Implementer, GitHub/evidence responsibilities. | iOS build/device/signing/distribution duties populate role responsibilities without changing authority. | BASE + CORE | Roles / responsibilities / authority | None. |
| 3.1 Chat Web GPT | PRESERVE | Supervisor plans, scopes, reviews and decides; does not self-implement the reviewed task normally. | macOS/Xcode, simulator/device, signing and distribution evidence are review inputs only. | BASE + CORE + I5 | Supervisor role contract | None. |
| 4. Agente implementador | EXTEND | Implement authorized change, verify, diff, commit/PR and report; no self-approval. | Add reconstruction of project/workspace/scheme/configuration, macOS/Xcode build lane, test destinations, archive/export/signing boundaries and risk-tiered simulator/device evidence. | BASE + I4 + I5 + FINAL-I | Implementer role contract | Project-native commands and exact environment are project facts. |
| 5. GitHub | PRESERVE | Persistent control plane for Issue, branch, commit, PR, diff, CI and decisions. | No iOS-specific semantic change. | BASE + CORE | GitHub / evidence systems | None. |
| 6. Documentación del proyecto | ADAPT | Distinguish product documentation from workflow documentation. | iOS workflow may reference project Xcode/build/signing/release docs but remains separate from app/product documentation. | BASE + ISSUE8 | Reading/context policy + provenance | Exact project doc paths are project-specific. |
| 7. Unidad de trabajo: GitHub Issue | PRESERVE | Six-field Work Item contract. | iOS environment, scheme/destination, verification, signing and release details populate the six fields without replacing them. | BASE + CORE + I5 | Work Item contract | None. |
| Objective | PRESERVE | Define what the Work Item must achieve. | iOS implementation detail may refine context but cannot replace or silently expand the authorized outcome. | BASE + CORE | Work Item contract — Objective | None. |
| Acceptance Criteria | EXTEND | Define observable conditions proving the Objective is satisfied. | Add iOS-specific evidence when needed: project-native build/test, Simulator/device behavior, archive/export/signing or release-boundary proof. | BASE + CORE + I4 + I5 | Work Item contract — Acceptance Criteria | Concrete criteria remain Work Item-specific. |
| Authorized Scope | PRESERVE | Define authorized file/module boundary independently from semantic authority. | Project/workspace/scheme files, source modules, tests, entitlements or signing config may be scoped explicitly; path permission never grants unrelated semantic authority. | BASE + CORE | Work Item contract — Authorized Scope | None. |
| Relevant Sources | ADAPT | Identify documentation/evidence the Implementer must read. | Point to future standalone iOS workflow, project iOS/Xcode docs and only materially required accepted/current sources; Issue #2 remains provenance, not normal execution dependency. | BASE + CORE + ISSUE8 | Work Item contract — Relevant Sources | Project-specific source paths. |
| Verification | ADAPT | Define exact checks/evidence required before handoff. | Use project-native Swift Testing/XCTest or equivalents, affected xcodebuild scheme/configuration, retained result evidence, and risk-triggered Simulator/device/archive evidence. | BASE + I4 + I5 + FINAL-I | Work Item contract — Verification | Exact commands/test destinations/device matrix are project-specific. |
| Base | PRESERVE | Bind the task to the branch/commit from which authorized work starts. | Preserve exact ref/SHA semantics; Mac/Xcode access or signing capability cannot compensate for repository-base mismatch. | BASE + CORE | Work Item contract — Base | None. |
| 8. Dos tipos de scope | PRESERVE | Semantic Scope and Path Scope are independently required. | No iOS-specific semantic change. | BASE + CORE | Semantic Scope + Path Scope | None. |
| Semantic Scope | PRESERVE | Authorize behavior/change, not paths. | No iOS-specific semantic change. | BASE + CORE | Semantic Scope | None. |
| Path Scope | PRESERVE | Authorize files/modules, not behavior. | No iOS-specific semantic change. | BASE + CORE | Path Scope | None. |
| 9. Flujo completo | ADAPT | Preserve end-to-end Human→Supervisor→Issue→Implementer→review lifecycle. | Insert iOS environment reconstruction, Mac build adapter, risk-triggered Simulator/device evidence and isolated signing/archive/export technical boundary before handoff/review. | BASE + I5 + CORE | End-to-end lifecycle | None. |
| Fase A — intención | PRESERVE | Human intent is analyzed for objective, architecture, risk, scope and verification. | iOS risk includes native Xcode build, Simulator/device fidelity, signing/provisioning, archive/export and distribution concerns when material. | BASE + I5 | Human intent / Supervisor preparation | None. |
| Fase B — creación del Work Item | PRESERVE | Create bounded Work Item, ideally one objective/branch/PR. | iOS environment, scheme/configuration, destination, signing and verification requirements populate the same six-field contract. | BASE + CORE | Work Item creation | None. |
| 10. Inicio del Agente implementador | PRESERVE | Use a short pointer-based prompt; GitHub holds durable detail. | No iOS-specific semantic change. | BASE | Implementer start | None. |
| 11. Bootstrap del Agente implementador | EXTEND | Answer material authority/scope/base/context/test questions before edits. | Add project/workspace/scheme/configuration, macOS/Xcode availability, destination/test-plan, Simulator/device need, signing/provisioning, archive/export and App Store/TestFlight impact questions. | BASE + I4 + I5 + FINAL-I | Implementer bootstrap | Concrete project environment facts resolved per Work Item. |
| 12. Política de lectura | ADAPT | Use progressive disclosure and read only necessary context. | Read future iOS workflow first, then project iOS/Xcode/build/test/signing docs and affected sources/tests; Issue #2 remains provenance. | BASE + ISSUE8 | Reading / context policy | None. |
| 13. Implementación | EXTEND | Make the minimal authorized change; no opportunistic refactor/infrastructure. | Respect existing Swift/Objective-C/SwiftUI/UIKit/project architecture as project facts; no forced migration. Keep Apple-runtime dependence only where semantics require it. | BASE + I4 + I5 | Implementation discipline | Project architecture constrains details. |
| 14. Problemas descubiertos durante el trabajo | PRESERVE | In-scope related issue may be fixed; unrelated issue reported; scope expansion stops. | No iOS-specific semantic change. | BASE | Discovered-problem handling | None. |
| 15. Verificación local | ADAPT | Run relevant checks, correct, rerun and inspect full diff. | Base iOS evidence uses project-native Swift Testing/XCTest/equivalents and affected xcodebuild build/test on macOS/Xcode; add Simulator/device/archive/export evidence by risk. | BASE + I4 + I5 + FINAL-I | Verification model | Exact commands/destinations/device matrix are project-specific. |
| 16. Publicación | ADAPT | Commit/push/PR publication of proposed repository change for review. | Use REPOSITORY_PUBLICATION for GitHub commit/push/PR. Product/TestFlight/App Store publication remains separate and Human-only. | BASE + CORE + AUDIT | Repository handoff / PR publication | None. |
| 17. Handoff del Agente implementador | EXTEND | Compact durable report with Work Item, PR, commit, verification, CI and state. | Add relevant macOS/Xcode environment, scheme/destination, xcresult/run evidence, Simulator/device and archive/export/signing evidence references when applicable. | BASE + I4 + I5 | Implementer handoff | None. |
| 18. Revisión de Chat Web GPT | EXTEND | Independent review of Issue, diff, architecture, tests, docs, PR, SHA and CI. | For iOS, review Xcode/macOS evidence, test destinations, Simulator/device sufficiency, signing/provisioning/archive boundaries and Human publication boundary when relevant. | BASE + I5 + CORE | Supervisor exact-SHA review | None. |
| 19. Significado de las decisiones | PRESERVE | Closed Supervisor semantic state vocabulary. | No iOS-specific decision states. | BASE + CORE | Formal decisions | None. |
| SEMANTIC_ACCEPTED | PRESERVE | Exact reviewed SHA satisfies Work Item intent; not automatic merge. | No iOS-specific semantic change. | BASE + CORE | SEMANTIC_ACCEPTED | None. |
| REWORK | PRESERVE | Correction required within same objective. | No iOS-specific semantic change. | BASE + CORE | REWORK | None. |
| HOLD | PRESERVE | Objective blocker cannot currently be resolved. | iOS examples may include unavailable Mac/Xcode/device capability, signing credential/provisioning or external dependency; semantics unchanged. | BASE + I4 | HOLD | None. |
| ESCALATE | PRESERVE | Human/material decision required. | iOS examples may include signing/account role, paid Mac/device capacity, architecture/scope or publication decision; semantics unchanged. | BASE + I5 | ESCALATE | None. |
| 20. REWORK | PRESERVE | Same-objective correction stays same Issue/branch/PR; new SHA requires new review. | Use focused iOS REWORK; no broad research cycle by default. | BASE + CORE + ISSUE8 | REWORK procedure | None. |
| 21. Decisión vigente | PRESERVE | Latest Supervisor decision explicitly associated with current HEAD is valid. | No iOS-specific semantic change. | BASE + CORE | Current-decision rule | None. |
| 22. CI | ADAPT | CI produces reproducible exact-SHA mechanical evidence; PASS != approval. | Replace baseline npm-specific commands with project-native Xcode/xcodebuild/test commands on an authorized macOS lane; retain result bundles/artifacts; Simulator/device jobs only when justified. | BASE + I4 + I5 + CORE | CI / evidence discipline | Concrete CI provider, Mac image and commands are project-specific. |
| 23. Integración | PRESERVE | READY_FOR_REVIEW→SEMANTIC_ACCEPTED→target checks→MERGE_ELIGIBLE→MERGED→CLOSED. | No iOS-specific semantic change. | BASE + CORE | Integration / merge eligibility | None. |
| 24. Merge | PRESERVE | Supervisor-only merge after exact-SHA acceptance and eligibility checks when separately authorized. | No iOS-specific semantic change. | BASE + CORE | Merge boundary | Repository-specific merge authority still governs. |
| 25. Cambio de sesión del Agente implementador | EXTEND | Fresh Implementer reconstructs from GitHub, not transcript. | Also recover project/workspace/scheme/configuration, macOS/Xcode environment, latest test destination/result, Simulator/device state and unresolved signing/release constraints. | BASE + CORE + I5 | Implementer session recovery | None. |
| 26. Cambio de sesión de Chat Web GPT | EXTEND | Fresh Supervisor reconstructs product/work item/scope/HEAD/evidence/latest decision. | Also recover iOS environment, test/device evidence, archive/export/signing status and unresolved distribution decisions. | BASE + CORE + I5 | Supervisor session recovery | None. |
| 27. Rol del humano | EXTEND | Human owns intent, priorities, permissions, credentials, trade-offs and publication. | Preserve PUBLISH = HUMAN ACTION for TestFlight/App Store/other product distribution. Technical archive/sign/upload ability does not transfer publication authority. | BASE + CORE + AUDIT + I5 | Human role + product publication boundary | Concrete Apple account/App Store Connect roles per project. |
| 28. Reglas esenciales | EXTEND | Retain durable memory, Issue authority, role separation, dual scope, exact-SHA review, evidence≠approval, REWORK continuity and recovery. | Add HARD VETO non-regression, PUBLISH = HUMAN ACTION, TECHNICAL CAPABILITY != WORKFLOW AUTHORITY and explicit iOS platform-delta preservation. | BASE + CORE + AUDIT + DELTA | Fundamental principles / invariants | None. |
| 29. AI_STUDIO_OPERATOR — fallback excepcional por escalamiento verificado | ADAPT | Preserve function: optional subordinate external capability, never a new authority source. | Replace provider-specific AI Studio role with optional Mac/Xcode/device/build/signing-support/pre-publication technical actor for a concrete missing iOS capability. | BASE + ACTOR + I4 + I5 | Optional external-actor protocol | Provider chosen only when project need/authority exists. |
| 29.1 Permission Matrix | ADAPT | Explicit allowed/forbidden capabilities and Human/Supervisor boundaries. | Use capability-specific iOS actor authority matrix; Mac/device/sign/archive/upload capability never grants Workflow or publication authority. | BASE + ACTOR + CORE | External actor authority matrix | Exact actor capability per activity. |
| 29.2 Gate universal de escalamiento AI Studio | ADAPT | External escalation only after bounded need/blocker and Supervisor verification. | Invoke an external Mac/device/signing-support capability only when required and explicitly authorized; no provider-by-default. | BASE + ACTOR + I5 | External actor invocation gate | None. |
| 29.3 Inicio: AI_STUDIO_REQUEST y modos técnicos | ADAPT | Persist request, objective, baseline, operations, evidence and stop conditions. | Use durable external-actor activity record; provider-specific modes are not universal iOS semantics. | BASE + ACTOR | External actor activity start | Exact actor/provider mode if selected. |
| 29.4 SHA Gate y evidencia | EXTEND | Bind external activity to expected SHA/baseline and evidence. | Add artifact identity/hash, macOS/Xcode/toolchain, scheme/configuration, destination/device and archive/export context where applicable. | BASE + ACTOR + I4 + I5 | External actor baseline/evidence gate | Exact destination/device matrix per Work Item. |
| 29.5 Ventana única de intervención | ADAPT | External action is bounded in time/scope and returns control. | Represent one persisted bounded invocation; repeat requires renewed authority/evidence when baseline, artifact, signing context or destination changes materially. | BASE + ACTOR | External actor bounded execution | None. |
| 29.6 Clasificación, seguridad operacional y recuperación | ADAPT | Classify result/blocker safely, protect secrets and reconstruct activity. | Use generic iOS actor result/evidence/STOP/recovery rules; protect certificates/keys/profiles and account roles. | BASE + ACTOR + I4 | External actor result / recovery | None. |
| 29.7 Publicación — exclusiva del Humano | PRESERVE | Product publication belongs exclusively to Human. | Exact invariant PUBLISH = HUMAN ACTION; archive/export/sign/upload/TestFlight/App Store Connect capability never transfers publication authority. | BASE + CORE + AUDIT + I5 | Product publication boundary | None. |
| 29.8 RESEARCH_GATE y SPIKE_READ_ONLY | ADAPT | Use read-only research spike for unresolved external facts/capabilities before unsafe action. | Apply only when current Xcode/macOS/SDK submission requirements, Apple policy, provider/device capability or account constraints are materially required; reuse Issue #2 otherwise. | BASE + I4 + I5 + ISSUE8 | Research / freshness gate | Current external fact only when triggered. |
| 29.9 Regla absoluta de no escritura de repositorio/product-code | ADAPT | External operator defaults to no unauthorized repository/product mutation. | Generic iOS actor may write only when activity + Work Item explicitly authorize it; default deny outside enumerated operations. Publication remains Human-only. | BASE + ACTOR | External actor forbidden operations | Exact actor write capability if ever authorized. |
| 29.10 AI_STUDIO_REPORT y STOP obligatorio | ADAPT | External actor returns structured report and stops. | Persist RESULT/evidence/STATUS and mandatory STOP/escalation after bounded iOS activity. | BASE + ACTOR | External actor result / STOP | None. |
| 29.11 Fallback de mutación externa de plataforma | ADAPT | External platform mutation requires exact target/scope, baseline, before/after evidence, rollback when applicable, and stop conditions. | iOS may require bounded non-publication changes in provisioning/device/provider/App Store Connect staging under explicit authority; no code/merge/publication authority follows. | BASE + ACTOR + I5 | External platform mutation protocol | Specific external mutation only by Work Item. |
| 29.12 Compatibilidad operacional inmediata — Issue #53 | NOT_APPLICABLE_WITH_JUSTIFICATION | Historical compatibility rule for a specific prior Issue/HOLD must remain traceable but is not a reusable platform-workflow function. | Do not import Issue #53/AI Studio quota state into iOS. Future equivalent availability/quota blockers use generic HOLD/current-decision/recovery/external-actor rules. | BASE + AUDIT | Provenance appendix only | None; normative omission justified because safety function is preserved elsewhere. |
| 30. RESEARCH_GATE + STRATEGIC_RATIONALE | PRESERVE | Require research when a material unknown/current fact can change architecture/implementation; record rationale. | iOS facts are platform-specific; gate semantics remain unchanged. | BASE + I5 + ISSUE8 | Research / freshness gate | None. |
| 30.1 Cuándo se activa RESEARCH_GATE | ADAPT | Trigger on material uncertainty/current external fact, not curiosity. | Examples: Xcode/macOS compatibility, current SDK/submission requirement, App Store/TestFlight policy, provider/device capability or current account requirement when material. | BASE + I4 + I5 | Research trigger | Only concrete triggered fact. |
| 30.2 Investigación y evidencia | ADAPT | Prefer primary/official sources; separate fact/inference/recommendation/unknown. | Use Apple/Xcode/App Store Connect official sources when fresh research is triggered; accepted Issue #2 evidence otherwise. | BASE + I4 + I5 | Research evidence discipline | None. |
| 30.3 Verificación del Supervisor | PRESERVE | Supervisor independently evaluates research relevance/quality before authority changes. | No iOS-specific semantic change. | BASE | Supervisor research review | None. |
| 30.4 STRATEGIC_RATIONALE | PRESERVE | Persist why a material technical/architecture choice is justified. | iOS-specific rationale references accepted evidence and project facts without freezing volatile platform data. | BASE + I5 | Strategic rationale | None. |
| 30.5 Aplicación por rol y límites de autoridad | PRESERVE | Research informs decisions but does not transfer authority or scope. | No iOS-specific semantic change. | BASE + CORE | Research authority boundary | None. |
| 31. TECHNICAL PERMISSION != WORKFLOW AUTHORITY | PRESERVE | Technical access/capability never equals Workflow authority. | Exact accepted invariant retained. | BASE + CORE + ACTOR + AUDIT | Technical permission / authority boundary | None. |
| 31.1 Escritura de repositorio/product-code | PRESERVE | Repository/product writes require explicit Semantic + Path Scope authority. | Xcode/macOS/signing/account tool access does not expand repository write authority. | BASE + CORE + ACTOR | Repository write authority | None. |
| 31.2 Escalación AI Studio | ADAPT | External technical escalation remains subordinate to Workflow authority. | Generalize AI Studio to optional Mac/Xcode/device/signing-support actor; escalation never creates semantic/merge/publication authority. | BASE + ACTOR + I5 | External actor escalation boundary | None. |
| Resultado | ADAPT | Summarize operational system without replacing normative sections. | iOS result summarizes Human→Supervisor→Issue→Implementer→Mac/Xcode verification→review while retaining Apple-specific mechanics, provider neutrality outside unavoidable Apple coupling, and authority boundaries. | BASE + I5 | Result / workflow synopsis | None. |
| Apéndice A — Provenance de mejoras consolidadas | ADAPT | Preserve provenance of inherited/adopted rules. | Trace baseline plus accepted Issue #2 iOS/shared artifacts and Issue #8 architecture authorities; do not rewrite history. | BASE + AUDIT + ISSUE8 | Provenance appendix | None. |
| Apéndice B — Handover canónico | ADAPT | Prevent ambiguous coexistence of old/new normative sources and record handover status. | Until explicit adoption, future iOS workflow remains PROPOSAL — NOT CANONICAL; handover/adoption requires later authority. | BASE + ISSUE8 | Status / adoption appendix | Future canonical adoption decision. |
| Apéndice C — Matriz completa de trazabilidad del baseline | EXTEND | Provide complete baseline coverage proof. | Use this iOS adaptation matrix and future workflow cross-check as acceptance evidence; include accepted Issue #2 controls without erasing baseline mapping. | BASE + CORE + AUDIT + ISSUE8 | Baseline traceability appendix / DoD | None. |

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
that baseline rule persisted a specific historical Issue #53 / AI Studio quota/HOLD compatibility state. It is not a reusable iOS platform mechanic. Its safety function remains explicit through generic `HOLD`, current-decision, recovery, external-actor gating, STOP/escalation and Human publication rules.

No other baseline section/subsection is omitted.

## iOS-specific insertions required by accepted evidence

The future `IOS_WORKFLOW.md` must operationalize at least:

### 1. macOS/Xcode environment boundary

Record material project facts such as:
- project/workspace;
- scheme;
- configuration;
- supported macOS/Xcode combination;
- Apple SDK/deployment target;
- dependency state;
- test plans/destinations;
- deterministic project-native `xcodebuild` or equivalent commands.

Do not encode “latest Xcode” or a current App Store policy as a permanent invariant.

Native iOS app compilation, Simulator execution, archive/export and signing remain macOS/Xcode-bound where Apple tooling is required.

Pure Swift/package/domain work may be portable only when its dependencies actually support that execution environment.

### 2. Build/test evidence ladder

Base evidence should be project-native and risk-driven:
- Swift Testing and/or XCTest or project-native equivalents where applicable;
- affected scheme/configuration build/test;
- retained result evidence such as `.xcresult` when produced.

Add Simulator evidence for UI/runtime integration when required.

Add physical-device evidence when Simulator fidelity is insufficient, including hardware, performance, device-only behavior or release-critical real-device semantics.

`SIMULATOR CAPABILITY != PHYSICAL-DEVICE CAPABILITY`.

### 3. Provider-neutral Mac/device adapter

Possible implementations include:
- local/self-hosted Mac;
- authorized macOS CI runner;
- Xcode Cloud;
- another authorized macOS CI provider;
- Simulator;
- physical Apple device;
- authorized device service.

No one provider is mandatory.

Evidence should bind to:
- exact SHA/artifact;
- macOS/Xcode/toolchain;
- project/workspace/scheme/configuration;
- destination/device metadata;
- test selection;
- run/result bundle;
- pass/fail/skip;
- logs/reports;
- retries/deviations;
- unresolved warnings.

### 4. Signing/provisioning boundary

Signing certificates/private keys, provisioning profiles, entitlements and App Store Connect roles are controlled capabilities/assets.

Ordinary implementation contexts should not receive production distribution credentials by default.

Technical possession/use of those capabilities does not create Workflow authority.

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`.

### 5. Archive/export and technical staging

Archive/export/signing/upload/staging are technical operations only when explicitly authorized.

They may produce evidence for a release candidate.

They do not authorize product publication.

`PUBLISH = HUMAN ACTION`.

### 6. TestFlight / App Store / distribution

TestFlight/App Store/enterprise distribution mechanics are iOS platform facts.

A future workflow must distinguish:
- technical build/archive/export/sign/upload/stage capability;
- account/role/credential authority;
- Human product publication action.

No CI, external actor, signing key, App Store Connect role or upload ability transfers publication authority.

### 7. Durable optional external actor

Possible capability-specific actors:
- Mac/Xcode build operator;
- Simulator/device operator;
- signing-support operator;
- technical archive/export/staging operator.

Every invocation requires durable GitHub activity:

`request → authority → execution → evidence → result → stop/escalation`

The activity is evidence/continuity only and creates no authority.

### 8. iOS non-symmetry rules

Do not import Android mechanics:
- no Gradle/AGP;
- no compileSdk/targetSdk/minSdk;
- no APK/AAB;
- no Android API/ABI semantics;
- no Android emulator/Gradle Managed Device;
- no Firebase Test Lab requirement;
- no Play Console/Play signing model;
- no Compose/View/Java migration rule.

Also do not claim Linux-native iOS application build merely because Swift can run on Linux.

Apple-required Xcode/signing/distribution coupling is a real iOS boundary and must not be abstracted away for symmetry.

## Decisions intentionally deferred to the future iOS Work Item/project

The architecture does not invent:
- exact macOS/Xcode versions;
- exact project/workspace/scheme/configuration;
- exact deployment target/SDK combination;
- exact Swift/Objective-C/SwiftUI/UIKit mix;
- exact CI provider/Mac capacity;
- exact build/test/static-analysis commands;
- exact test plan/destinations;
- Simulator matrix;
- physical-device matrix;
- certificate/private-key custody;
- provisioning strategy/profile ownership;
- entitlements;
- archive/export method and artifact form;
- App Store Connect roles;
- TestFlight/App Store technical staging permissions;
- enterprise/distribution channel;
- runner/device/provider cost or quota;
- current Apple SDK/submission policy at release time;
- concrete Human publication action.

These remain project/Work Item facts under explicit authority and, for volatile external facts, the Research/Freshness Gate.

## Research decision

Fresh research triggered:
NO

Reason:
the accepted Issue #2 iOS evidence is sufficient to classify the baseline and define the durable platform deltas required by this matrix. No current volatile fact is needed to complete the architecture/adaptation artifact.

Any future concrete iOS Work Item that depends on current Xcode/SDK/App Store/provider requirements must activate the Research/Freshness Gate at that time.

## Acceptance condition for future IOS_WORKFLOW.md

The future standalone workflow fails the baseline-coverage gate if:
- any of the 71 rows above lacks a target implementation;
- a classification changes without explicit authority/evidence;
- any of the six Work Item fields is grouped away;
- an accepted invariant is compressed away;
- `PUBLISH = HUMAN ACTION` is weakened;
- `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY` is weakened;
- exact-SHA review or GitHub recovery is weakened;
- external-actor durability is omitted;
- Issue #2 becomes a normal execution dependency;
- Android mechanics are copied into iOS;
- Apple-required iOS mechanics are erased to force cross-platform symmetry;
- current Apple/toolchain policy is frozen as timeless workflow semantics.

Any unexplained loss, weakening, substitution or reinterpretation is a HARD VETO.
