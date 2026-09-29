# WORKPLAN — Cross-platform workflows cycle 01

## Purpose

Execute a persistent sequential research/design program to produce review-ready workflow proposals for:

1. Android.
2. iPhone / iOS.
3. Web applications.

The Implementer is not the Supervisor and may not change authority, baseline, scope or adoption status.

## Repository operating model

The Implementer must use the GitHub integration/API functions available in its execution environment.

It must not clone, download/copy or operate the repository through a local Git checkout/worktree.

Read `REPOSITORY_ACCESS.md` before any execution.

All references in this Workpack to:
- branch verification mean remote branch/ref verification;
- `git log` mean remote GitHub commit history;
- checkpoint commit + push mean one checkpoint commit persisted on the authorized remote branch and remote HEAD verification.

## Entry gate — TASK 00

TASK 00 is a session-recognition gate.

It is intentionally non-executive.

The Implementer must:
- read Issue #2;
- verify the remote target branch/ref;
- read REPOSITORY_ACCESS.md;
- read this WORKPLAN;
- read README.md and STATE.md;
- read AGENTS.md and PROGRAM.md as read-only governance context;
- read references/README.md and identify the frozen baseline;
- confirm write scope and read-only paths;
- confirm required GitHub integration/API capabilities;
- confirm STOP conditions;
- confirm that TASK 01 is NOT_STARTED;
- post the required READY acknowledgement in Issue #2.

During TASK 00 the Implementer must NOT:
- clone/download/copy the repository;
- use a local Git checkout/worktree;
- research platform recommendations;
- generate candidate outputs;
- change STATE.md;
- modify files;
- create a checkpoint commit;
- update the branch ref;
- start TASK 01;
- alter authority, workflow rules, scope or baseline.

After a valid acknowledgement, the Implementer must WAIT for an explicit START instruction from the Supervisor.

The START instruction releases execution of the already-authorized sequence; it does not create or alter authority.

## Execution plan

### TASK 01 — Research framework and invariants
Outputs:
- research method;
- source register;
- invariants;
- scoring model;
- sensitivity-analysis method.

Goal:
Fix the evidence methodology before candidate generation.

Checkpoint:
one remote checkpoint commit persisted through GitHub integration/API + verify branch HEAD + Issue #2 checkpoint.

### TASK 02 — Android Candidates 1–3
Outputs:
- current Android evidence;
- capability matrix;
- Candidate 1 Minimal;
- Candidate 2 Portable;
- Candidate 3 Verified.

Checkpoint:
one remote checkpoint commit + branch HEAD verification + Issue #2 checkpoint.

### TASK 03 — Android comparison + Candidate 4
Outputs:
- weighted comparison;
- sensitivity analysis;
- Candidate 4 presentation proposal;
- Supervisor Review Packet.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

Supervisor checkpoint:
PASS | REWORK | HOLD | ESCALATE.

### TASK 04 — iOS Candidates 1–3
Outputs:
- current iOS evidence;
- capability matrix;
- Candidate 1 Minimal;
- Candidate 2 Portable;
- Candidate 3 Verified.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

### TASK 05 — iOS comparison + Candidate 4
Outputs:
- comparison;
- sensitivity analysis;
- Candidate 4;
- Supervisor Review Packet.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

Supervisor checkpoint:
PASS | REWORK | HOLD | ESCALATE.

### TASK 06 — Web Candidates 1–3
Outputs:
- current web/tooling evidence;
- capability matrix;
- Candidate 1 Minimal;
- Candidate 2 Portable;
- Candidate 3 Verified.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

### TASK 07 — Web comparison + Candidate 4
Outputs:
- comparison;
- sensitivity analysis;
- Candidate 4;
- Supervisor Review Packet.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

Supervisor checkpoint:
PASS | REWORK | HOLD | ESCALATE.

### TASK 08 — Cross-platform synthesis
Outputs:
- smallest common governance core;
- platform-specific deltas;
- optional external actor interface;
- evidence map.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

### TASK 09 — Adversarial verification
Outputs:
- contradiction audit;
- baseline traceability;
- source freshness audit;
- semantic propagation risk analysis;
- required rework register;
- Supervisor Review Packet.

Purpose:
Attempt to falsify earlier conclusions and detect semantic errors before final packaging.

Checkpoint:
one remote checkpoint commit + branch HEAD verification.

Supervisor checkpoint:
PASS | REWORK | HOLD | ESCALATE.

### TASK 10 — Presentation proposal package
Outputs:
- Android workflow proposal;
- iOS workflow proposal;
- Web workflow proposal;
- common-core proposal;
- presentation brief;
- final handoff.

All proposals must state:
STATUS: PROPOSAL — NOT CANONICAL.

Finalization:
- verify TASKS 01–10 COMPLETED;
- verify baseline unchanged;
- verify no out-of-scope writes;
- open one PR to main for evaluation using the available GitHub integration/API;
- persist final handoff in Issue #2;
- STOP.

## Continuity rule

Conversational memory is not authoritative.

Recover in this order:

Issue #2
→ remote target branch/ref
→ remote GitHub commit history
→ REPOSITORY_ACCESS.md
→ WORKPLAN.md
→ STATE.md
→ prompt for first non-COMPLETED task
→ required previous outputs only.

## Authority rule

The Issue creates authority.
Prompts transmit actions within that authority.

Neither a prompt, model capability, GitHub function, tool permission nor repository write access may:
- enlarge scope;
- change roles;
- modify baseline authority;
- grant self-approval;
- grant merge authority;
- adopt a proposal as canonical.

## Review cadence

Mandatory independent Supervisor review after:
- TASK 03;
- TASK 05;
- TASK 07;
- TASK 09;
- final PR / TASK 10.

This is designed to reduce semantic error propagation while preserving long-horizon sequential execution.
