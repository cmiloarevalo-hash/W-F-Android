# TASK 08 — Optional external actor interface

STATUS: PROPOSAL — NOT CANONICAL

An external actor is optional and exists only when a required capability is unavailable or better isolated from the Implementer/CI.

## Authority invariant

```text
TECHNICAL CAPABILITY != WORKFLOW AUTHORITY
```

Technical access to source, devices, browsers, signing, deployment, release tooling, credentials or publication controls does not grant Workflow authority.

The actor is defined by its explicit capability/authority contract, not by provider identity.

## Required actor contract

### CAPABILITY
One concrete capability, e.g.:
- Android physical-device matrix;
- iOS macOS/Xcode/device execution;
- web design/accessibility review;
- authorized technical release/deployment operation that does not transfer publication authority.

### PRECONDITIONS
Must include:
- authorized governing Work Item and task;
- exact repository ref/SHA and artifact hashes where applicable;
- provider/account/credential availability if required;
- cost/quota authorization if applicable;
- expected environment/configuration.

### AUTHORIZED OPERATIONS
Enumerate exact allowed actions. Default is deny outside the list.

Code implementation is forbidden unless it is explicitly authorized by the activity contract and the governing Work Item's Semantic Scope + Path Scope.

### FORBIDDEN OPERATIONS
At minimum:
- Workflow modification;
- Objective or Acceptance Criteria change;
- Semantic Scope or Path Scope expansion;
- authority expansion;
- unrelated source modifications;
- baseline/reference or canonical modification;
- code implementation unless explicitly authorized by the activity contract;
- self-approval;
- SEMANTIC_ACCEPTED decision;
- MERGE_ELIGIBLE decision;
- merge unless separately authorized under Workflow to the authorized Supervisor; the external actor itself never gains merge authority from technical capability;
- production publication by the technical actor;
- credential/account/billing changes unless explicitly authorized;
- new credential, paid service or provider commitment without authorization;
- unauthorized workaround after a STOP condition.

Publication invariant:

```text
PUBLISH = HUMAN ACTION
```

No Work Item permission, deploy credential, signing key, upload ability, release-tool access or technical capability transfers publication authority to the external actor or Implementer.

### EXPECTED BASELINE
Provide immutable inputs:
- governing Work Item;
- exact repository ref/SHA;
- artifact hashes;
- toolchain/configuration;
- requested test/deploy matrix;
- current Acceptance Criteria relevant to the activity.

### EVIDENCE RETURNED
Return only evidence required by the activity, e.g.:
- run/deployment ID;
- environment/device/browser metadata;
- pass/fail/skip;
- logs/reports/artifact references;
- retries/deviations;
- unresolved warnings.

### STOP CONDITIONS
Stop when:
- input baseline/ref/SHA differs;
- required credential/cost/account permission is missing;
- requested operation exceeds authority or scope;
- Objective/Acceptance Criteria/Semantic Scope/Path Scope would need to change;
- evidence is invalid/incomplete;
- provider/environment behavior creates a material contradiction;
- a new credential, paid service or provider commitment would be required without authorization.

Authority/scope contradiction is always STOP. Do not guess or silently expand authority.

### ESCALATION PATH
Return to Supervisor/Human with:
- exact blocker;
- evidence;
- requested decision;
- no unauthorized workaround.

## Durable GitHub activity record

Every external-actor invocation MUST create or update a durable GitHub activity/record under the governing Work Item. A chat-only or provider-only trace is insufficient.

Minimum record:

- ACTIVITY_ID / reference
- GOVERNING_WORK_ITEM
- ACTOR_TYPE
- CAPABILITY
- OBJECTIVE
- PRECONDITIONS
- AUTHORIZED_OPERATIONS
- FORBIDDEN_OPERATIONS
- EXPECTED_BASELINE / exact ref or SHA when applicable
- EVIDENCE_REQUIRED
- RESULT / evidence returned
- STOP_CONDITIONS
- ESCALATION_PATH
- STATUS / closure state

The durable record must let a later authorized Supervisor/Implementer reconstruct:

```text
request
→ authority
→ execution
→ evidence
→ result
→ stop/escalation
```

The activity record is evidence and continuity, not a new authority source. It cannot modify Workflow, Objective, Acceptance Criteria, Semantic Scope, Path Scope, baseline/canonical state, merge authority or publication authority.

No provider-specific activity mechanism is assumed. No public-standard meaning is assigned to "AIFUE"; if a project-specific schema exists, it may be referenced only under separate project authority.

## Interface invariant

An actor that technically can sign, deploy, upload, publish or edit still lacks Workflow permission unless the governing authority explicitly allows that technical operation. Even then:

- no self-approval;
- no SEMANTIC_ACCEPTED;
- no MERGE_ELIGIBLE;
- no authority/scope expansion;
- no publication by technical actor;
- **PUBLISH = HUMAN ACTION**.
