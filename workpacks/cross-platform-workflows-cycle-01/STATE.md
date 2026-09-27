# STATE — cross-platform workflow cycle 01

## Fixed context
- Authority: Issue #2
- Repository access: GitHub integration/API only; NO local clone/worktree
- Remote target branch/ref: `workpack/cross-platform-workflows-cycle-01`
- Writable scope: `workpacks/cross-platform-workflows-cycle-01/**`
- Baseline: `references/WORKFLOW_BASE_ORIGINAL.md` — READ ONLY
- Supervisor: Chat Web GPT
- Implementer: execution/research agent

## Session entry gate

| Gate | Status |
|---|---|
| TASK 00 — session bootstrap acknowledgement | WAITING_FOR_ACKNOWLEDGEMENT |
| GitHub integration capability confirmation | NOT_VERIFIED |
| Supervisor START release | NOT_ISSUED |

TASK 01 MUST NOT start until:
1. TASK 00 acknowledgement is persisted in Issue #2 with `READY_FOR_START: YES`;
2. required GitHub integration/API capabilities are confirmed; and
3. Supervisor sends explicit START.

The START signal releases execution of the sequence already authorized by Issue #2. It does not alter authority or scope.

## Task state

| Task | Description | Status | Checkpoint commit |
|---|---|---|---|
| 01 | Research framework + invariants + scoring model | NOT_STARTED | — |
| 02 | Android Candidates 1–3 | NOT_STARTED | — |
| 03 | Android comparison + Candidate 4 | NOT_STARTED | — |
| 04 | iOS Candidates 1–3 | NOT_STARTED | — |
| 05 | iOS comparison + Candidate 4 | NOT_STARTED | — |
| 06 | Web Candidates 1–3 | NOT_STARTED | — |
| 07 | Web comparison + Candidate 4 | NOT_STARTED | — |
| 08 | Cross-platform common core + external actor interface | NOT_STARTED | — |
| 09 | Adversarial verification + contradiction audit | NOT_STARTED | — |
| 10 | Presentation proposal package + final handoff | NOT_STARTED | — |

## Continuation rule
After START has been issued, continue from the first task whose status is not COMPLETED.
Never infer progress from chat memory.

Continuity uses remote GitHub state:
Issue #2 → remote branch/ref → remote commit history → STATE.md → current prompt → required outputs.

## Global STOP
STOP and persist coherent state if:
- required GitHub integration/API capability is unavailable;
- repository access would require clone/download/local Git;
- write outside authorized scope is required;
- baseline/workflow source modification appears necessary;
- authority or scope change is required;
- product/human decision is required;
- evidence contradicts a previous material assumption and cannot be resolved inside the current task;
- a dependency/cost/credential must be adopted without prior authority;
- current task outputs cannot be verified;
- previous remote checkpoint commit/branch HEAD verification is missing;
- Supervisor has posted HOLD/REWORK/ESCALATE on the active workpack.
