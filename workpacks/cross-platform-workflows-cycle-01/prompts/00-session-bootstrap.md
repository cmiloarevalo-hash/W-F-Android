# TASK 00 — Session bootstrap and authority acknowledgement

## OBJECTIVE

Demonstrate that you understand the persistent Workpack, your role and its limits before any execution begins.

This task does NOT authorize research or implementation.

## REQUIRED READS

Read, in this order:

1. GitHub Issue #2.
2. Branch `workpack/cross-platform-workflows-cycle-01`.
3. `workpacks/cross-platform-workflows-cycle-01/WORKPLAN.md`.
4. `workpacks/cross-platform-workflows-cycle-01/README.md`.
5. `workpacks/cross-platform-workflows-cycle-01/STATE.md`.
6. `AGENTS.md` — READ ONLY.
7. `PROGRAM.md` — READ ONLY.
8. `references/README.md` — READ ONLY.
9. Identify `references/WORKFLOW_BASE_ORIGINAL.md` as frozen READ-ONLY baseline. Do not modify it.

## REQUIRED VERIFICATIONS

Confirm:

- your role is Implementer / Technical Researcher;
- Supervisor is Chat Web GPT;
- authority comes from Issue #2;
- current branch is exactly `workpack/cross-platform-workflows-cycle-01`;
- writable scope is exactly `workpacks/cross-platform-workflows-cycle-01/**`;
- all other repository paths are read-only unless Issue #2 is explicitly amended by authorized Supervisor/Human decision;
- `references/**` is read-only;
- `G_INF_01` is read-only;
- baseline modification is forbidden;
- authority modification is forbidden;
- self-approval is forbidden;
- auto-merge is forbidden;
- candidate adoption is forbidden;
- TASK 01 remains NOT_STARTED;
- no STOP condition is currently known.

## FORBIDDEN DURING TASK 00

Do NOT:

- change any file;
- update STATE.md;
- create outputs;
- research Android/iOS/Web;
- create a commit;
- push;
- open a PR;
- start TASK 01;
- reinterpret or modify authority;
- propose a scope expansion;
- modify the baseline.

## REQUIRED RESPONSE

Post exactly one acknowledgement comment in Issue #2 using this structure:

```text
SESSION_BOOTSTRAP

ROLE: IMPLEMENTER / TECHNICAL RESEARCHER
SUPERVISOR: CHAT WEB GPT
AUTHORITY: ISSUE #2
BRANCH: workpack/cross-platform-workflows-cycle-01
AUTHORIZED_WRITE_PATH: workpacks/cross-platform-workflows-cycle-01/**

READ_ONLY:
- references/**
- AGENTS.md
- PROGRAM.md
- all other repository paths unless explicitly authorized
- cmiloarevalo-hash/G_INF_01

BASELINE: references/WORKFLOW_BASE_ORIGINAL.md
BASELINE_MODIFICATION: FORBIDDEN
AUTHORITY_CHANGE: FORBIDDEN
SCOPE_EXPANSION: FORBIDDEN
SELF_APPROVAL: FORBIDDEN
AUTO_MERGE: FORBIDDEN
CANONICAL_ADOPTION: FORBIDDEN

CURRENT_STATE: TASK 01 NOT_STARTED
STOP_CONDITION_PRESENT: NO | YES: <reason>
READY_FOR_START: YES | NO
NEXT_ACTION: WAIT_FOR_SUPERVISOR_START
```

If any required fact cannot be verified, set `READY_FOR_START: NO`, explain the exact blocker and STOP.

## END CONDITION

After posting the acknowledgement:

STOP.

Wait for the Supervisor's explicit START prompt.

Do not begin TASK 01 automatically.
