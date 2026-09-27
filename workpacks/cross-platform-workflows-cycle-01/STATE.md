# STATE — cross-platform workflow cycle 01

## Fixed context
- Authority: Issue #2
- Branch: `workpack/cross-platform-workflows-cycle-01`
- Writable scope: `workpacks/cross-platform-workflows-cycle-01/**`
- Baseline: `references/WORKFLOW_BASE_ORIGINAL.md` — READ ONLY
- Supervisor: Chat Web GPT
- Implementer: execution/research agent

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
Continue from the first task whose status is not COMPLETED.
Never infer progress from chat memory.

## Global STOP
STOP and persist coherent state if:
- write outside authorized scope is required;
- baseline/workflow source modification appears necessary;
- product/human decision is required;
- evidence contradicts a previous material assumption and cannot be resolved inside the current task;
- a dependency/cost/credential must be adopted without prior authority;
- current task outputs cannot be verified;
- previous checkpoint commit/push is missing;
- Supervisor has posted HOLD/REWORK/ESCALATE on the active workpack.
