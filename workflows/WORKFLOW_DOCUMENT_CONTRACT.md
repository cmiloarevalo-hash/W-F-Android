# Workflow Document Contract

STATUS: PROPOSAL — NOT CANONICAL
GOVERNING WORK ITEM: Issue #8
ARCHITECTURE AUTHORITY: Issue #8 comments 5882543491 and 5882550265
ACCEPTED SOURCE BASE: 84172391dce91e9aa14d433b4859ae6f8f5bac0c

## 1. Product definition

A platform workflow is a standalone operational document that adapts the functional Workflow baseline to one engineering platform without weakening its lifecycle, authority boundaries, recovery model, verification discipline, handoff/review mechanics, merge boundary, publication boundary, research gate, or external-actor controls.

A platform workflow is not:
- an executive summary;
- a research report;
- a Candidate 4 presentation;
- a link collection that requires reconstructing procedure from Issue #2;
- a new canonical baseline merely because it is semantically accepted as a proposal artifact.

### Audience

Primary consumers:
- Human;
- Supervisor;
- Implementer;
- optional external actor operating under a persisted activity contract.

GitHub/CI are evidence and persistence systems, not decision-making actors.

### Standalone requirement

A fresh authorized Implementer or Supervisor must be able to execute/review a normal Work Item using:
- repository;
- active Work Item;
- platform workflow;
- project documentation explicitly referenced by that workflow.

Normal execution MUST NOT require reconstructing procedure from Issue #2 research artifacts. Issue #2 remains provenance and accepted evidence.

## 2. Governing design rule

MEJORA = BASELINE FUNCIONAL + ADAPTACIÓN JUSTIFICADA

Every baseline function is preserved, adapted, extended, or explicitly classified not applicable with justification.

No silent omission is permitted.

The nine protected baseline guarantees remain a minimum non-regression set, not a substitute for section-level operational coverage.

## 3. Source precedence and normative/evidence separation

When sources differ, use this precedence:

1. Current Human/Supervisor authority in the governing Work Item.
2. Functional baseline for lifecycle and operational structure.
3. Accepted Common Core / non-regression rules from Issue #2.
4. Accepted platform evidence, deltas, actor contract, and platform synthesis from Issue #2.
5. Presentation summaries only as summaries/checks.

Rules:
- Current Work Item authority controls scope.
- The baseline controls inherited operational function.
- Accepted Issue #2 research supports justified platform adaptation.
- Evidence does not create authority.
- A shorter derivative document cannot silently override a more complete normative rule.
- Volatile external facts are re-researched only when materially required by the Research/Freshness Gate.

## 4. Mandatory document architecture

Every standalone platform workflow MUST contain the following operational functions. Headings may be renamed only if traceability remains explicit.

0. Document status, authority, provenance, and source precedence.
1. Purpose, audience, and usage.
2. Fundamental principles.
3. Roles, responsibilities, and authority boundaries.
4. Terminology, notation, and state vocabulary.
5. Work Item contract.
6. Semantic Scope + Path Scope.
7. End-to-end lifecycle.
8. Human intent / Work Item creation.
9. Implementer bootstrap.
10. Reading and context policy.
11. Platform environment contract.
12. Implementation discipline.
13. Discovered-problem handling.
14. Verification model.
15. CI, evidence, and checkpoint discipline.
16. Repository handoff / PR publication procedure.
17. Implementer handoff.
18. Supervisor exact-SHA review.
19. Formal Supervisor decisions.
20. REWORK procedure.
21. Current-decision rule.
22. Integration and merge eligibility.
23. Merge boundary.
24. Product publication boundary.
25. Implementer session recovery.
26. Supervisor session recovery.
27. Human role.
28. Research/Freshness Gate + Strategic Rationale.
29. Optional external-actor protocol + durable GitHub activity.
30. Technical permission / Workflow authority boundary.
31. Platform-specific deltas.
32. Definition of Done and acceptance tests.
33. Execution templates/checklists.
34. Provenance and maintenance.

The document may be compact, but none of these operational functions may disappear.

## 5. Roles and normative contracts

### 5.1 Human

MUST:
- define product intent and priorities;
- provide/authorize credentials, authentication, material costs, provider commitments, and exceptional permissions when needed;
- execute product publication.

MAY:
- change product direction or material scope;
- approve exceptional trade-offs.

MUST NOT be treated as:
- routine code implementer;
- substitute for durable GitHub evidence.

Reserved decisions:
- product intent;
- material scope change;
- architecture/Workflow adoption when Human authority is required;
- credentials/account permissions;
- product publication.

Required evidence/output:
- persisted Human decision when it changes authority, scope, cost, credential use, or publication.

### 5.2 Supervisor

MUST:
- translate Human intent into bounded Work Items;
- define/verify Objective, Acceptance Criteria, Semantic Scope, Path Scope, sources, verification, and base;
- independently review exact HEAD and evidence;
- issue only SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE as semantic decisions;
- verify merge eligibility separately from semantic acceptance.

MAY:
- authorize bounded technical activities within governing authority;
- execute merge only when separately authorized by the governing Workflow and merge-eligibility conditions pass.

MUST NOT:
- infer authority from technical capability;
- treat CI/test PASS as semantic approval;
- transfer Human publication authority to a technical actor.

Required output:
- durable exact-SHA decision and evidence references.

### 5.3 Implementer

MUST:
- bootstrap from GitHub;
- operate only inside Semantic Scope + Path Scope;
- implement the authorized task;
- verify relevant behavior;
- review the complete diff;
- persist evidence and handoff;
- stop on material authority/scope/base mismatch.

MAY:
- make bounded implementation choices consistent with existing architecture and Work Item authority;
- report unrelated findings without changing them.

MUST NOT:
- redefine architecture or Workflow without authority;
- expand scope silently;
- self-approve;
- issue SEMANTIC_ACCEPTED or MERGE_ELIGIBLE;
- merge merely because tests pass;
- publish product.

Required output:
- exact ref/SHA, changed paths, verification, evidence, unresolved findings, and state.

### 5.4 Optional external actor

MUST:
- operate only under a persisted activity contract;
- respect exact baseline/ref/artifact identity;
- return only required evidence;
- stop on authority/scope/credential/cost/baseline contradiction.

MAY:
- execute only explicitly authorized technical operations.

MUST NOT:
- create Workflow authority;
- expand Objective, Acceptance Criteria, Semantic Scope, or Path Scope;
- self-approve;
- issue semantic decisions;
- gain merge/publication authority from credentials or technical capability.

Required output:
- durable GitHub activity record and evidence.

### 5.5 GitHub / CI

MUST be treated as:
- persistence/evidence systems.

MUST NOT be treated as:
- semantic decision authority.

CI/TEST PASS != SEMANTIC_ACCEPTED.

## 6. Critical-action authority matrix

| Critical action | DECIDE | EXECUTE | Boundary |
|---|---|---|---|
| Product intent / priorities | Human | Human/Supervisor persists | Technical actors cannot infer it |
| Define bounded Work Item | Supervisor within Human intent | Supervisor | Material intent/scope change escalates |
| Change Semantic Scope | Supervisor if within authority; Human when material | Supervisor persists | Implementer cannot self-expand |
| Change Path Scope | Supervisor | Supervisor persists | Path permission != semantic permission |
| Change document/workflow architecture | Supervisor/Human under explicit authority | Implementer only if tasked | Never opportunistic |
| Implement code/docs | Supervisor authorizes | Implementer | Exact scope only |
| Run tests / collect evidence | Supervisor defines required evidence | Implementer/CI/external actor | Evidence != approval |
| Invoke external actor | Supervisor under governing authority | External actor | Durable activity required |
| Provide/use credentials | Human authorizes/provides; Supervisor bounds use | Authorized technical actor | Credential possession != authority |
| Approve cost/provider commitment | Human unless explicitly delegated | Authorized actor | No silent paid-service commitment |
| Issue SEMANTIC_ACCEPTED | Supervisor | Supervisor | Exact reviewed SHA only |
| Issue REWORK/HOLD/ESCALATE | Supervisor | Supervisor | Durable decision |
| Declare MERGE_ELIGIBLE | Supervisor | Supervisor | Separate from semantic acceptance |
| Merge | Supervisor only when separately authorized | Supervisor | Implementer/external actor never self-merge |
| Product publication | Human | Human | PUBLISH = HUMAN ACTION |

Mandatory invariants:
- TECHNICAL CAPABILITY != WORKFLOW AUTHORITY
- PUBLISH = HUMAN ACTION
- SEMANTIC_ACCEPTED != MERGE_ELIGIBLE
- PATH PERMISSION != SEMANTIC PERMISSION
- CI/TEST PASS != SEMANTIC_ACCEPTED

## 7. Closed terminology, states, and notation

### Formal Supervisor decisions
Only:
- SEMANTIC_ACCEPTED
- REWORK
- HOLD
- ESCALATE

No platform-specific semantic decision state may replace these.

### Integration/lifecycle states
- READY_FOR_REVIEW
- MERGE_ELIGIBLE
- MERGED
- CLOSED

These are operational/integration states, not substitutes for semantic decisions.

### CI/evidence states
- PASS
- FAIL
- PENDING
- NOT CONFIGURED

### Document status
Until explicit adoption:
- PROPOSAL — NOT CANONICAL

### Baseline adaptation classifications
Only:
- PRESERVE
- ADAPT
- EXTEND
- NOT_APPLICABLE_WITH_JUSTIFICATION

These classify coverage; they are not lifecycle states.

### Publication vocabulary

REPOSITORY_PUBLICATION:
- commit/push/PR publication of a proposed change into GitHub for review;
- may be executed by the Implementer when authorized by the Work Item.

PUBLISH / PRODUCT_PUBLICATION:
- externally observable product/store/deployment publication;
- PUBLISH = HUMAN ACTION.

The two meanings MUST NOT be conflated.

### Notation
- A → B: ordered lifecycle transition.
- A != B: explicit semantic non-equivalence.
- exact SHA: immutable review/evidence identity.
- MUST / MUST NOT: normative.
- SHOULD / MAY: guidance/optionality.

## 8. Baseline adaptation contract

Each platform requires a complete section-by-section matrix.

Every baseline section/subsection MUST have:
- baseline identifier/title;
- one classification;
- preserved operational function;
- platform delta;
- accepted evidence/source;
- target workflow section;
- unresolved decision, if any.

Rules:
- PRESERVE: semantic/operational function remains effectively unchanged.
- ADAPT: same function, platform-specific execution/wording.
- EXTEND: baseline function remains and accepted platform evidence adds required controls.
- NOT_APPLICABLE_WITH_JUSTIFICATION: only when the original function truly does not transfer; justification is mandatory.

HARD VETO:
Any unexplained loss, weakening, substitution, or reinterpretation of baseline operational function.

A HARD VETO cannot be compensated by:
- score;
- CI/test success;
- automation;
- portability;
- cost;
- convenience;
- actor capability.

## 9. Lossless derivation / summary-regression gate

No derivative, summary, presentation, handoff, checklist, or generated platform workflow may weaken or omit normative behavior.

Before acceptance:
1. compare derivative against the contract and baseline matrix;
2. verify all mandatory invariants remain explicit;
3. verify authority tables and publication boundary remain unchanged;
4. verify platform deltas remain present;
5. reject any lossy summary as REWORK/HARD VETO when normative meaning changes.

Summaries are non-normative unless separately adopted through an explicit architecture/Workflow decision.

## 10. Durable external-actor activity

Every invocation MUST persist a GitHub activity under the governing Work Item containing:
- ACTIVITY_ID/reference;
- GOVERNING_WORK_ITEM;
- ACTOR_TYPE;
- CAPABILITY;
- OBJECTIVE;
- PRECONDITIONS;
- AUTHORIZED_OPERATIONS;
- FORBIDDEN_OPERATIONS;
- EXPECTED_BASELINE/ref/SHA/artifact identity;
- EVIDENCE_REQUIRED;
- RESULT;
- STOP_CONDITIONS;
- ESCALATION_PATH;
- STATUS.

Required lifecycle:

request → authority → execution → evidence → result → stop/escalation

The activity record is evidence/continuity only; it is not a new authority source.

## 11. Research / freshness behavior

Reuse accepted Issue #2 research.

Do not repeat broad candidate/scoring research during operationalization.

Activate fresh research only when:
- a current external fact is materially required;
- the fact is volatile enough that accepted evidence may be stale;
- a concrete contradiction blocks implementation.

Research must distinguish:
- project fact;
- verified external fact;
- empirical observation;
- inference;
- recommendation;
- unknown.

Primary/official sources are preferred for capability, policy, security, compatibility, and release requirements.

## 12. Platform production / closure loop

Normal loop after architecture acceptance:

### ROUND 1 — BUILD
Supervisor persists one bounded platform BUILD activity.
Implementer produces the complete standalone platform workflow from:
- this contract;
- approved platform adaptation matrix;
- accepted Issue #2 evidence;
- current Work Item authority.

Implementer publishes handoff and stops.

### ROUND 2 — SUPERVISOR REVIEW
Supervisor performs independent exact-HEAD/content review against Definition of Done and acceptance tests.

If PASS:
- platform workflow may be accepted/closed under separate authority.

If correction is required:
- one focused same-objective REWORK is persisted.

### ROUND 3 — OPTIONAL
Only evidence-backed unresolved defects are corrected and reviewed.

Two turns are the default efficiency expectation, not a correctness limit.

If a platform REWORK exposes a defect in this shared architecture contract, STOP platform production and return to architecture review rather than patching the same defect independently across platforms.

## 13. Android exemplar rule

Android is the first exemplar of document architecture.

It is NOT the template for platform mechanics.

Android validates:
- standalone consumption;
- baseline coverage;
- role/authority representation;
- environment contract;
- risk-tiered host/device verification;
- external-actor durability;
- recovery;
- product publication boundary.

After Android is accepted, perform a short architecture-conformance check before iOS:
- identify which structures are genuinely common;
- remove no Android detail from Android;
- prevent Android-specific mechanics from becoming mandatory in iOS/Web.

## 14. Definition of Done

A platform workflow is DONE only when all checks pass:

1. BASELINE COVERAGE
100% of baseline sections/subsections mapped; no silent omission.

2. STANDALONE USABILITY
Fresh Implementer/Supervisor can operate from repository + active Work Item + platform workflow without reconstructing Issue #2 procedure.

3. FULL LIFECYCLE
Human intent → Work Item → bootstrap → implementation → verification → repository handoff → Supervisor review → REWORK/HOLD/ESCALATE or acceptance → merge boundary → Human product publication boundary.

4. AUTHORITY SAFETY
Capability, credentials, CI, path access, or actor identity cannot be read as Workflow authority.

5. EXACT-SHA SEMANTICS
Review and acceptance bind only to exact reviewed HEAD.

6. RECOVERY
Fresh Implementer and Supervisor can reconstruct current state from GitHub.

7. EXTERNAL ACTOR
Full contract + durable activity record.

8. RESEARCH/FRESHNESS
Current facts trigger fresh research only when materially necessary.

9. PLATFORM COMPLETENESS
Build/test/device/browser/signing/distribution constraints are operationally expressed.

10. TEMPLATE COMPLETENESS
Minimum executable templates/checklists are included.

11. PROVENANCE
Every material platform adaptation traces to accepted evidence or an explicit later decision.

12. NON-REGRESSION
No unexplained weakening of baseline function or mandatory invariant.

## 15. Acceptance tests

### TEST A — BASELINE COVERAGE
Every baseline section/subsection appears in the matrix with one valid classification and target workflow section.

### TEST B — HAPPY PATH
Using only platform workflow + representative Work Item:
bootstrap → implement → verify → handoff → Supervisor review → accepted integration path.

### TEST C — REWORK
Supervisor reviews SHA A → REWORK → Implementer produces SHA B → prior acceptance does not carry → SHA B receives new review.

### TEST D — AUTHORITY ADVERSARIAL
The workflow must resolve safely:
- Implementer has store credentials → cannot publish.
- External actor can deploy → cannot publish/approve.
- CI PASS → cannot issue semantic acceptance.
- Authorized path → cannot expand semantic scope.
- Technical capability → cannot create Workflow authority.

### TEST E — STOP / ESCALATION
Wrong base, scope mismatch, missing credential/cost approval, or architecture contradiction produces STOP/HOLD/ESCALATE rather than inference.

### TEST F — SESSION RECOVERY
Fresh Implementer and Supervisor reconstruct Issue, branch/ref, HEAD, PR, evidence, last valid decision, and unresolved state.

### TEST G — EXTERNAL-ACTOR DURABILITY
GitHub reconstructs:
request → authority → execution → evidence → result → stop/escalation.

### TEST H — PLATFORM DELTA
Platform-specific capability boundaries remain explicit.
For Android: host compilation != emulator/device capability; signing/build capability != Play publication authority.

### TEST I — STANDALONE
Normal operation succeeds without opening Issue #2 research artifacts.

### TEST J — SUMMARY REGRESSION
Any summary/checklist is compared to normative invariants and cannot silently become the normative source.

## 16. Minimum execution templates

### Work Item
Objective
Acceptance Criteria
Authorized Scope
Relevant Sources
Verification
Base

### Implementer handoff
WORK ITEM:
BRANCH/PR:
HEAD:
CHANGED PATHS:
VERIFICATION:
CI:
EVIDENCE:
UNEXPECTED FINDING:
STATE: READY_FOR_REVIEW | BLOCKED

### REWORK
PROBLEM:
REQUIRED RESULT:
EVIDENCE:
SCOPE: unchanged | explicitly changed
REVIEWED SHA:
NEXT EXPECTED SHA:

### External actor activity
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

### Recovery checkpoint
REPOSITORY:
WORK ITEM:
ROLE:
BRANCH/REF:
HEAD:
PR:
LATEST VALID DECISION:
REVIEWED SHA:
EVIDENCE:
BLOCKER/REWORK:
NEXT AUTHORIZED ACTION:

## 17. Evidence library for operationalization

Accepted Issue #2 material is reused, not re-researched:
- references/WORKFLOW_BASE_ORIGINAL.md
- workpacks/cross-platform-workflows-cycle-01/outputs/03/android-candidate-4-presentation.md
- workpacks/cross-platform-workflows-cycle-01/outputs/08/common-governance-core.md
- workpacks/cross-platform-workflows-cycle-01/outputs/08/external-actor-interface.md
- workpacks/cross-platform-workflows-cycle-01/outputs/08/platform-deltas.md
- workpacks/cross-platform-workflows-cycle-01/outputs/09/**
- workpacks/cross-platform-workflows-cycle-01/outputs/10/**

Accepted parent state:
84172391dce91e9aa14d433b4859ae6f8f5bac0c

This contract does not implement Android/iOS/Web workflows and does not authorize merge, canonical adoption, or product publication.


## 18. Workflow startup, freshness, and bounded maintenance

Every standalone workflow MUST keep an internal Workflow Source Registry so freshness review starts from known material sources instead of broad rediscovery. Minimum source record:

SOURCE_ID; SUBJECT; SOURCE_REF_OR_URL; SOURCE_TYPE; AUTHORITY_LEVEL; VERSION_OR_DATE_SCOPE; LAST_CHECKED; VOLATILITY; LAST_FINDING; NEXT_REVIEW; NOTES.

Prefer official/primary sources for volatile facts. Accepted repository evidence may use exact SHA/path. Registry metadata is navigation/evidence, not authority. Distinguish stable/internal, volatile/external, and project-specific sources. Do not duplicate full external documents.

At startup for substantial work:

WORKFLOW IDENTITY → SOURCE REGISTRY → LAST_WORKFLOW_FRESHNESS_REVIEW → DUE CHECK → PROJECT/SPECIFICATION READINESS → CAPABILITY/ACTOR PLAN → SESSION PREPARATION → IMPLEMENTATION BOOTSTRAP.

14 DAYS SINCE LAST FRESHNESS REVIEW → LIGHTWEIGHT FRESHNESS CHECK, NOT AUTOMATIC FULL RESEARCH.

The targeted check records sources checked, unchanged/changed/unavailable facts, material-change finding, improvement candidate, limitations, and next review. Outcomes are CURRENT_ENOUGH / MATERIAL_CHANGE_REVIEW_REQUIRED / SOURCE_UNAVAILABLE / WORKFLOW_IMPROVEMENT_CANDIDATE. These are evidence/preflight states only.

WORKFLOW_IMPROVEMENT_CANDIDATE != WORKFLOW CHANGE AUTHORITY. Required flow:

IMPROVEMENT_CANDIDATE → persist rationale → inform Human → Human AUTHORIZE | DECLINE | DEFER → if authorized create one bounded WORKFLOW_CHANGE_UNIT → implementation/research as authorized → exact-SHA Supervisor review.

A WORKFLOW_CHANGE_UNIT records at minimum change ID, target workflow, authority, base SHA, trigger, objective, type, affected sections/invariants/profiles/trace rows, material sources, expected delta, non-affected areas, authorized paths, local/global review, verification, stop conditions, resulting SHA, and state.

Default review is proportional: exact diff → deep review of affected surface/dependencies → affected evidence verification → minimum global-invariant checks → exact-SHA decision. Global checks preserve authority, exact-SHA, Work Item/scopes, decision vocabulary, REWORK/current-decision behavior, merge/publication boundaries, recovery, source precedence, baseline trace, internal references, active profiles, and path/scope boundaries. Expand to broader/full review when impact cannot be bounded or materially affects shared architecture/Contract, authority, state vocabulary, source precedence, adaptation classification, merge/publication semantics, or multiple unrelated regions.

Before substantial product/application implementation verify current specifications, executable Objective/Acceptance Criteria, normative-document consistency, unresolved product decisions, material technical unknowns, volatile facts, credentials/cost, required local/device/external capability, expected evidence, and recovery viability. Product/Human decisions return to Human. Missing/ambiguous material specification stops substantial implementation under current gap rules.

A material technical unknown may produce a bounded research recommendation; recommendation != research authority. Nontrivial research begins only after explicit Human authorization. The routine lightweight freshness check itself needs no separate research activity unless it exposes a material question requiring deeper investigation.

Capability/session planning is proportional. Record whether Implementer, Local Execution Agent, physical device, external service, credential, paid service, or another special capability is required. CAPABILITY REQUIRED != AUTHORITY GRANTED. Activate only actors needed now; future capabilities may be FORESEEN and deferred. GitHub pointers, not transcript dependence, carry durable context.

Reject as defaults: full external research every 14 days; rereading every source on every use; full repository documentation audit; full-workflow rereview for every localized edit; activating every actor at startup; premature Local Agent/device sessions; research just in case; duplicating source contents; automatic workflow modification after freshness findings.

Prefer REGISTERED SOURCES → TARGETED CHECK → DELTA and BOUNDED CHANGE UNIT → IMPACT SURFACE → MINIMUM GLOBAL CHECKS.
