# Cross-platform workflows — sequential workpack cycle 01

## Authority
Persistent authority: GitHub Issue #2.

This workpack is an experimental/design package. Nothing produced here becomes a canonical workflow automatically.

## Branch
`workpack/cross-platform-workflows-cycle-01`

## Writable scope
```text
workpacks/cross-platform-workflows-cycle-01/**
```

Everything else is read-only for the Implementer unless Issue #2 is explicitly amended by the Supervisor/Human.

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
→ branch
→ git log
→ STATE.md
→ current prompt
→ completed outputs
```

Continue from the first task not marked COMPLETED.

## Automatic continuation
Issue #2 pre-authorizes TASK 01 → TASK 10.

The Implementer may continue automatically only when the current task has:
1. required outputs;
2. verification complete;
3. scope check complete;
4. STATE.md updated;
5. exactly one checkpoint commit for that task;
6. push complete;
7. no STOP CONDITION.

## Candidate status
All outputs are experimental candidates/proposals.

```text
NO SELF-APPROVAL
NO AUTO-ADOPTION
NO AUTO-MERGE
NO BASELINE MODIFICATION
```

One final PR may be opened after TASK 10 for Supervisor evaluation.
