# Cross-platform workflows — sequential workpack cycle 01

## Authority
Persistent authority: GitHub Issue #2.

This workpack is an experimental/design package. Nothing produced here becomes a canonical workflow automatically.

## Repository access
The Implementer must use only the GitHub integration/API functions available in its environment.

No local clone, repository copy/download, local checkout/worktree, `git pull`, `git fetch` or `git push`.

Read:
`REPOSITORY_ACCESS.md`

The authorized branch is a remote target ref.

## Session entry
Before TASK 01, the Implementer must execute `prompts/00-session-bootstrap.md`.

TASK 00 is acknowledgement-only:
- no file writes;
- no research;
- no STATE change by Implementer;
- no commit/ref update;
- no TASK 01.

After a valid `READY_FOR_START: YES` comment in Issue #2, the Implementer waits for an explicit Supervisor START signal.

## Branch
Remote target branch/ref:
`workpack/cross-platform-workflows-cycle-01`

## Writable scope
```text
workpacks/cross-platform-workflows-cycle-01/**
```

Everything else is read-only for the Implementer unless Issue #2 is explicitly amended by authorized Supervisor/Human decision.

Especially:
```text
references/**   READ ONLY
AGENTS.md       READ ONLY
PROGRAM.md      READ ONLY
G_INF_01        READ ONLY
workflow base   READ ONLY
```

## Continuity
Conversational memory is non-authoritative.

Recover from:
```text
Issue #2
→ remote branch/ref
→ remote GitHub commit history
→ REPOSITORY_ACCESS.md
→ WORKPLAN.md
→ STATE.md
→ current prompt
→ completed outputs
```

After START, continue from the first task not marked COMPLETED.

## Automatic continuation
Issue #2 pre-authorizes TASK 01 → TASK 10, but execution is held behind the session START gate.

After START, the Implementer may continue automatically only when the current task has:
1. required outputs;
2. verification complete;
3. scope check complete;
4. STATE.md updated;
5. exactly one checkpoint commit persisted on the authorized remote branch;
6. remote branch HEAD verification complete;
7. no STOP CONDITION.

## Candidate status
All outputs are experimental candidates/proposals.

```text
NO SELF-APPROVAL
NO AUTO-ADOPTION
NO AUTO-MERGE
NO BASELINE MODIFICATION
NO AUTHORITY CHANGE
NO LOCAL REPOSITORY CLONE
```

One final PR may be opened after TASK 10 for Supervisor evaluation.
