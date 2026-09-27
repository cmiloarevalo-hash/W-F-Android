# TASK 08 — Optional external actor interface

STATUS: PROPOSAL — NOT CANONICAL

An external actor is optional and exists only when a required capability is unavailable or better isolated from the Implementer/CI.

## Required contract

### CAPABILITY
One concrete capability, e.g.:
- Android physical-device matrix;
- iOS macOS/Xcode/device execution;
- web design/accessibility review;
- authorized release/deployment operation.

### PRECONDITIONS
Must include:
- authorized Work Item and task;
- exact repository ref/artifact hashes;
- provider/account/credential availability if required;
- cost/quota authorization if applicable;
- expected environment/configuration.

### AUTHORIZED OPERATIONS
Enumerate exact allowed actions. Default is deny outside the list.

### FORBIDDEN OPERATIONS
At minimum:
- authority/scope changes;
- unrelated source modifications;
- baseline/reference modification;
- credential/account/billing changes unless explicitly authorized;
- merge/canonical adoption;
- production release unless the Work Item explicitly grants it.

### EXPECTED BASELINE
Provide immutable inputs:
- repository/ref;
- artifact hashes;
- toolchain/configuration;
- requested test/deploy matrix;
- current task acceptance criteria.

### EVIDENCE RETURNED
Return:
- run/deployment ID;
- environment/device/browser metadata;
- pass/fail/skip;
- logs/reports/artifact references;
- retries/deviations;
- unresolved warnings.

### STOP CONDITIONS
Stop when:
- input baseline differs;
- required credential/cost/account permission is missing;
- requested operation exceeds authority;
- evidence is invalid/incomplete;
- provider/environment behavior creates a material contradiction.

### ESCALATION PATH
Return to Supervisor/Human with:
- exact blocker;
- evidence;
- requested decision;
- no unauthorized workaround.

## Interface invariant

`CAPABILITY != AUTHORITY`

An actor that technically can sign, deploy, publish or edit does not have workflow permission to do so unless the Work Item explicitly grants that operation.
