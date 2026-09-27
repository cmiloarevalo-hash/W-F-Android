# TASK 00 — Session bootstrap and authority acknowledgement

## OBJECTIVE

Demonstrate that you understand the persistent Workpack, your role, repository-access method and authority limits before any execution begins.

This task does NOT authorize research or implementation.

## REQUIRED READS

Read, in this order, using the GitHub integration/API functions available in your environment:

1. GitHub Issue #2 and its current comments.
2. Remote branch/ref `workpack/cross-platform-workflows-cycle-01`.
3. `workpacks/cross-platform-workflows-cycle-01/REPOSITORY_ACCESS.md`.
4. `workpacks/cross-platform-workflows-cycle-01/WORKPLAN.md`.
5. `workpacks/cross-platform-workflows-cycle-01/README.md`.
6. `workpacks/cross-platform-workflows-cycle-01/STATE.md`.
7. `AGENTS.md` — READ ONLY.
8. `PROGRAM.md` — READ ONLY.
9. `references/README.md` — READ ONLY.
10. Identify `references/WORKFLOW_BASE_ORIGINAL.md` as frozen READ-ONLY baseline. Do not modify it.

## REPOSITORY ACCESS RULE

You do **not** have authority to clone or operate this repository through local Git.

Do not attempt `git clone`, checkout, pull, fetch, push, local worktrees, or repository downloads/copies.

Use only the GitHub integration/API capabilities provided by your execution environment.

The branch named below is a remote target ref, not a local checkout.

## REQUIRED VERIFICATIONS

Confirm:

- your role is Implementer / Technical Researcher;
- Supervisor is Chat Web GPT;
- authority comes from Issue #2;
- authorized remote target branch/ref is exactly `workpack/cross-platform-workflows-cycle-01`;
- repository operations must use the available GitHub integration/API, not local Git;
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
- the required GitHub integration/API capabilities listed in `REPOSITORY_ACCESS.md` are available;
- no STOP condition is currently known.

## FORBIDDEN DURING TASK 00

Do NOT:

- clone or download/copy the repository;
- run local Git repository commands;
- change any file;
- update STATE.md;
- create outputs;
- research Android/iOS/Web;
- create a commit;
- update the branch ref;
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
REPOSITORY_ACCESS: GITHUB_INTEGRATION_API_ONLY
LOCAL_CLONE: FORBIDDEN
LOCAL_GIT_WORKTREE: FORBIDDEN
TARGET_REMOTE_BRANCH: workpack/cross-platform-workflows-cycle-01
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

GITHUB_INTEGRATION_READ_CAPABILITY: AVAILABLE | UNAVAILABLE
GITHUB_INTEGRATION_WRITE_COMMIT_CAPABILITY: AVAILABLE | UNAVAILABLE
GITHUB_ISSUE_COMMENT_CAPABILITY: AVAILABLE | UNAVAILABLE
GITHUB_PR_CAPABILITY: AVAILABLE | UNAVAILABLE

CURRENT_STATE: TASK 01 NOT_STARTED
STOP_CONDITION_PRESENT: NO | YES: <reason>
READY_FOR_START: YES | NO
NEXT_ACTION: WAIT_FOR_SUPERVISOR_START
```

If a required GitHub integration/API capability cannot be verified, set `READY_FOR_START: NO`, identify the unavailable capability and STOP.

Do not compensate by cloning/downloading the repository or using another unapproved repository channel.

## END CONDITION

After posting the acknowledgement:

STOP.

Wait for the Supervisor's explicit START prompt.

Do not begin TASK 01 automatically.
