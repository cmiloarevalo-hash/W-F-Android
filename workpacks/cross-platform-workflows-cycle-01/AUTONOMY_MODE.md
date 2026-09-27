# AUTONOMY MODE — unattended sequential execution

## Purpose

Allow the Implementer to continue the remaining Workpack while the Human/Supervisor may be absent, without converting the Implementer into the Supervisor.

## Mode

```text
AUTONOMY_MODE = UNATTENDED_SEQUENTIAL
```

After `AUTONOMY_RELEASE`, the Implementer may execute:

```text
TASK 03
→ TASK 04
→ TASK 05
→ TASK 06
→ TASK 07
→ TASK 08
→ TASK 09
→ TASK 10
→ final PR
→ final handoff
→ STOP
```

without waiting for a new prompt between tasks.

## Non-blocking review packets

TASK 03, TASK 05, TASK 07 and TASK 09 still produce `SUPERVISOR_REVIEW_PACKET.md`.

These packets are persistent evidence for later review.

They are **non-blocking by default** in unattended mode.

After completing one of those tasks, the Implementer may continue to the next task if:

- the current task is fully persisted;
- the checkpoint commit is verified on the authorized remote branch;
- STATE.md is updated;
- Issue #2 checkpoint is posted;
- no STOP condition exists;
- no explicit Supervisor `REWORK`, `HOLD` or `ESCALATE` is already present for the current or later state.

Absence of Supervisor review does not block unattended progress.

## Mandatory Issue check at every task boundary

Before starting each next task, the Implementer must read the latest Issue #2 comments using the GitHub integration/API.

If it finds a newer explicit Supervisor decision:

```text
REWORK
HOLD
ESCALATE
```

that applies to the current Workpack state, it must STOP and obey that decision.

If no such decision exists, it may continue.

## Final review boundary

The Implementer may draft the final workflow proposals, presentation brief and final PR.

This does not make them canonical.

After TASK 10 and final handoff:

```text
STOP
→ Supervisor/Human review
```

No merge.
No canonical adoption.
No modification of the frozen baseline.

## Decisions allowed during unattended execution

The Implementer may make local research/design decisions required to complete a task when they are:

- inside the authorized Workpack scope;
- reversible within candidate/proposal artifacts;
- explicitly documented as evidence, inference or recommendation;
- not a change of authority, product intent, credentials, cost commitment or canonical architecture.

It may compare alternatives and select/synthesize a Candidate 4 for presentation purposes.

That selection is not canonical adoption.

## Decisions that still require STOP

STOP remains mandatory if:

- writing outside the Workpack path is required;
- authority or scope must change;
- baseline/references/G_INF_01 would need modification;
- credentials, billing, paid services or external account changes are required;
- the GitHub integration loses a required capability;
- evidence reveals an unresolved contradiction that prevents a coherent candidate;
- a Supervisor/Human decision explicitly requires REWORK/HOLD/ESCALATE;
- final merge or canonical adoption would be required.

## Persistence discipline

For each task:

```text
read latest Issue #2 comments
→ read STATE + task prompt
→ execute
→ persist outputs
→ verify
→ update STATE
→ exactly one checkpoint commit through GitHub integration/API
→ verify remote HEAD
→ post checkpoint to Issue #2
→ proceed if no STOP condition
```

Conversational memory remains non-authoritative.

## Authority

```text
Issue #2 = authority
AUTONOMY_RELEASE = execution mode release
Implementer != Supervisor
Technical capability != workflow authority
```

Autonomy does not grant:
- scope expansion;
- authority changes;
- self-approval;
- merge;
- canonical adoption;
- baseline modification.
