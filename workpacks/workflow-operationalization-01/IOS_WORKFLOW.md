# iOS Operational Workflow

STATUS: PROPOSAL — NOT CANONICAL

PLATFORM: iOS

GOVERNING WORK ITEM FOR THIS DOCUMENT:
Issue #8

ACCEPTED iOS BASELINE ADAPTATION MATRIX:
25e4296877044cb272bedeaaea80befa2cf251d5

ACCEPTED DOCUMENT ARCHITECTURE:
621d4e58eccbc697d42074e5f7eaa53a162a0582

DOCUMENT PURPOSE:
Standalone operational workflow for iOS engineering work executed by Human + Supervisor + Implementer + GitHub/CI, with optional bounded Mac/device/signing-support external actors.

PRIMARY DESIGN RULE:

IOS_WORKFLOW.md = BASELINE FUNCIONAL + ADAPTACIÓN IOS JUSTIFICADA

This document is an operational workflow. It is not a research report, executive summary, Candidate presentation, or automatic canonical replacement for the frozen functional baseline.

No merge, canonical adoption, TestFlight publication, App Store publication, enterprise publication, or other product publication is authorized merely because this document exists or is semantically accepted as a proposal artifact.

---

## 0. Document status, authority, provenance, and source precedence

### 0.1 What this document is

This document defines how an authorized iOS Work Item is:

- created;
- bootstrapped;
- implemented;
- built and tested;
- verified on Simulator and/or physical device when justified;
- handled across signing/provisioning/archive/export boundaries;
- handed off;
- independently reviewed;
- reworked;
- integrated;
- recovered across sessions;
- prepared for Human-controlled product publication when applicable.

It is designed so that a fresh authorized session can operate the normal lifecycle using:

- the repository;
- the active GitHub Issue / Work Item;
- this iOS workflow;
- project documentation explicitly referenced by the Work Item.

Normal operation MUST NOT require reconstructing procedure from Issue #2 research outputs.

### 0.2 What this document is not

This document is not:

- a requirement to use one CI provider;
- a requirement to use Xcode Cloud;
- a requirement to use GitHub-hosted macOS runners;
- a requirement to use one device provider;
- a requirement to migrate Objective-C to Swift;
- a requirement to migrate UIKit to SwiftUI;
- a statement that pure Swift portability implies native iOS app portability;
- an authorization to use production signing credentials;
- an authorization to upload or distribute a build;
- an authorization to publish through TestFlight, the App Store, enterprise distribution, or any other channel;
- a timeless source for volatile Xcode, Apple SDK, App Store Connect, submission, account, or policy facts.

### 0.3 Source precedence

When sources appear to conflict, apply this precedence:

1. Current Human/Supervisor authority in the active governing Work Item.
2. This platform workflow for the normal iOS operational lifecycle, once the active Work Item points to it.
3. Frozen functional baseline for inherited lifecycle semantics and non-regression.
4. Accepted Common Core / authority / external-actor controls from Issue #2.
5. Accepted iOS evidence and platform deltas from Issue #2.
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

Accepted iOS adaptation:
- IOS_BASELINE_ADAPTATION_MATRIX.md;
- accepted at 25e4296877044cb272bedeaaea80befa2cf251d5.

Accepted Issue #2 evidence reused:
- iOS capability matrix;
- iOS evidence ledger;
- iOS Candidate 4;
- Common Governance Core;
- Optional External Actor Interface;
- Platform Deltas;
- Contradiction Audit;
- final iOS workflow proposal;
- final Issue #2 handoff.

Issue #2 evidence is reused.
The comparative Candidate/scoring/sensitivity cycle is not repeated by this workflow.

The accepted Android exemplar is only proof that the shared document architecture is executable. It is not an iOS mechanics source.

---

## 1. Purpose, audience, and usage

### 1.1 Objective

The objective is to provide a complete iOS engineering workflow that:

- preserves the full operational lifecycle of the functional baseline;
- adds iOS-specific macOS/Xcode, build/test, Simulator/device, signing/provisioning, archive/export, and distribution constraints only where justified;
- remains provider-neutral where Apple does not impose a provider;
- preserves unavoidable Apple toolchain/distribution coupling where it is real;
- is recoverable across sessions;
- separates evidence from authority;
- scales runtime/device verification according to technical risk;
- prevents accidental merge, publication, scope expansion, signing misuse, or authority transfer.

### 1.2 Audience

Primary consumers:

- Human;
- Supervisor;
- Implementer / technical writer-engineer / coding agent;
- optional external actor when a concrete missing capability requires one.

Supporting systems:

- GitHub;
- CI;
- macOS build infrastructure;
- Xcode;
- Simulator;
- physical Apple devices;
- signing/provisioning infrastructure;
- App Store Connect technical interfaces where separately authorized.

Supporting systems produce state/evidence.
They do not issue semantic decisions.

### 1.3 When to use this workflow

Use this workflow for iOS Work Items involving:

- iOS application code;
- iOS frameworks/libraries;
- Swift packages used by an iOS product;
- Objective-C or mixed-language modules;
- SwiftUI or UIKit;
- Xcode project/workspace configuration;
- schemes/configurations;
- build settings;
- tests;
- CI;
- Simulator verification;
- physical-device verification;
- entitlements;
- signing/provisioning technical work;
- archive/export technical work;
- technical TestFlight/App Store Connect staging when separately authorized;
- iOS-specific documentation;
- iOS workflow maintenance under explicit authority.

For a non-iOS task, use the appropriate workflow or governing repository instructions.

---

## 2. Fundamental principles

The following rules are always active unless a higher Human/Supervisor authority explicitly changes the governing workflow through a separate decision process.

### 2.1 GitHub is durable memory

The repository, Issue, branch/ref, commits, PR, evidence, CI, Supervisor decisions, and external-actor records are durable state.

Prior chat transcript is not an authority source.

### 2.2 Work Item before substantial work

A sufficiently important task must exist as a bounded GitHub Issue / Work Item.

### 2.3 Two independent scopes

Semantic Scope controls what behavior/change is authorized.

Path Scope controls which files/modules may be changed.

PATH PERMISSION != SEMANTIC PERMISSION.

Both must pass.

### 2.4 Exact-SHA review

Supervisor semantic review applies only to the exact reviewed SHA.

A later commit creates a new HEAD and requires a new semantic decision for that HEAD.

### 2.5 Evidence is not approval

CI/TEST PASS != SEMANTIC_ACCEPTED.

Build success, unit test success, UI test success, Simulator success, physical-device success, archive/export success, signing success, upload success, actor output, or artifact generation remain evidence only.

### 2.6 Capability is not authority

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

A technical actor may possess source access, macOS capacity, Xcode, device access, certificates, private keys, provisioning material, App Store Connect roles, API keys, upload capability, or release tooling and still lack authority to use them for an operation.

### 2.7 Semantic acceptance is not merge eligibility

SEMANTIC_ACCEPTED != MERGE_ELIGIBLE.

Merge requires separate integration checks and appropriate authority.

### 2.8 Product publication is Human action

PUBLISH = HUMAN ACTION.

Build, archive, export, sign, upload, stage, or App Store Connect access does not transfer product publication authority to Implementer, CI, or external actor.

### 2.9 Baseline non-regression is a HARD VETO

Any unexplained loss, weakening, substitution, or reinterpretation of a protected baseline function is a HARD VETO.

A HARD VETO cannot be compensated by:

- score;
- CI success;
- test success;
- automation;
- portability;
- cost;
- convenience;
- provider capability;
- signing capability;
- external-actor capability.

### 2.10 iOS capability boundaries are explicit

PURE SWIFT OR PACKAGE PORTABILITY != NATIVE IOS APPLICATION BUILD CAPABILITY.

SIMULATOR CAPABILITY != PHYSICAL-DEVICE CAPABILITY.

ARCHIVE/EXPORT/SIGN/UPLOAD CAPABILITY != PRODUCT PUBLICATION AUTHORITY.

Native iOS application compilation, Simulator execution, archive/export, and Apple signing operations remain macOS/Xcode-bound where Apple tooling is required.

A passing Simulator test does not automatically prove all physical-device behavior.

A successful archive/export/sign/upload operation does not authorize product publication.

---

## 3. Roles, responsibilities, and authority

### 3.1 Human

#### MUST

The Human MUST:

- define product intent and priorities;
- decide material changes in product direction;
- decide material architecture/Workflow changes when reserved to Human authority;
- provide or authorize credentials, MFA, Apple account access, certificates/private-key use, App Store Connect role use, and material provider permissions when needed;
- decide material costs or paid provider commitments unless explicitly delegated;
- perform product publication.

#### MAY

The Human MAY:

- set risk tolerance;
- approve Mac/device provider budget;
- define supported device/OS product policy;
- approve exceptional trade-offs;
- authorize technical TestFlight/App Store Connect staging;
- explicitly change Work Item intent or architecture through a persisted decision.

#### MUST NOT be treated as

The Human MUST NOT be treated as:

- routine code implementer;
- substitute for durable evidence;
- implicit approver of a signing/upload/publication operation merely because credentials exist.

#### Reserved decisions

Reserved to Human unless a governing decision says otherwise:

- product intent;
- material product scope change;
- credentials/MFA;
- material paid-service commitments;
- publication through TestFlight/App Store/enterprise/other product distribution channels.

#### Required evidence/output

A material Human decision that changes scope, permission, cost, credential use, account role, signing authority, or publication state must be persisted in GitHub.

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
- independently review implementation, tests, documentation, CI, macOS/Xcode evidence, Simulator/device evidence, and signing/release evidence when relevant;
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
- define a Simulator/physical-device evidence matrix when needed;
- define archive/export technical evidence when needed;
- narrow or clarify verification;
- merge only where the governing Workflow and repository authority separately allow it and merge eligibility passes.

#### MUST NOT

The Supervisor MUST NOT:

- treat CI/test PASS as semantic acceptance;
- infer product publication authority from technical capability;
- silently expand Human intent;
- treat an old reviewed SHA as acceptance of a new SHA;
- treat signing/upload evidence as product publication approval.

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
- read the minimum necessary context;
- reconstruct project/workspace/scheme/configuration facts relevant to the task;
- implement only the authorized objective;
- use project-native iOS tooling;
- run required verification;
- inspect the complete diff;
- persist exact commit/PR evidence;
- report unexpected findings;
- stop on authority/scope/base contradiction.

#### MAY

The Implementer MAY:

- choose bounded implementation details consistent with existing architecture;
- add or update tests inside authorized scope;
- use a Simulator or physical device when required and available under authority;
- use an authorized macOS build provider;
- invoke an authorized external actor through the durable activity protocol;
- perform REPOSITORY_PUBLICATION when explicitly allowed;
- perform archive/export/signing/upload technical operations only when the Work Item explicitly authorizes them.

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
- use production signing credentials merely because technically available;
- change Apple account roles by inference;
- upload or distribute merely because a build is technically ready;
- invent current Xcode, Apple SDK, submission, TestFlight, App Store, account, or provider facts.

#### Required evidence/output

At handoff the Implementer must provide:

- Work Item;
- branch/PR;
- exact HEAD;
- changed paths;
- project/workspace/scheme/configuration relevant to verification;
- verification commands/results;
- CI status;
- Simulator/device evidence when required;
- result bundle/artifact/run references when applicable;
- signing/archive/export evidence when applicable;
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
- Supervisor decisions;
- external-actor activity records;
- session recovery.

GitHub does not make semantic decisions by itself.

---

### 3.5 CI

CI:

- runs reproducible mechanical checks;
- associates evidence with a commit;
- may build and test on authorized macOS infrastructure;
- may retain result bundles/artifacts;
- may execute authorized Simulator/device jobs;
- may prepare archives/exports when explicitly authorized.

CI MUST NOT:

- issue SEMANTIC_ACCEPTED;
- issue MERGE_ELIGIBLE;
- merge unless a separately governed automation explicitly has that authority;
- publish a product by inference;
- infer signing/upload/publication authority from credential access.

CI/TEST PASS != SEMANTIC_ACCEPTED.

---

### 3.6 Optional external actor

An external actor is optional.

Examples:

- macOS/Xcode build operator;
- Simulator execution operator;
- physical-device lab operator;
- signing-support operator;
- archive/export technical operator;
- authorized App Store Connect technical staging operator.

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

No iOS-specific decision state may replace these.

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

### 4.5 Repository publication vs product publication

REPOSITORY_PUBLICATION means:

- commit;
- push;
- opening/updating a PR;
- making proposed repository changes available for review.

The Implementer MAY perform REPOSITORY_PUBLICATION when the Work Item authorizes it.

PUBLISH / PRODUCT_PUBLICATION means:

- externally observable product distribution or release;
- TestFlight distribution as a product/beta publication action;
- App Store publication;
- enterprise or other product distribution.

PUBLISH = HUMAN ACTION.

Technical upload/staging may be separately authorized without transferring Human publication authority.

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

SHOULD / MAY are recommendations or options.

Exact SHA means immutable commit identity used for review/evidence.

---

## 5. Work Item contract

Every substantial iOS task MUST have a Work Item with six explicit fields.

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

iOS Acceptance Criteria SHOULD identify relevant evidence such as:

- Swift Testing/XCTest or project-native unit/integration behavior;
- XCUITest or project-native UI/runtime behavior when applicable;
- affected scheme/configuration build result;
- retained result bundle where produced;
- Simulator behavior;
- physical-device behavior when Simulator fidelity is insufficient;
- archive/export result;
- signing/provisioning evidence;
- documentation updates;
- release-boundary checks.

Acceptance Criteria do not authorize unrelated changes.

### 5.3 Authorized Scope

Defines authorized files/modules and permitted operation boundaries.

It should identify:

- allowed repository paths;
- allowed targets/modules/packages;
- Xcode project/workspace files if included;
- schemes/configurations if included;
- entitlements/signing configuration if included;
- tests/docs if included;
- whether external systems are in scope;
- whether account/signing credentials may be used;
- whether archive/export/upload/staging is permitted.

Authorized Scope MUST NOT be interpreted as Semantic Scope expansion.

### 5.4 Relevant Sources

Defines what the Implementer should read.

Typical priority:

1. this iOS workflow;
2. repository AGENTS.md / PROGRAM.md or more specific instructions;
3. affected target/package/module docs;
4. Xcode/project build/test/signing docs relevant to the task;
5. architecture docs relevant to changed code;
6. accepted evidence explicitly cited by the Work Item;
7. fresh external official sources only if Research/Freshness Gate activates.

Issue #2 research is provenance/evidence, not a mandatory normal-operation reading set.

### 5.5 Verification

Defines required proof.

Examples:

- relevant Swift Testing/XCTest or project-native tests;
- affected scheme/configuration build;
- static analysis/lint if the project uses it;
- Simulator checks if runtime/UI semantics require them;
- physical-device checks if Simulator fidelity is insufficient;
- archive/export validation if release packaging is affected;
- signing/provisioning checks if those mechanics are affected;
- exact artifact/result references;
- CI checks;
- documentation checks.

The Work Item should specify the smallest evidence set that proves the change while respecting risk.

### 5.6 Base

Defines the exact starting branch/ref/commit.

The Implementer MUST verify the Base before editing.

Wrong Base is STOP.

macOS/Xcode, device, signing, or account capability cannot compensate for Base mismatch.

### 5.7 Work Item template

~~~markdown
## Objective

...

## Acceptance Criteria

- ...

## Authorized Scope

- Semantic Scope:
- Path Scope:
- Allowed external operations:
- Allowed signing/account operations:
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

- fix a specific crash;
- add one bounded feature;
- update one iOS workflow section;
- add a test for one behavior;
- adjust one entitlement under explicit authority.

Semantic Scope does not automatically authorize every implementation path.

### 6.2 Path Scope

Path Scope authorizes files/modules/targets.

Examples:

- Sources/...
- Tests/...
- one target/module/package;
- one Xcode project/workspace file;
- one entitlement or configuration path when authorized.

Path Scope does not authorize unrelated behavior change.

### 6.3 Required rule

Both constraints must pass independently.

PATH PERMISSION != SEMANTIC PERMISSION.

If a correct implementation requires a path outside Path Scope or a behavior outside Semantic Scope:

STOP → report → Supervisor decision.

Do not temporarily expand scope.

---

## 7. End-to-end lifecycle

Normal iOS lifecycle:

Human intent
→ Supervisor analysis
→ GitHub Work Item
→ Implementer bootstrap
→ project/Xcode context reconstruction
→ bounded implementation
→ project-native build/test
→ iOS risk classification
→ Simulator evidence when required
→ physical-device evidence when required
→ archive/export/signing evidence when required
→ evidence bundle
→ REPOSITORY_PUBLICATION
→ Implementer handoff
→ Supervisor exact-SHA review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ if accepted, integration target checks
→ MERGE_ELIGIBLE only if separately satisfied
→ merge only under separate authority
→ technical staging only if separately authorized
→ product publication only by Human action
→ CLOSED when governing conditions are complete.

A shorter path is valid only when steps are genuinely not applicable.

---

## 8. Human intent and Work Item creation

### 8.1 Human intent

Before creating the Work Item, the Supervisor should identify:

- desired product outcome;
- iOS surface affected;
- target/module/package affected;
- user impact;
- architecture impact;
- security/privacy impact;
- native Apple-runtime dependence;
- Simulator/device dependence;
- signing/provisioning impact;
- archive/export impact;
- TestFlight/App Store/enterprise impact;
- current-fact uncertainty;
- credential/account/provider/cost needs.

### 8.2 Work Item creation

The Supervisor persists:

- Objective;
- Acceptance Criteria;
- Authorized Scope;
- Relevant Sources;
- Verification;
- Base.

Prefer:

ONE OBJECTIVE → ONE BRANCH → ONE PR

unless repository governance explicitly uses another model.

### 8.3 iOS-specific planning questions

When material, determine:

- project or workspace?
- affected scheme?
- configuration?
- target/package/module?
- deployment target and SDK facts relevant to this task?
- Swift, Objective-C, mixed-language?
- SwiftUI, UIKit, mixed UI?
- test plan and destinations?
- can any logic be verified outside the native app runtime?
- does native iOS compilation require a Mac/Xcode lane?
- is Simulator evidence sufficient?
- is physical-device evidence required?
- are certificates/private keys/profiles/entitlements involved?
- is archive/export affected?
- is technical upload/staging requested?
- does App Store/TestFlight policy materially affect the task?
- is a paid Mac/device/provider required?
- does any action require Human account/publication authority?

---

## 9. Implementer start and bootstrap

The start prompt SHOULD be short and pointer-based.

Example:

~~~text
ROLE: IMPLEMENTER
REPOSITORY: owner/repo
WORK ITEM: #123
Read IOS_WORKFLOW.md and the Work Item.
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
13. PROJECT OR WORKSPACE?
14. SCHEME / CONFIGURATION?
15. TARGET / PACKAGE / MODULE?
16. MACOS/XCODE CAPABILITY REQUIRED?
17. TEST PLAN / DESTINATION KNOWN?
18. SIMULATOR EVIDENCE REQUIRED?
19. PHYSICAL-DEVICE EVIDENCE REQUIRED?
20. SIGNING/PROVISIONING INVOLVED?
21. ARCHIVE/EXPORT INVOLVED?
22. APP STORE CONNECT / TESTFLIGHT TECHNICAL ACTION INVOLVED?
23. CREDENTIAL/COST/PROVIDER ACTION REQUIRED?
24. PRODUCT PUBLICATION AUTHORIZED TO TECHNICAL ACTOR? Expected answer: NO.
25. UNRESOLVED HOLD/REWORK/ESCALATE?
26. MISMATCH CHECK: PASS | FAIL?

If any material answer is UNKNOWN and cannot be safely reconstructed:

STOP → report blocker → Supervisor.

### 9.2 Bootstrap output

~~~text
BOOTSTRAP

REPOSITORY:
ROLE:
WORK ITEM:
AUTHORITY:
BASE:
BRANCH/PR:
OBJECTIVE:
SEMANTIC SCOPE:
PATH SCOPE:
VERIFICATION:
PROJECT/WORKSPACE:
SCHEME/CONFIGURATION:
MACOS/XCODE ENVIRONMENT:
SIMULATOR EVIDENCE REQUIRED: YES | NO | UNKNOWN
PHYSICAL DEVICE REQUIRED: YES | NO | UNKNOWN
SIGNING/PROVISIONING: YES | NO
ARCHIVE/EXPORT: YES | NO
EXTERNAL ACTION REQUIRED: YES | NO
PRODUCT PUBLISH AUTHORITY FOR TECHNICAL ACTOR: NO
MISMATCH CHECK: PASS | FAIL
STATE: READY | BLOCKED
~~~

---

## 10. Reading and context policy

Use progressive disclosure.

### 10.1 Read first

1. Active Work Item.
2. This iOS workflow.
3. AGENTS.md / PROGRAM.md and more specific repository instructions.
4. Affected source/target/package/module.
5. Relevant Xcode project/workspace settings.
6. Tests adjacent to changed behavior.
7. Project docs directly relevant to the task.

### 10.2 Read only when needed

- architecture docs;
- build/test docs;
- signing/provisioning docs;
- release/distribution docs;
- accepted Issue #2 evidence;
- external official docs activated by Research/Freshness Gate.

### 10.3 Do not reconstruct history unnecessarily

Normal operation must not require reading the full Issue #2 Workpack.

Issue #2 exists as accepted provenance/evidence.

### 10.4 Avoid irrelevant context

Do not load:

- unrelated targets/packages/modules;
- old candidate comparisons;
- unrelated issue threads;
- entire repository docs by default;
- external sources not needed by the task.

Context size is not evidence quality.

---

## 11. iOS environment contract

Each iOS project should define or allow reconstruction of an environment contract.

The workflow does not freeze current versions.

### 11.1 Required environment facts

Record where materially relevant:

- project or workspace;
- scheme;
- configuration;
- target/package/module;
- supported macOS/Xcode combination;
- Apple SDK relevant to the project;
- deployment target;
- Swift/toolchain facts when relevant;
- Objective-C/mixed-language facts when relevant;
- SwiftUI/UIKit project facts when relevant;
- dependency state/manager as used by the project;
- test plan;
- test destinations;
- deterministic xcodebuild or project-native build/test commands;
- static-analysis/lint command if used;
- archive/export command or procedure if relevant;
- CI execution environment;
- Simulator capability;
- physical-device capability;
- signing/provisioning context if relevant.

### 11.2 Environment facts are project facts

Do not encode:

- latest Xcode;
- latest SDK;
- current submission requirement;
- current TestFlight rule;
- current App Store Connect rule;
- current provider image label;

as timeless Workflow constants.

When current facts matter, use the Research/Freshness Gate.

### 11.3 Portable layer vs native app boundary

Pure Swift/package/domain logic MAY be executable outside the native iOS app runtime when project dependencies support it.

That portability is useful for fast evidence but does not remove the native app boundary.

Native iOS application build, Simulator execution, archive/export, and Apple signing remain macOS/Xcode work where Apple tooling is required.

Do not claim native iOS application build capability on a non-macOS environment merely because Swift code can run there.

### 11.4 Existing project architecture

Swift, Objective-C, SwiftUI, UIKit, mixed-language, and mixed-UI choices are project facts.

Do not force migration.

A Work Item may authorize migration separately, but this workflow does not.

---

## 12. Implementation discipline

### 12.1 Minimal authorized change

Implement the smallest change that satisfies the Work Item.

Avoid:

- opportunistic refactors;
- toolchain upgrades not required by the task;
- Xcode project rewrites;
- dependency migrations;
- broad architecture migrations;
- UI-framework migrations;
- signing/provisioning changes not required by the task;
- new provider adoption not required by the task.

### 12.2 Respect project architecture

Before adding structure, identify:

- target/package/module boundaries;
- app architecture;
- state/data patterns;
- navigation approach;
- dependency injection/service patterns if any;
- test conventions;
- Xcode/build conventions.

New work should fit the current architecture unless the Work Item explicitly authorizes change.

### 12.3 Keep logic portable/testable where practical

Where project architecture permits, isolate domain/package logic from iOS runtime concerns so fast tests can prove behavior.

This does not eliminate Simulator/device evidence when iOS runtime semantics matter.

### 12.4 Never hide required runtime behavior behind portable success

PURE SWIFT OR PACKAGE PORTABILITY != NATIVE IOS APPLICATION BUILD CAPABILITY.

A non-native or host-level test cannot prove behavior that depends on:

- app lifecycle;
- UIKit/SwiftUI runtime integration;
- iOS permissions;
- hardware;
- device services;
- signing/runtime entitlements;
- actual device behavior.

---

## 13. Problems discovered during work

Classify discovered problems.

### 13.1 Related and inside scope

If the issue:

- is directly caused by the authorized change;
- is inside Semantic Scope;
- is inside Path Scope;
- can be fixed without authority expansion;

the Implementer MAY fix it and report it.

### 13.2 Related but outside scope

If correction requires:

- a new path/target/package;
- expanded behavior;
- architecture change;
- toolchain change;
- new dependency/provider;
- entitlement/signing change;
- credential/account action;
- material cost;

STOP and request Supervisor decision.

### 13.3 Unrelated defect

Do not fix opportunistically.

Persist/report enough evidence for later triage.

### 13.4 Security, signing, or publication concern

If work reveals:

- exposed certificate/private key;
- unsafe keychain/export practice;
- incorrect provisioning access;
- unauthorized App Store Connect role use;
- unintended product distribution;
- production-state mutation;

STOP immediately and escalate.

---

## 14. iOS verification model

Verification is risk-tiered.

The Work Item defines the required minimum.

### 14.1 Base project-native verification

For ordinary implementation checkpoints, use the project-native minimum that proves the change.

Typical evidence may include:

1. Swift Testing and/or XCTest or equivalent relevant tests;
2. affected scheme/configuration build or test;
3. project-native static analysis/lint when configured;
4. retained result evidence such as xcresult when produced.

Illustrative command shape:

~~~text
xcodebuild \
  -project <project> OR -workspace <workspace> \
  -scheme <scheme> \
  -configuration <configuration> \
  -destination <destination> \
  test
~~~

or a project-provided wrapper/automation command.

Do not assume one command, scheme, destination, or configuration for all projects.

### 14.2 XCUITest/UI automation

Use XCUITest or project-native UI/runtime automation when the project uses it and the Work Item requires UI/system interaction evidence.

UI automation remains evidence, not semantic approval.

### 14.3 Simulator evidence risk classifier

Simulator evidence is required when the change materially affects:

- SwiftUI/UIKit runtime behavior;
- app lifecycle;
- scene/navigation behavior;
- permissions/OS dialogs;
- notifications/background behavior;
- local persistence behavior tied to iOS runtime;
- deep links/universal links where relevant;
- UI layout/interaction;
- accessibility semantics;
- device-orientation behavior;
- OS-version compatibility;
- release-critical user journey.

### 14.4 Physical-device trigger

Physical-device evidence is required or strongly indicated when Simulator fidelity is insufficient, including:

- camera;
- microphone/audio route;
- Bluetooth;
- sensors;
- secure hardware/keychain behavior when relevant;
- push/environment behavior that requires real device;
- performance/thermal/battery behavior;
- hardware-dependent frameworks;
- device-only entitlement behavior;
- vendor/device-specific behavior;
- release-critical physical-device journey.

SIMULATOR CAPABILITY != PHYSICAL-DEVICE CAPABILITY.

### 14.5 Physical-device evidence is not mandatory for every change

Do not run a broad device matrix by default.

Select the smallest matrix justified by risk.

Broader matrices MAY run:

- pre-release;
- nightly;
- in dedicated compatibility validation;
- through an authorized device service.

This must be an explicit project rule.

### 14.6 Archive/export verification

If the change affects:

- release configuration;
- bundle metadata;
- entitlements;
- capabilities;
- signing;
- packaging;
- export options;
- distribution artifact construction;

the Work Item should require appropriate archive/export evidence.

Archive/export success remains technical evidence only.

### 14.7 Accessibility and UX

For material iOS UI changes:

- run applicable automated accessibility checks when available;
- validate VoiceOver-relevant labels/traits/focus behavior when material;
- verify Dynamic Type/layout behavior where required;
- require Human/design/accessibility review when qualitative judgment is needed.

Automation is evidence, not complete UX approval.

---

## 15. Provider-neutral Mac/Simulator/device evidence adapter

This adapter represents a capability boundary, not a mandatory provider.

### 15.1 Allowed implementations

Depending on project and authority:

- local developer Mac;
- self-hosted Mac runner;
- GitHub-hosted macOS runner;
- Xcode Cloud;
- another authorized macOS CI provider;
- local Simulator;
- authorized remote Simulator capability;
- attached physical Apple device;
- authorized physical-device service.

No one provider is mandatory.

Apple-required tooling is not treated as avoidable provider lock-in.

### 15.2 Required adapter inputs

When platform evidence is required, record:

- governing Work Item;
- exact repository SHA;
- app/test/archive artifact identity;
- artifact hash when applicable;
- project/workspace;
- scheme;
- configuration;
- macOS/Xcode/toolchain;
- SDK/deployment-target facts relevant to the run;
- test plan;
- destination;
- Simulator/device model and OS when relevant;
- physical-device requirement when relevant;
- test selection;
- retry/flaky policy;
- timeout;
- expected result;
- signing context if applicable.

### 15.3 Required adapter outputs

Return as applicable:

- pass/fail/skip;
- macOS/Xcode environment;
- destination/device metadata;
- run ID;
- xcresult or equivalent result reference;
- logs/reports;
- screenshots/traces only when required and permitted;
- artifact/archive/export references;
- retry history;
- deviations;
- unresolved warnings.

### 15.4 Adapter boundary

A provider result cannot issue:

- SEMANTIC_ACCEPTED;
- MERGE_ELIGIBLE;
- merge;
- product publication.

Mac/device evidence remains evidence.

---

## 16. CI, evidence, and checkpoint discipline

### 16.1 CI goals

CI should provide reproducible evidence bound to exact SHA.

Typical iOS CI may include:

- dependency/setup;
- project-native tests;
- affected build;
- static analysis/lint if configured;
- Simulator tests when required;
- physical-device job when required and available;
- result bundle retention;
- archive/export validation when authorized;
- artifact collection.

### 16.2 CI exactness

Evidence must identify:

- commit SHA;
- workflow/job;
- macOS/Xcode environment;
- project/workspace/scheme/configuration;
- destination where relevant;
- pass/fail state;
- artifact/result/run references.

### 16.3 CI failure

If required CI fails:

- do not ignore it;
- determine whether the failure is caused by the change;
- fix within scope or report blocker;
- rerun only under allowed workflow operations.

### 16.4 CI absence

If CI is NOT CONFIGURED:

- do not claim CI PASS;
- run required project-native verification in an authorized environment;
- report CI: NOT CONFIGURED.

### 16.5 Checkpoints

Persist a checkpoint when:

- switching phase;
- context may be lost;
- external actor is invoked;
- material research changes rationale;
- long-running Mac/device verification crosses a boundary;
- signing/archive/export work begins;
- Supervisor needs an intermediate decision.

A checkpoint should include exact SHA and state.

---

## 17. Repository publication procedure

This section corresponds to the inherited baseline repository-publication function.

REPOSITORY_PUBLICATION is not product publication.

### 17.1 Before commit

The Implementer MUST:

- review all changed paths;
- confirm Semantic Scope;
- confirm Path Scope;
- confirm no unintended project/workspace/signing files changed;
- run required verification;
- confirm secrets/certificates/private keys are not introduced;
- confirm no baseline/reference violation.

### 17.2 Commit

Use a focused commit.

The commit should:

- describe the bounded change;
- avoid unrelated edits;
- preserve traceability.

### 17.3 Push / branch

Push only to the authorized branch.

Wrong target is STOP.

### 17.4 Pull request

Open/update the authorized PR.

The PR should identify:

- Work Item;
- purpose;
- exact scope;
- verification;
- environment assumptions;
- known risks;
- evaluation/merge status.

Opening a PR does not create semantic acceptance or merge eligibility.

---

## 18. Implementer handoff

After implementation and verification, publish a compact durable handoff.

Required fields:

~~~text
IOS_IMPLEMENTER_HANDOFF

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

PROJECT/WORKSPACE:
SCHEME:
CONFIGURATION:

VERIFICATION:
- command/check:
- destination:
- result:

MACOS/XCODE ENVIRONMENT:
- relevant facts:

SIMULATOR EVIDENCE:
REQUIRED: YES | NO
DESTINATION:
RUN/RESULT REF:
RESULT:

PHYSICAL DEVICE EVIDENCE:
REQUIRED: YES | NO
DEVICE/OS:
RUN/RESULT REF:
RESULT:

SIGNING/PROVISIONING:
INVOLVED: YES | NO
SAFE EVIDENCE REF:

ARCHIVE/EXPORT:
REQUIRED: YES | NO
ARTIFACT/ARCHIVE REF:
RESULT:

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
- never include private key material, secrets, or sensitive credential values;
- stop after handoff unless later authority authorizes more work.

---

## 19. Supervisor exact-SHA review

The Supervisor independently checks the exact PR HEAD.

### 19.1 Required review inputs

- governing Work Item;
- exact HEAD;
- branch/PR;
- diff;
- changed files;
- architecture compatibility;
- Acceptance Criteria;
- project/workspace/scheme/configuration;
- verification evidence;
- CI;
- Simulator evidence when required;
- physical-device evidence when required;
- signing/provisioning evidence when relevant;
- archive/export evidence when relevant;
- documentation;
- external-actor records when used;
- unresolved warnings.

### 19.2 Review questions

1. Does implementation satisfy Objective?
2. Does each Acceptance Criterion pass?
3. Did Implementer stay inside Semantic Scope?
4. Did Implementer stay inside Path Scope?
5. Are project/workspace/scheme/configuration facts sufficient?
6. Is macOS/Xcode evidence appropriate?
7. Was Simulator evidence required and sufficient?
8. Was physical-device evidence required and sufficient?
9. Is Simulator success being incorrectly treated as physical-device proof?
10. Are signing/provisioning boundaries respected?
11. Are certificate/private-key/account-role secrets protected?
12. Are archive/export/upload operations inside explicit authority?
13. Did any technical capability become implicit Workflow authority?
14. Is product publication still Human-only?
15. Does exact reviewed SHA match PR HEAD?
16. Are CI/test results evidence rather than approval?
17. Is any HARD VETO present?
18. Are unresolved findings acceptable or do they require REWORK/HOLD/ESCALATE?

### 19.3 New commit after review

If HEAD changes after review, the prior semantic decision does not automatically apply to the new SHA.

A new exact-SHA review is required.

---

## 20. Formal Supervisor decisions

Only four semantic decisions exist.

### 20.1 SEMANTIC_ACCEPTED

Meaning:

- exact reviewed SHA satisfies Work Item intent and Acceptance Criteria;
- no material semantic defect remains for that exact SHA.

It does NOT mean:

- MERGE_ELIGIBLE automatically;
- merged;
- canonical;
- TestFlight published;
- App Store published;
- enterprise published.

### 20.2 REWORK

Meaning:

- correction is required;
- objective generally remains valid;
- same Work Item/branch/PR normally continues.

REWORK must identify:

- reviewed SHA;
- defect;
- required result;
- scope;
- evidence required.

### 20.3 HOLD

Meaning:

- objective cannot currently progress because a blocker is unresolved.

Examples:

- required Mac/Xcode capability unavailable;
- required Simulator/device capability unavailable;
- required signing credential unavailable;
- provisioning/account role unavailable;
- external dependency prevents proof;
- Human decision pending.

HOLD is not failure by default.

### 20.4 ESCALATE

Meaning:

- Human/material decision is required.

Examples:

- objective/scope change;
- architecture decision;
- paid Mac/device provider commitment;
- signing/provisioning/account policy decision;
- distribution strategy decision;
- product publication decision;
- material risk trade-off.

---

## 21. REWORK continuity

### 21.1 Same objective

When Objective and authorized contract remain valid:

- continue in same Issue;
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
- new signing/account/provider authority;
- new paid-service commitment;
- changed publication authority;

STOP → Supervisor/Human decision.

Do not disguise scope expansion as REWORK.

---

## 22. Current-decision rule

The current valid semantic decision is:

the latest Supervisor decision explicitly associated with the current exact HEAD.

Do not use:

- an older decision for another SHA;
- a handoff as a decision;
- CI status as a decision;
- external actor result as a decision;
- signing/archive/upload success as a decision.

If current HEAD has no applicable decision:

state is not semantically accepted.

---

## 23. Integration and merge eligibility

After SEMANTIC_ACCEPTED, integration still requires separate checks.

Typical sequence:

READY_FOR_REVIEW
→ SEMANTIC_ACCEPTED
→ verify target branch/base state
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
- CI required checks pass;
- required approvals exist;
- no blocking HOLD/ESCALATE;
- no merge conflict or target divergence invalidates review assumptions;
- repository rules allow merge;
- merge authority is present.

SEMANTIC_ACCEPTED != MERGE_ELIGIBLE.

---

## 24. Merge boundary

The Implementer MUST NOT self-merge.

An external actor MUST NOT gain merge authority from technical capability.

Where governing Workflow authorizes Supervisor merge, the Supervisor may merge only after:

- exact-SHA semantic acceptance;
- merge-eligibility checks;
- target state verification.

If merge authority is not demonstrable:

STOP.

---

## 25. Product publication boundary

Product publication is distinct from repository publication.

PUBLISH = HUMAN ACTION.

### 25.1 iOS technical pre-publication work

When explicitly authorized, technical work MAY include:

- validating release configuration;
- building an archive;
- validating export;
- validating entitlements/provisioning;
- signing-support operations;
- generating export artifacts;
- technical App Store Connect upload/staging;
- retaining archive/export/signing evidence;
- checking current Apple SDK/submission/account requirements through Research/Freshness Gate.

### 25.2 What technical actors cannot infer

The following do not grant product publication authority:

- certificate/private-key access;
- provisioning-profile access;
- App Store Connect role;
- App Store Connect API access;
- upload capability;
- archive/export success;
- signed artifact availability;
- TestFlight technical access;
- CI release credentials;
- Work Item technical permission;
- external-actor capability.

### 25.3 Signing and provisioning boundary

Signing materials are controlled assets.

Ordinary implementation/test contexts should not hold production distribution private keys unless explicitly required.

If signing is required:

- use least privilege;
- identify team/bundle/artifact context;
- identify certificate/profile/entitlement context without exposing secret values;
- do not log private keys, passwords, tokens, or sensitive credential material;
- persist only safe evidence;
- stop if credential handling exceeds authority.

Automatic signing or tool-managed provisioning is still technical capability, not Workflow authority.

### 25.4 Archive/export boundary

Archive/export may be authorized as technical evidence.

Record:

- exact SHA;
- project/workspace;
- scheme/configuration;
- archive identity;
- export method/configuration;
- signing/provisioning context;
- result;
- artifact reference/hash where applicable.

Archive/export success does not authorize product publication.

### 25.5 TestFlight / App Store / other distribution

Technical upload/staging MAY be authorized separately.

Actual product publication remains Human action.

This includes any externally observable beta/release publication state that the governing product process treats as publication.

If the distinction between technical staging and publication is unclear:

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
- last evidence/checkpoint;
- project/workspace;
- scheme/configuration;
- macOS/Xcode environment;
- Simulator/device evidence state;
- signing/provisioning state;
- archive/export state;
- external-actor activity state;
- unresolved REWORK/HOLD/ESCALATE;
- next authorized action.

### 26.2 Recovery rule

If current HEAD differs from SHA named in latest semantic decision:

do not assume acceptance.

### 26.3 Recovery template

~~~text
IOS_IMPLEMENTER_RECOVERY

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
PROJECT/WORKSPACE:
SCHEME/CONFIGURATION:
MACOS/XCODE ENVIRONMENT:
SIMULATOR EVIDENCE STATE:
PHYSICAL DEVICE EVIDENCE STATE:
SIGNING/PROVISIONING STATE:
ARCHIVE/EXPORT STATE:
LATEST SUPERVISOR DECISION:
REVIEWED SHA:
EXTERNAL ACTIVITY:
BLOCKER / REWORK:
NEXT AUTHORIZED ACTION:
MISMATCH CHECK: PASS | FAIL
~~~

---

## 27. Supervisor session recovery

A fresh Supervisor also reconstructs from GitHub, not prior chat.

### 27.1 Minimum Supervisor recovery set

- Human intent/current governing Issue;
- active Work Item;
- exact PR HEAD;
- target branch;
- Work Item contract;
- relevant repository instructions;
- latest Implementer handoff;
- verification evidence;
- CI;
- project/workspace/scheme/configuration;
- macOS/Xcode facts;
- Simulator/device evidence when required;
- signing/provisioning evidence when relevant;
- archive/export evidence when relevant;
- external-actor records;
- latest Supervisor decision/reviewed SHA;
- unresolved blocker/REWORK/HOLD/ESCALATE.

### 27.2 Supervisor mismatch rule

If repository, Work Item, actor, authority, target, or SHA mismatches:

STOP.

Do not reinterpret another project's task into the current one.

---

## 28. Human role

The Human is not merely an emergency fallback.

The Human owns decisions that require human product/account authority.

Typical Human-only or Human-reserved actions:

- credentials/MFA;
- Apple account/security confirmation;
- material scope/product change;
- architecture/Workflow adoption where required;
- paid provider commitment;
- App Store Connect role decisions when reserved;
- distribution/publication decisions;
- PUBLISH / product publication.

The workflow should automate permitted technical work while minimizing Human interruption.

Do not ask Human to perform routine mechanical work that an authorized technical actor can safely perform.

---

## 29. Research/Freshness Gate + Strategic Rationale

Issue #2 research is the accepted evidence library.

Do not repeat broad research by default.

### 29.1 When Research/Freshness Gate activates

Activate when a material decision depends on a current external fact, such as:

- Xcode/macOS compatibility;
- current Apple SDK/submission requirement;
- current deployment/submission minimum;
- current TestFlight behavior/policy;
- current App Store Connect requirement;
- current signing/provisioning rule;
- current provider image/capability;
- current device-service capability;
- provider pricing/quota when cost authority matters;
- security guidance materially affecting implementation;
- deprecation/removal changing feasible architecture.

Do not activate for curiosity.

### 29.2 Research behavior

When activated:

- prefer official/primary Apple or provider sources;
- record date/version scope;
- distinguish fact from inference;
- avoid timeless wording for volatile facts;
- cite evidence in Work Item or rationale;
- stop if research reveals architecture/authority change requiring decision.

### 29.3 Evidence categories

Label material statements as appropriate:

- PROJECT FACT
- EXTERNAL VERIFIED FACT
- EMPIRICAL OBSERVATION
- INFERENCE
- RECOMMENDATION
- UNKNOWN

### 29.4 Supervisor verification

Supervisor reviews whether:

- research was actually required;
- sources are appropriate;
- conclusions follow from evidence;
- authority remains unchanged.

### 29.5 Strategic Rationale

Persist a STRATEGIC_RATIONALE when a material technical choice affects architecture, risk, provider use, verification, signing, distribution, or maintainability.

Template:

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

- macOS/Xcode build/test;
- Simulator run;
- physical-device matrix;
- signing-support operation;
- archive/export technical operation;
- bounded App Store Connect technical staging operation.

### 30.3 Preconditions

Include:

- governing Work Item;
- exact ref/SHA;
- artifact/archive hashes where applicable;
- macOS/Xcode environment;
- project/workspace/scheme/configuration;
- destination/device matrix;
- Apple/team/account role availability if required;
- credential authority;
- cost/quota authority;
- signing/provisioning context if applicable.

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
- unauthorized account-role change;
- unauthorized signing credential change;
- new paid-service/provider commitment;
- unauthorized retry/workaround after STOP.

### 30.6 Expected baseline / SHA gate

Activity must bind to:

- Work Item;
- exact SHA/ref;
- artifact/archive hash where applicable;
- toolchain/environment;
- project/workspace/scheme/configuration;
- requested test/device/signing/export matrix.

If baseline changes:

STOP or obtain renewed authority.

### 30.7 Evidence returned

Return only evidence required by activity:

- run ID;
- environment/destination/device metadata;
- pass/fail/skip;
- result bundle/log/report reference;
- archive/export/artifact reference;
- signing/provisioning safe evidence;
- retry/deviation history;
- unresolved warnings.

### 30.8 STOP conditions

STOP when:

- input SHA differs;
- required Mac/Xcode/device capability is missing;
- required credential/account/cost permission is missing;
- signing/provisioning context differs materially;
- operation exceeds scope;
- Objective/Acceptance Criteria/scope would need to change;
- evidence is invalid/incomplete;
- environment/provider behavior creates material contradiction;
- publication would be required;
- retry could create unsafe or duplicate external effects.

### 30.9 Escalation

Return:

- exact blocker;
- evidence;
- requested decision;
- no unauthorized workaround.

### 30.10 Durable result and closure

Persist RESULT and STATUS.

Provider-only or chat-only trace is insufficient.

### 30.11 Bounded external platform mutation

If external Apple/provider state must be changed, require:

- exact target;
- exact authorized scope;
- observable baseline;
- before/after evidence;
- rollback when applicable;
- STOP conditions;
- no code/merge/publication authority implied.

Examples may include bounded non-publication provisioning/device/provider configuration under explicit authority.

### 30.12 Historical AI Studio Issue #53 compatibility rule

The frozen baseline contains a specific historical compatibility rule for an earlier Issue #53 / AI Studio quota state.

That historical state is NOT a reusable iOS operational rule.

It is intentionally not imported into normative iOS operation.

Its reusable safety functions are preserved through:

- HOLD;
- current-decision rule;
- external-actor gate;
- recovery;
- PUBLISH = HUMAN ACTION;
- TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

This is the only baseline area classified NOT_APPLICABLE_WITH_JUSTIFICATION by the accepted iOS adaptation matrix.

---

## 31. Technical permission != Workflow authority

Exact invariant:

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

### 31.1 Repository/product-code writes

An actor may write repository/product code only when governing Work Item authorizes:

- semantic change;
- path;
- operation.

A tool's ability to edit a file does not authorize the edit.

### 31.2 External actor escalation

Escalating a task to an external actor does not transfer:

- Supervisor authority;
- Human authority;
- semantic-decision authority;
- merge authority;
- publication authority.

### 31.3 Signing/account credentials

Possession of:

- certificate;
- private key;
- provisioning profile;
- App Store Connect role;
- API key;
- upload credential;
- cloud token;

does not imply permission to exercise every technical capability available.

### 31.4 Cost

Technical access to a paid Mac/device/provider does not authorize cost.

Material provider cost requires governing permission.

---

## 32. iOS-specific platform deltas

iOS remains iOS-specific.

Do not force cross-platform symmetry.

### 32.1 Primary native build boundary

Native iOS app build is macOS/Xcode-bound where Apple SDK/tooling is required.

The project may contain portable Swift/package/domain components, but that does not remove native app build constraints.

### 32.2 Project/workspace/scheme/configuration

iOS build/test evidence must identify the relevant:

- project or workspace;
- scheme;
- configuration;
- target/package/module;
- destination where applicable.

Do not assume a universal project shape.

### 32.3 Language/UI stack

Swift, Objective-C, SwiftUI, UIKit, or combinations are project facts.

No forced migration is introduced.

### 32.4 Testing stack

Use project-native testing:

- Swift Testing where applicable;
- XCTest where applicable;
- XCUITest where applicable;
- project wrappers/tools where configured.

No testing framework becomes mandatory merely for symmetry.

### 32.5 Simulator vs physical device

Simulator is useful for many runtime/UI checks.

Simulator is not equivalent to physical device for every behavior.

SIMULATOR CAPABILITY != PHYSICAL-DEVICE CAPABILITY.

### 32.6 Signing and provisioning

Apple certificates/private keys, profiles, entitlements, teams, bundle identity, and account roles are real platform constraints.

They are technical capabilities/assets, not authority sources.

### 32.7 Archive/export

Archive/export is a distinct technical boundary.

Evidence may include:

- archive identity;
- export result;
- artifact reference;
- signing context.

Archive/export success does not authorize publication.

### 32.8 Distribution

Possible channels may include:

- TestFlight;
- App Store;
- enterprise/internal distribution;
- other project-authorized channels.

The workflow does not make one channel mandatory.

### 32.9 Provider neutrality ceiling

Provider neutrality is high in task/governance orchestration but lower at Apple-required native build/signing/distribution boundaries.

Possible Mac providers remain optional.

Xcode Cloud is optional, not mandatory.

### 32.10 Accessibility/UX boundary

iOS accessibility/device UX remains platform-specific.

Use project-appropriate checks and Human judgment where qualitative validation is required.

### 32.11 Volatile Apple facts

Current Xcode, SDK, App Store submission, TestFlight, provider, account, or policy facts belong behind Research/Freshness Gate.

Do not freeze them as timeless workflow semantics.

---

## 33. Operational Definition of Done

An iOS Work Item governed by this workflow is ready for Supervisor review only when applicable checks are complete.

The iOS workflow itself is operationally complete only if all tests in section 34 pass.

### 33.1 Work Item implementation DoD

For a normal Work Item:

- repository/Work Item/role/authority/Base match;
- Objective addressed;
- Acceptance Criteria evidenced;
- Semantic Scope respected;
- Path Scope respected;
- project/workspace/scheme/configuration facts sufficient;
- macOS/Xcode environment facts sufficient;
- implementation bounded;
- discovered issues handled correctly;
- required build/test verification complete;
- required Simulator evidence complete;
- required physical-device evidence complete;
- required archive/export evidence complete;
- required signing/provisioning evidence complete;
- required CI state reported;
- secrets/credentials handled safely;
- external actor record complete if used;
- full diff reviewed;
- REPOSITORY_PUBLICATION correct;
- exact HEAD identified;
- handoff persisted;
- no self-approval;
- no product publication by technical actor.

---

## 34. Acceptance tests for this workflow

These tests validate document architecture and operational completeness.

### TEST A — Baseline coverage

Procedure:

1. Read accepted iOS Baseline Adaptation Matrix.
2. Verify all 71 classified rows have an implemented target in this document.
3. Verify all six Work Item child fields are explicit.
4. Verify only baseline 29.12 is NOT_APPLICABLE_WITH_JUSTIFICATION.
5. Verify no normative row is silently grouped away.

Expected result:

PASS.

Failure is HARD VETO.

### TEST B — Happy path

Representative scenario:

1. Human states bounded iOS intent.
2. Supervisor creates six-field Work Item.
3. Implementer bootstraps and verifies Base/scope.
4. Implementer changes authorized iOS code.
5. Relevant project-native tests/build pass.
6. Risk classifier says Simulator evidence is required and physical-device evidence is not.
7. Required Simulator evidence passes.
8. Implementer publishes commit/PR.
9. Implementer handoff names exact SHA.
10. Supervisor independently reviews exact SHA.
11. Supervisor issues SEMANTIC_ACCEPTED.
12. Integration checks separately establish MERGE_ELIGIBLE.
13. Authorized merge occurs.
14. Product publication, if any, remains Human action.

Expected result:

Lifecycle can be executed from this document without reading Issue #2.

### TEST C — REWORK exact-SHA invalidation

Scenario:

1. Supervisor reviews SHA A.
2. Supervisor issues REWORK.
3. Implementer fixes same objective in same Issue/branch/PR.
4. New HEAD is SHA B.
5. Prior review of SHA A does not apply to SHA B.
6. Verification reruns as required.
7. New handoff names SHA B.
8. Supervisor reviews SHA B.

Expected result:

No acceptance automatically carries across SHA change.

### TEST D — Authority adversarial

Cases:

1. Implementer has App Store Connect access.
   Expected: cannot product-publish.

2. Implementer has signing certificate/private key.
   Expected: cannot infer permission to sign/distribute outside Work Item.

3. External actor can upload a build.
   Expected: cannot product-publish or self-approve.

4. CI is green.
   Expected: CI cannot issue SEMANTIC_ACCEPTED.

5. Implementer can edit authorized project path.
   Expected: cannot make unrelated semantic change.

6. Archive/export succeeds.
   Expected: cannot imply publication authority.

7. Supervisor issued SEMANTIC_ACCEPTED.
   Expected: merge eligibility still checked separately.

All cases must resolve safely.

### TEST E — STOP / escalation

Cases:

- wrong repository;
- wrong Work Item;
- wrong Base;
- wrong PR target;
- missing Path Scope;
- implementation requires architecture change;
- required Mac/Xcode unavailable;
- required physical device unavailable;
- required signing credential unavailable;
- App Store Connect role insufficient;
- paid Mac/device provider required but cost not authorized;
- current Apple policy is material but unknown;
- external actor baseline does not match;
- publication would require technical actor to exceed authority.

Expected result:

STOP / HOLD / ESCALATE as appropriate.
No inference.

### TEST F — Session recovery

Fresh Implementer reconstructs:

- Issue;
- branch/ref;
- HEAD;
- PR;
- scope;
- evidence;
- latest decision;
- project/workspace/scheme/configuration;
- macOS/Xcode;
- Simulator/device state;
- signing/archive state;
- next action.

Fresh Supervisor reconstructs same durable state for review.

Expected result:

No prior chat transcript required.

### TEST G — External actor durability

Create a representative Mac/device activity.

Verify GitHub records:

request
→ authority
→ execution
→ evidence
→ result
→ stop/escalation.

Expected result:

A future authorized session can reconstruct exactly what happened and why.

### TEST H — iOS platform delta

Cases:

1. Swift package/domain tests pass on a portable environment.
   Expected: do not claim native iOS application build proof.

2. Native build requires macOS/Xcode.
   Expected: route through authorized Mac/Xcode capability.

3. Simulator tests pass but physical hardware behavior is material.
   Expected: obtain justified physical-device evidence or report blocker.

4. One Mac/device provider is unavailable.
   Expected: workflow remains valid if another authorized capability exists; provider is not canonical.

5. Archive/export/sign/upload succeeds.
   Expected: product publication remains Human-only.

6. Existing Objective-C/UIKit application.
   Expected: no forced Swift/SwiftUI migration.

### TEST I — Standalone use

Remove Issue #2 research artifacts from normal execution scenario.

Provide only:

- repository;
- active Work Item;
- this document;
- project docs explicitly referenced by Work Item.

Expected result:

Implementer and Supervisor can run normal lifecycle.

Issue #2 remains provenance, not procedure dependency.

### TEST J — Summary regression

Create a short summary/checklist from this workflow.

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
- Simulator/device capability boundary;
- signing/archive/publication boundary;
- external-actor durability.

If any invariant disappears or weakens:

REWORK / HARD VETO.

---

## 35. Execution templates and checklists

### 35.1 Supervisor Work Item checklist

~~~text
IOS WORK ITEM CREATION

HUMAN INTENT:
OBJECTIVE:
ACCEPTANCE CRITERIA:
AUTHORIZED SEMANTIC SCOPE:
AUTHORIZED PATH SCOPE:
ALLOWED EXTERNAL OPERATIONS:
ALLOWED SIGNING/ACCOUNT OPERATIONS:
FORBIDDEN OPERATIONS:
RELEVANT SOURCES:
PROJECT/WORKSPACE:
SCHEME:
CONFIGURATION:
MACOS/XCODE FACTS:
VERIFICATION:
SIMULATOR TRIGGER:
PHYSICAL DEVICE TRIGGER:
ARCHIVE/EXPORT TRIGGER:
SIGNING/PROVISIONING TRIGGER:
CI REQUIREMENT:
CREDENTIAL/COST REQUIREMENT:
BASE:
BRANCH/PR MODEL:
STOP CONDITIONS:
~~~

### 35.2 Implementer bootstrap checklist

~~~text
IOS IMPLEMENTER BOOTSTRAP

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
PROJECT/WORKSPACE KNOWN: YES | NO
SCHEME/CONFIGURATION KNOWN: YES | NO
MACOS/XCODE CAPABILITY SUFFICIENT: YES | NO | UNKNOWN
SIMULATOR EVIDENCE REQUIRED: YES | NO | UNKNOWN
PHYSICAL DEVICE REQUIRED: YES | NO | UNKNOWN
SIGNING/PROVISIONING INVOLVED: YES | NO
ARCHIVE/EXPORT INVOLVED: YES | NO
CREDENTIAL/COST ACTION REQUIRED: YES | NO
PRODUCT PUBLISH AUTHORITY FOR TECHNICAL ACTOR: NO
MISMATCH CHECK: PASS | FAIL
STATE: READY | BLOCKED
~~~

### 35.3 iOS environment contract template

~~~text
IOS ENVIRONMENT CONTRACT

PROJECT OR WORKSPACE:
TARGET/PACKAGE/MODULE:
SCHEME:
CONFIGURATION:
MACOS:
XCODE:
APPLE SDK:
DEPLOYMENT TARGET:
SWIFT/TOOLCHAIN:
LANGUAGE MIX:
UI STACK:
DEPENDENCIES:
TEST PLAN:
TEST DESTINATIONS:
BASE TEST COMMAND:
BUILD COMMAND:
STATIC ANALYSIS/LINT COMMAND:
SIMULATOR COMMAND:
PHYSICAL DEVICE COMMAND:
ARCHIVE COMMAND:
EXPORT PROCEDURE:
CI ENVIRONMENT:
NOTES / UNKNOWN:
~~~

Unknown values are allowed if not material.
Do not invent them.

### 35.4 iOS risk classifier template

~~~text
IOS RISK CLASSIFIER

CHANGE AFFECTS:
[ ] pure portable/package/domain logic only
[ ] native iOS build
[ ] SwiftUI/UIKit runtime behavior
[ ] app lifecycle
[ ] permissions/OS integration
[ ] persistence/runtime semantics
[ ] hardware/device services
[ ] accessibility/device UX
[ ] OS/device compatibility
[ ] release-critical journey
[ ] entitlement/capability
[ ] signing/provisioning
[ ] archive/export
[ ] current TestFlight/App Store policy

PORTABLE/HOST EVIDENCE SUFFICIENT:
YES | NO

SIMULATOR EVIDENCE REQUIRED:
YES | NO

PHYSICAL DEVICE REQUIRED:
YES | NO

ARCHIVE/EXPORT EVIDENCE REQUIRED:
YES | NO

SIGNING/PROVISIONING EVIDENCE REQUIRED:
YES | NO

RATIONALE:
...
~~~

### 35.5 Mac/Simulator/device evidence template

~~~text
IOS PLATFORM EVIDENCE

WORK ITEM:
SHA:
PROJECT/WORKSPACE:
SCHEME:
CONFIGURATION:
MACOS/XCODE:
ARTIFACT/ARCHIVE:
ARTIFACT HASH:
ADAPTER:
RUN ID:
DESTINATION:
DEVICE/OS:
TEST PLAN/SELECTION:
RETRY POLICY:
RESULT:
XCRESULT/REPORT REF:
RETRIES/DEVIATIONS:
UNRESOLVED WARNING:
~~~

### 35.6 Signing/provisioning evidence template

~~~text
IOS SIGNING / PROVISIONING EVIDENCE

WORK ITEM:
SHA:
TEAM/BUNDLE CONTEXT:
CERTIFICATE CONTEXT:
PROVISIONING CONTEXT:
ENTITLEMENTS:
AUTHORIZED OPERATION:
ARTIFACT/ARCHIVE:
RESULT:
SAFE EVIDENCE REF:
SECRET MATERIAL INCLUDED IN REPORT: NO
PUBLICATION AUTHORITY TRANSFERRED: NO
~~~

### 35.7 Archive/export evidence template

~~~text
IOS ARCHIVE / EXPORT EVIDENCE

WORK ITEM:
SHA:
PROJECT/WORKSPACE:
SCHEME:
CONFIGURATION:
ARCHIVE REF:
EXPORT METHOD:
ARTIFACT REF:
ARTIFACT HASH:
SIGNING CONTEXT:
RESULT:
UPLOAD/STAGING AUTHORIZED: YES | NO
PRODUCT PUBLICATION AUTHORIZED TO TECHNICAL ACTOR: NO
~~~

### 35.8 Implementer handoff template

Use section 18.

### 35.9 Supervisor review template

~~~text
IOS_SUPERVISOR_REVIEW

WORK ITEM:
PR:
REVIEWED SHA:
BASE:
DIFF/SCOPE: PASS | FAIL
ACCEPTANCE CRITERIA: PASS | FAIL
PROJECT/WORKSPACE/SCHEME: SUFFICIENT | INSUFFICIENT
BUILD/TEST: PASS | FAIL | N/A
SIMULATOR EVIDENCE: PASS | FAIL | N/A
PHYSICAL DEVICE EVIDENCE: PASS | FAIL | N/A
SIGNING/PROVISIONING: PASS | FAIL | N/A
ARCHIVE/EXPORT: PASS | FAIL | N/A
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
IOS_REWORK

WORK ITEM:
REVIEWED SHA:
PROBLEM:
REQUIRED RESULT:
SCOPE:
SEMANTIC SCOPE CHANGED: NO | YES -> ESCALATE
PATH SCOPE CHANGED: NO | YES -> AUTHORITY REQUIRED
SIGNING/ACCOUNT AUTHORITY CHANGED: NO | YES -> AUTHORITY REQUIRED
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

The document preserves the functional baseline and applies iOS adaptations justified by accepted evidence.

### 36.2 Maintenance rule

When this workflow changes:

1. identify governing Work Item;
2. state whether change is PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION relative to accepted architecture;
3. verify baseline functions remain covered;
4. verify iOS platform deltas remain valid;
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

may silently replace this document as normative iOS workflow.

A summary MAY point to this document.

A summary MUST NOT weaken it.

### 36.4 Architecture changes

If maintaining iOS requires changing:

- Workflow Document Contract;
- baseline adaptation classifications;
- ADR decision;
- role authority model;
- state vocabulary;
- publication boundary;

STOP platform work and return to architecture authority.

Do not patch architecture defects only inside iOS.

### 36.5 Current facts

Do not hardcode volatile platform facts into Workflow semantics.

Keep current versions/policies in:

- project configuration;
- Work Item;
- evidence;
- Strategic Rationale;
- release checklist;

as appropriate.

---

# Appendix A — Baseline implementation trace

This appendix demonstrates implementation of the accepted iOS Baseline Adaptation Matrix.

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
| 5. GitHub | PRESERVE | §3.4 |
| 6. Documentación del proyecto | ADAPT | §10 |
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
| 27. Rol del humano | EXTEND | §28 |
| 28. Reglas esenciales | EXTEND | §2 |
| 29. AI_STUDIO_OPERATOR fallback | ADAPT | §30 |
| 29.1 Permission Matrix | ADAPT | §30.4–30.5 |
| 29.2 Gate universal de escalamiento | ADAPT | §30.2–30.3 |
| 29.3 Inicio / request / modos | ADAPT | §30.1–30.4 |
| 29.4 SHA Gate y evidencia | EXTEND | §30.6–30.7 |
| 29.5 Ventana única de intervención | ADAPT | §30 bounded activity |
| 29.6 Clasificación, seguridad y recuperación | ADAPT | §30.7–30.10 |
| 29.7 Publicación — exclusiva del Humano | PRESERVE | §25 |
| 29.8 RESEARCH_GATE / SPIKE_READ_ONLY | ADAPT | §29 |
| 29.9 Regla de no escritura | ADAPT | §30.5 |
| 29.10 REPORT / STOP | ADAPT | §30.7–30.10 |
| 29.11 Fallback de mutación externa | ADAPT | §30.11 |
| 29.12 Compatibilidad inmediata Issue #53 | NOT_APPLICABLE_WITH_JUSTIFICATION | §30.12 |
| 30. RESEARCH_GATE + STRATEGIC_RATIONALE | PRESERVE | §29 |
| 30.1 Cuándo se activa | ADAPT | §29.1 |
| 30.2 Investigación y evidencia | ADAPT | §29.2–29.3 |
| 30.3 Verificación del Supervisor | PRESERVE | §29.4 |
| 30.4 STRATEGIC_RATIONALE | PRESERVE | §29.5 |
| 30.5 Aplicación por rol/límites | PRESERVE | §29.5 and §31 |
| 31. TECHNICAL PERMISSION != WORKFLOW AUTHORITY | PRESERVE | §31 |
| 31.1 Escritura de repositorio/product-code | PRESERVE | §31.1 |
| 31.2 Escalación AI Studio | ADAPT | §31.2 / generic external actor |
| Resultado | ADAPT | §7 + Result |
| Apéndice A — Provenance de mejoras consolidadas | ADAPT | §0, §36, Appendix B |
| Apéndice B — Handover canónico | ADAPT | §0 status + §36 |
| Apéndice C — Matriz completa de trazabilidad del baseline | EXTEND | Appendix A + accepted matrix |

Coverage:

- accepted matrix rows: 71;
- rows represented in this trace: 71;
- missing rows: 0;
- silently grouped normative Work Item fields: 0;
- NOT_APPLICABLE_WITH_JUSTIFICATION: exactly 1, baseline 29.12 historical Issue #53 compatibility rule.

---

# Appendix B — Accepted iOS evidence provenance

This appendix preserves provenance without making Issue #2 an execution dependency.

Accepted evidence used conceptually includes:

1. iOS Capability Matrix
   - provider-neutral macOS build lane;
   - Simulator/physical-device distinction;
   - result evidence;
   - signing/provisioning/release separation.

2. iOS Evidence
   - Xcode command-line/native build boundary;
   - Swift Testing/XCTest;
   - xcodebuild test/result behavior;
   - Simulator/physical-device distinction;
   - provisioning/signing constraints;
   - TestFlight/App Store Connect mechanics;
   - provider options;
   - portable Swift vs native app boundary.

3. iOS Candidate 4
   - provider-neutral task/context/evidence control;
   - explicit macOS/Xcode build boundary;
   - risk-triggered Simulator/device verification;
   - isolated signing/TestFlight/App Store technical boundary.

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
   - macOS/Xcode primary native build boundary;
   - Simulator/physical-device evidence distinction;
   - Apple signing/provisioning;
   - TestFlight/App Store distribution;
   - Xcode Cloud optional;
   - no forced cross-platform symmetry.

7. Adversarial Audit
   - publication-authority defect history preserved;
   - Human publication invariant restored;
   - evidence cannot override authority.

8. Issue #8 architecture and iOS matrix
   - standalone document requirement;
   - source precedence;
   - lossless derivation;
   - complete 71-row matrix;
   - short BUILD → REVIEW → focused REWORK closure loop.

---

# Result

This workflow operationalizes iOS using the full inherited lifecycle plus justified iOS adaptation.

Normal execution is:

Human
→ Supervisor
→ bounded GitHub Work Item
→ Implementer bootstrap
→ project/Xcode context reconstruction
→ bounded implementation
→ project-native build/test
→ Simulator evidence when risk requires
→ physical-device evidence when risk requires
→ archive/export/signing evidence when required
→ evidence bundle
→ REPOSITORY_PUBLICATION
→ Implementer handoff
→ Supervisor exact-SHA review
→ SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE
→ separate MERGE_ELIGIBLE checks
→ merge only with authority
→ technical staging only when separately authorized
→ PUBLISH only by Human action
→ durable recovery from GitHub.

The document remains:

PROPOSAL — NOT CANONICAL

until a separate authorized adoption decision changes that status.
