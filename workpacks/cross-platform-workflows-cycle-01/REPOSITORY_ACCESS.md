# REPOSITORY ACCESS CONTRACT — No local clone

## Purpose

The Implementer does **not** have a local Git repository capability for this Workpack.

Therefore the Implementer must not attempt to clone, copy, mount, checkout, pull, fetch, push or otherwise operate the repository through a local Git CLI/worktree.

## Mandatory access mode

All repository interaction must use the **GitHub integration/API functions available in the Implementer's execution environment**.

Use those capabilities to perform the equivalent remote operations, for example:

- read Issue #2 and its comments;
- inspect branch/ref metadata;
- read remote commit history;
- fetch files by repository path and explicit branch/ref;
- create or update files only inside the authorized path and target branch;
- create/persist checkpoint commits through the integration;
- update the authorized branch ref when the integration requires it;
- add Issue comments;
- open the final PR when TASK 10 authorizes it.

Exact function names depend on the execution environment. The contract is capability-based, not tool-name-based.

## Forbidden repository access

Do not run or attempt:

```text
git clone
git checkout
git switch
git pull
git fetch
git push
git add
git commit
git reset
git merge
local worktree creation
repository download/copy as a substitute for the GitHub integration
```

Do not claim to have a local checkout or filesystem-backed Git repository unless the Work Item is explicitly amended by the Supervisor/Human.

## Branch semantics

`workpack/cross-platform-workflows-cycle-01` is the **authorized remote target branch/ref**.

"Verify branch" means verify that the GitHub branch/ref exists and that repository writes are targeted to that branch.

It does not mean performing a local checkout.

## Checkpoint semantics

Whenever another Workpack document says:

```text
checkpoint commit + push
```

interpret it operationally as:

```text
persist exactly one checkpoint commit on the authorized remote branch
through the available GitHub integration/API
+
verify that the remote branch HEAD reflects that checkpoint
```

No local `git push` is required or authorized.

## Continuity semantics

Whenever another Workpack document refers to `git log`, interpret it as:

```text
remote GitHub commit history for the authorized branch
```

retrieved using the available GitHub integration/API.

## Capability gate

Before TASK 01, the Implementer must confirm that its environment can, through an authorized GitHub integration/API:

1. read Issue #2 and comments;
2. read branch/ref state;
3. read files by path/ref;
4. write files to the authorized target branch/path;
5. persist a checkpoint commit or equivalent repository commit state;
6. comment on Issue #2;
7. later open a PR.

If required repository write/commit capabilities are unavailable:

```text
READY_FOR_START: NO
STOP_CONDITION_PRESENT: YES: REQUIRED_GITHUB_INTEGRATION_CAPABILITY_UNAVAILABLE
```

Do not compensate by cloning/downloading the repository or inventing another write channel.

## Authority

Technical availability of a GitHub function does not grant permission to use it outside the Work Item.

```text
TECHNICAL CAPABILITY != WORKFLOW AUTHORITY
```

Issue #2, the Authorized Path Scope, STOP conditions and Supervisor decisions remain controlling.
