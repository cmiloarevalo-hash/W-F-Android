# Android Baseline Adaptation Matrix

STATUS: PROPOSAL — NOT CANONICAL
GOVERNING WORK ITEM: Issue #8
ARCHITECTURE AUTHORITY: comment 5882550265
EXPECTED SOURCE BASE: 84172391dce91e9aa14d433b4859ae6f8f5bac0c

## Purpose

This matrix is the lossless section-by-section bridge from the frozen functional baseline to a future standalone ANDROID_WORKFLOW.md.

It does not implement ANDROID_WORKFLOW.md.

Rules:
- every real baseline heading outside code examples is represented;
- no silent omission;
- classification is one of PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION;
- accepted Issue #2 research is reused; Candidate/scoring research is not repeated;
- any later Android workflow must trace back to this matrix and the Workflow Document Contract.


Source codes:
- BASE = references/WORKFLOW_BASE_ORIGINAL.md, blob fa6ce8e396e1ae422ce4feab3f97d7d37bb43f83
- A4 = workpacks/cross-platform-workflows-cycle-01/outputs/03/android-candidate-4-presentation.md, blob f33baab02f1631ca081678c916508f24b6e44745
- CORE = outputs/08/common-governance-core.md, blob 8c8e46ebd54ed8110848e3d7035171692d53050c
- ACTOR = outputs/08/external-actor-interface.md, blob 8f742c1f362b5ac726c1429f7bbc075d2f0926db
- DELTA = outputs/08/platform-deltas.md, blob 8d327278ec87c20cf2589e771163f9ab80359056
- AUDIT = outputs/09/contradiction-audit.md
- FINAL-A = outputs/10/android-workflow-proposal.md, blob a23291787f27b29330d623b7b69abb1adabec74f
- ISSUE8 = Issue #8 Human/Supervisor architecture authority, especially comments 5882543491 and 5882550265


## Coverage matrix

| Baseline section/subsection | Classification | Preserved operational function | Android delta | Accepted evidence/source | Target ANDROID_WORKFLOW section | Unresolved decision |
|---|---|---|---|---|---|---|
| Document header / status / provenance | ADAPT | Declare workflow identity, canonical status and provenance. | Android workflow must identify Android platform, Issue #8 authority and accepted source chain. | BASE + ISSUE8 | Document status / authority / provenance | Canonical adoption remains separate. |
| Estado de procedencia | EXTEND | Retain provenance and supersession history. | Add Issue #2 accepted evidence library and Issue #8 architecture/adaptation authorities. | BASE + AUDIT + ISSUE8 | Provenance / maintenance | None. |
| 1. Objetivo | ADAPT | State collaborative workflow objective. | Objective becomes standalone Android operational workflow while preserving baseline lifecycle. | BASE + A4 + FINAL-A | Purpose / audience / usage | None. |
| 2. Principio fundamental | PRESERVE | GitHub/documents are durable memory; chat is not authority. | No Android-specific semantic change. | BASE + CORE | Fundamental principles | None. |
| 3. Responsabilidades | PRESERVE | Separate Human, Supervisor, Implementer, GitHub/evidence responsibilities. | Android duties are added under role-specific sections, not by changing authority. | BASE + CORE | Roles / responsibilities / authority | None. |
| 3.1 Chat Web GPT | PRESERVE | Supervisor plans, scopes, reviews, decides; does not self-implement reviewed task normally. | Android evidence/device/release checks become review inputs only. | BASE + CORE | Supervisor role contract | None. |
| 4. Agente implementador | EXTEND | Implement authorized change, verify, diff, commit/PR, report; no self-approval. | Add Android environment, Gradle/SDK, host/device verification responsibilities. | BASE + A4 + FINAL-A | Implementer role contract | Project-specific commands supplied by project. |
| 5. GitHub | PRESERVE | Persistent control plane for Issue, branch, commit, PR, diff, CI and decisions. | No Android-specific semantic change. | BASE + CORE | GitHub / evidence systems | None. |
| 6. Documentación del proyecto | ADAPT | Distinguish product documentation from workflow documentation. | Android workflow may reference Android project engineering docs but remains separate from app documentation. | BASE + ISSUE8 | Reading/context policy + provenance | Exact project doc paths are project-specific. |
| 7. Unidad de trabajo: GitHub Issue | PRESERVE | Six-field Work Item contract. | Android environment/device/release details populate fields without replacing them. | BASE + CORE + A4 | Work Item contract | None. |
| 8. Dos tipos de scope | PRESERVE | Semantic Scope and Path Scope both required. | No Android-specific semantic change. | BASE + CORE | Semantic Scope + Path Scope | None. |
| Semantic Scope | PRESERVE | Authorize behavior/change, not paths. | No Android-specific semantic change. | BASE + CORE | Semantic Scope | None. |
| Path Scope | PRESERVE | Authorize files/modules, not behavior. | No Android-specific semantic change. | BASE + CORE | Path Scope | None. |
| 9. Flujo completo | ADAPT | Preserve end-to-end Human→Supervisor→Issue→Implementer→review lifecycle. | Insert Android environment contract and risk-tiered host/device verification before evidence handoff. | BASE + A4 + CORE | End-to-end lifecycle | None. |
| Fase A — intención | PRESERVE | Human intent analyzed for objective, architecture, risk, scope, verification. | Android risk includes platform/device/release concerns where material. | BASE + A4 | Human intent / Supervisor preparation | None. |
| Fase B — creación del Work Item | PRESERVE | Bounded Work Item, ideally one objective/branch/PR. | Android verification and environment requirements go into the same six-field contract. | BASE + CORE | Work Item creation | None. |
| 10. Inicio del Agente implementador | PRESERVE | Short pointer-based prompt; GitHub holds detail. | No Android-specific semantic change. | BASE | Implementer start | None. |
| 11. Bootstrap del Agente implementador | EXTEND | Answer material authority/scope/base/context/test questions before edits. | Add Android toolchain, module/variant, emulator/device capability, signing/release-impact questions. | BASE + A4 + FINAL-A | Implementer bootstrap | Concrete project environment facts resolved per Work Item. |
| 12. Política de lectura | ADAPT | Progressive disclosure; read only necessary context. | Read platform workflow first, then Android/project docs and affected Gradle/modules/tests; Issue #2 is provenance, not normal execution dependency. | BASE + ISSUE8 | Reading / context policy | None. |
| 13. Implementación | EXTEND | Minimal authorized change; no opportunistic refactor/infrastructure. | Respect Android architecture/contracts and environment/toolchain constraints; keep device dependence risk-driven. | BASE + A4 | Implementation discipline | Project architecture may constrain details. |
| 14. Problemas descubiertos durante el trabajo | PRESERVE | In-scope related issue may be fixed; unrelated reported; scope expansion stops. | No Android-specific semantic change. | BASE | Discovered-problem handling | None. |
| 15. Verificación local | ADAPT | Run relevant checks, correct, rerun, inspect full diff. | Android base verification: relevant JVM/local tests + lint + affected compile/assemble/build; device evidence when risk classifier requires. | BASE + A4 + FINAL-A | Verification model | Exact commands/matrix are project-specific. |
| 16. Publicación | ADAPT | Commit/push/PR publication of the proposed change for review. | Rename operational meaning to REPOSITORY_PUBLICATION to avoid conflating with product PUBLISH. Implementer may commit/push/PR; product PUBLISH remains Human action. | BASE + CORE + AUDIT | Repository handoff / PR publication | None. |
| 17. Handoff del Agente implementador | EXTEND | Compact durable report with Work Item, PR, commit, verification, CI and state. | Add Android environment/device evidence references when applicable. | BASE + A4 | Implementer handoff | None. |
| 18. Revisión de Chat Web GPT | EXTEND | Independent review of Issue, diff, architecture, tests, docs, PR, SHA, CI. | For Android, verify host/device evidence, environment contract and publication/signing boundaries where relevant. | BASE + A4 + CORE | Supervisor exact-SHA review | None. |
| 19. Significado de las decisiones | PRESERVE | Closed Supervisor semantic state vocabulary. | No Android-specific decision states. | BASE + CORE | Formal decisions | None. |
| SEMANTIC_ACCEPTED | PRESERVE | Work Item intent satisfied for exact reviewed SHA; not automatic merge. | No Android-specific semantic change. | BASE + CORE | SEMANTIC_ACCEPTED | None. |
| REWORK | PRESERVE | Correction required within same objective. | No Android-specific semantic change. | BASE + CORE | REWORK | None. |
| HOLD | PRESERVE | Objective blocker cannot currently be resolved. | Android examples may include unavailable device/credential/provider capability; semantics unchanged. | BASE | HOLD | None. |
| ESCALATE | PRESERVE | Human/material decision required. | Android examples may include signing/store/cost/scope decisions; semantics unchanged. | BASE + A4 | ESCALATE | None. |
| 20. REWORK | PRESERVE | Same-objective correction stays same Issue/branch/PR; new SHA needs new review. | Use focused platform REWORK; no new broad research cycle by default. | BASE + CORE + ISSUE8 | REWORK procedure | None. |
| 21. Decisión vigente | PRESERVE | Latest Supervisor decision explicitly associated with current HEAD is valid. | No Android-specific semantic change. | BASE + CORE | Current-decision rule | None. |
| 22. CI | ADAPT | CI produces reproducible exact-SHA mechanical evidence; PASS != approval. | Replace baseline npm-specific commands with project-native Android/Gradle commands; device jobs only when risk requires. GitHub Actions remains project CI when configured. | BASE + A4 + CORE | CI / evidence discipline | Concrete project CI commands/configuration. |
| 23. Integración | PRESERVE | READY_FOR_REVIEW→SEMANTIC_ACCEPTED→target checks→MERGE_ELIGIBLE→MERGED→CLOSED. | No Android-specific semantic change. | BASE + CORE | Integration / merge eligibility | None. |
| 24. Merge | PRESERVE | Supervisor-only merge after exact-SHA acceptance and eligibility checks when separately authorized. | No Android-specific semantic change. | BASE + CORE | Merge boundary | Repository-specific merge authority still governs. |
| 25. Cambio de sesión del Agente implementador | EXTEND | Fresh Implementer reconstructs from GitHub, not transcript. | Also recover Android environment contract and last platform-specific evidence/device state. | BASE + CORE | Implementer session recovery | None. |
| 26. Cambio de sesión de Chat Web GPT | EXTEND | Fresh Supervisor reconstructs product/work item/scope/HEAD/evidence/latest decision. | Also recover Android environment, platform risk/evidence and unresolved release/device decisions. | BASE + CORE | Supervisor session recovery | None. |
| 27. Rol del humano | EXTEND | Human owns intent, priorities, permissions, credentials, trade-offs and publication. | Preserve exact PUBLISH = HUMAN ACTION for Android Play/other product publication; Human does not become code implementer. | BASE + CORE + AUDIT | Human role + product publication boundary | Concrete store/account role per project. |
| 28. Reglas esenciales | EXTEND | Retain durable memory, Issue authority, role separation, dual scope, exact-SHA review, evidence≠approval, REWORK continuity, recovery. | Add HARD VETO non-regression, PUBLISH = HUMAN ACTION, TECHNICAL CAPABILITY != WORKFLOW AUTHORITY, platform-delta preservation. | BASE + CORE + AUDIT | Fundamental principles / invariants | None. |
| 29. AI_STUDIO_OPERATOR — fallback excepcional por escalamiento verificado | ADAPT | Preserve function: optional subordinate external capability, never an authority source. | Replace provider-specific AI Studio role with optional Android external actor/device/build/signing-support operator under accepted generic actor contract. | BASE + ACTOR + A4 | Optional external-actor protocol | Provider chosen only when project need/authority exists. |
| 29.1 Permission Matrix | ADAPT | Explicit allowed/forbidden capabilities and Human/Supervisor boundaries. | Use capability-specific Android actor authority matrix; technical capability never grants Workflow authority. | BASE + ACTOR + CORE | External actor authority matrix | Exact actor capability per activity. |
| 29.2 Gate universal de escalamiento AI Studio | ADAPT | External escalation only after bounded need/blocker and Supervisor verification. | Generic gate: invoke external Android capability only when required and explicitly authorized; no provider-by-default. | BASE + ACTOR | External actor invocation gate | None. |
| 29.3 Inicio: AI_STUDIO_REQUEST y modos técnicos | ADAPT | Persist explicit request, objective, baseline, operations, evidence and stop conditions. | Use durable external-actor activity record per Issue #2 rule 5879863384; provider-specific modes are not universal. | BASE + ACTOR | External actor activity start | Exact actor/provider mode if selected. |
| 29.4 SHA Gate y evidencia | EXTEND | Bind external activity to expected SHA/baseline and evidence. | Add artifact hashes, Android device/API/ABI/form-factor/config where applicable. | BASE + ACTOR + A4 | External actor baseline/evidence gate | Exact test matrix per Work Item. |
| 29.5 Ventana única de intervención | ADAPT | External action is bounded in time/scope and returns control. | Represent as one persisted bounded activity/invocation; repeat requires renewed authority/evidence when baseline changes. | BASE + ACTOR | External actor bounded execution | None. |
| 29.6 Clasificación, seguridad operacional y recuperación | ADAPT | Classify result/blocker safely, protect secrets, reconstruct activity. | Use generic Android actor result/evidence/STOP/recovery rules and durable lifecycle. | BASE + ACTOR | External actor result / recovery | None. |
| 29.7 Publicación — exclusiva del Humano | PRESERVE | Product publication belongs exclusively to Human. | Exact invariant PUBLISH = HUMAN ACTION; Android signing/upload ability never transfers publication authority. | BASE + CORE + AUDIT | Product publication boundary | None. |
| 29.8 RESEARCH_GATE y SPIKE_READ_ONLY | ADAPT | Use read-only research spike for unresolved external facts/capabilities before unsafe action. | Apply to volatile Android SDK/Play/provider/device capability facts only when materially required; reuse Issue #2 otherwise. | BASE + A4 + ISSUE8 | Research / freshness gate | Current external fact only when triggered. |
| 29.9 Regla absoluta de no escritura de repositorio/product-code | ADAPT | External operator default is no unauthorized repository/product mutation. | Generic actor may write only if its activity + Work Item explicitly authorize implementation; default deny outside enumerated operations. Publication still Human-only. | BASE + ACTOR | External actor forbidden operations | Exact actor write capability if ever authorized. |
| 29.10 AI_STUDIO_REPORT y STOP obligatorio | ADAPT | External actor returns structured report and stops. | Use durable RESULT/evidence/STATUS and mandatory STOP/escalation after bounded activity. | BASE + ACTOR | External actor result / STOP | None. |
| 29.11 Fallback de mutación externa de plataforma | ADAPT | External platform mutation requires exact target/scope, baseline, before/after evidence, rollback when applicable, and stop conditions. | Android may require bounded non-publication store/device/provider configuration; no code/repo/publication authority follows. | BASE + ACTOR + A4 | External platform mutation protocol | Specific external mutation only by Work Item. |
| 29.12 Compatibilidad operacional inmediata — Issue #53 | NOT_APPLICABLE_WITH_JUSTIFICATION | Historical compatibility rule for a specific prior Issue/HOLD must remain traceable but is not a reusable platform-workflow function. | Do not import Issue #53/AI Studio quota state into Android. Equivalent future compatibility/HOLD state is handled by generic HOLD/current-decision/recovery rules. | BASE + AUDIT | Provenance appendix only | None; omission from normative Android procedure is justified. |
| 30. RESEARCH_GATE + STRATEGIC_RATIONALE | PRESERVE | Require research when a material unknown/current fact can change architecture/implementation; record rationale. | Android sources/facts are platform-specific; gate semantics remain unchanged. | BASE + A4 + ISSUE8 | Research / freshness gate | None. |
| 30.1 Cuándo se activa RESEARCH_GATE | ADAPT | Trigger on material uncertainty/current external fact, not curiosity. | Examples: Android SDK/AGP/JDK compatibility, Play policy, device/provider capability when material. | BASE + A4 | Research trigger | Only concrete triggered fact. |
| 30.2 Investigación y evidencia | ADAPT | Prefer primary/official sources; separate fact/inference/recommendation/unknown. | Use Android Developers/Google Play/toolchain official sources when fresh research is triggered; Issue #2 accepted evidence otherwise. | BASE + A4 | Research evidence discipline | None. |
| 30.3 Verificación del Supervisor | PRESERVE | Supervisor independently evaluates research relevance/quality before authority changes. | No Android-specific semantic change. | BASE | Supervisor research review | None. |
| 30.4 STRATEGIC_RATIONALE | PRESERVE | Persist why a material technical/architecture choice is justified. | Android-specific rationale references accepted evidence and project facts. | BASE + A4 | Strategic rationale | None. |
| 30.5 Aplicación por rol y límites de autoridad | PRESERVE | Research informs decisions but does not transfer authority or scope. | No Android-specific semantic change. | BASE + CORE | Research authority boundary | None. |
| 31. TECHNICAL PERMISSION != WORKFLOW AUTHORITY | PRESERVE | Technical access/capability never equals Workflow authority. | Exact accepted invariant retained. | BASE + CORE + ACTOR + AUDIT | Technical permission / authority boundary | None. |
| 31.1 Escritura de repositorio/product-code | PRESERVE | Repository/product writes require explicit Semantic + Path Scope authority. | Android tool access does not expand write authority. | BASE + CORE + ACTOR | Repository write authority | None. |
| 31.2 Escalación AI Studio | ADAPT | External technical escalation remains subordinate to Workflow authority. | Generalize AI Studio to optional Android external actor; escalation never creates semantic/merge/publication authority. | BASE + ACTOR | External actor escalation boundary | None. |
| Resultado | ADAPT | Summarize the operational system without replacing its normative sections. | Android result summarizes Human→Supervisor→Issue→Implementer→Android verification→review while retaining provider neutrality and authority boundaries. | BASE + A4 | Result / workflow synopsis | None. |
| Apéndice A — Provenance de mejoras consolidadas | ADAPT | Preserve provenance of inherited/adopted rules. | Trace baseline plus Issue #2 accepted artifacts and Issue #8 architecture authorities; do not rewrite history. | BASE + AUDIT + ISSUE8 | Provenance appendix | None. |
| Apéndice B — Handover canónico | ADAPT | Prevent ambiguous coexistence of old/new normative sources and record handover status. | Until explicit adoption, Android workflow remains PROPOSAL — NOT CANONICAL; handover/adoption requires later authority. | BASE + ISSUE8 | Status / adoption appendix | Future canonical adoption decision. |
| Apéndice C — Matriz completa de trazabilidad del baseline | EXTEND | Provide complete baseline coverage proof. | Use this Android adaptation matrix and final workflow cross-check as acceptance evidence; include new Issue #2 controls without erasing baseline mapping. | BASE + CORE + AUDIT + ISSUE8 | Baseline traceability appendix / DoD | None. |

## Coverage self-check

Real baseline headings covered by this matrix:
65

NOT_APPLICABLE_WITH_JUSTIFICATION:
- 29.12 Compatibilidad operacional inmediata — Issue #53 only.

Reason:
It is an Issue-specific transitional compatibility rule, not a reusable Android lifecycle function. Its general safety functions are already preserved through HOLD, current-decision, recovery, external-actor and publication rules.

No other baseline section/subsection is omitted.

## Android-specific insertions required by accepted evidence

The future ANDROID_WORKFLOW.md must operationalize at least:

1. Environment contract
- Gradle wrapper;
- Android Gradle Plugin compatibility;
- JDK/toolchain;
- compileSdk/targetSdk/minSdk;
- Kotlin/UI stack versions;
- required SDK components;
- deterministic project-native build/test/lint commands;
- network/dependency policy.

2. Verification tiers
Base:
- relevant local/JVM tests;
- Android lint;
- affected compile/assemble/build.

Risk-triggered device evidence for:
- Android framework/UI semantics;
- lifecycle/configuration;
- permissions/intents/services;
- persistence/device-only behavior;
- hardware/sensor/camera/Bluetooth/vendor behavior;
- API/form-factor compatibility;
- release-critical journeys.

3. Device adapter
Provider-neutral inputs/outputs with exact artifacts, hashes, device/API metadata, test selection, pass/fail/skip, logs/reports and retry history.

4. Signing/release boundary
Technical build/sign/upload capability does not create publication authority.

PUBLISH = HUMAN ACTION.

5. Optional external actor
No provider is mandatory.
Every invocation requires durable GitHub activity:
request → authority → execution → evidence → result → stop/escalation.

6. Platform non-symmetry
- host build != emulator/device capability;
- Android signing/store semantics remain Android-specific;
- Firebase Test Lab is optional;
- no iOS/Web mechanics are imported for symmetry.

## Decisions intentionally deferred to the future Android Work Item/project

The architecture does not invent:
- exact Android project/toolchain versions;
- exact module/variant names;
- exact CI commands beyond the project-native contract;
- emulator/device/API/form-factor matrix;
- device-lab provider;
- signing custody implementation;
- Play/account roles;
- quota/cost limits;
- product publication channel beyond the Human publication invariant.

These become project/Work Item facts under explicit authority.

## Acceptance condition for future ANDROID_WORKFLOW.md

The future workflow fails the baseline-coverage gate if:
- any row above has no target implementation;
- a classification changes without explicit authority/evidence;
- an accepted invariant is compressed away;
- Issue #2 research becomes a normal execution dependency;
- Android-specific mechanics are generalized into false cross-platform rules.

HARD VETO applies to unexplained loss or weakening.
