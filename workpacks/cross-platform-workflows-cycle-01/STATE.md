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
| TASK 00 — session bootstrap acknowledgement | ACKNOWLEDGED |
| GitHub integration capability confirmation | VERIFIED |
| Supervisor START release | ISSUED |

## Autonomy transition gate
| Gate | Status |
|---|---|
| TASK 01 | COMPLETED |
| TASK 02 | COMPLETED |
| AUTONOMY_MODE acknowledgement | ACKNOWLEDGED |
| AUTONOMY_RELEASE | ISSUED |

Mode: `UNATTENDED_SEQUENTIAL`

This release does not change authority, scope, baseline protection, merge authority, or canonical-adoption rules.

## Task state

| Task | Description | Status | Checkpoint commit |
|---|---|---|---|
| 01 | Research framework + invariants + scoring model | COMPLETED | `dfe67727fe7e41e4fb817745ef811e2f0bde2af9` |
| 02 | Android Candidates 1–3 | COMPLETED | `3e3fe5fb144b28cf40343e22895ea67ca14f92df` |
| 03 | Android comparison + Candidate 4 | COMPLETED | this TASK 03 checkpoint commit; exact SHA persisted in Issue #2 and verified as remote HEAD |
| 04 | iOS Candidates 1–3 | NOT_STARTED | — |
| 05 | iOS comparison + Candidate 4 | NOT_STARTED | — |
| 06 | Web Candidates 1–3 | NOT_STARTED | — |
| 07 | Web comparison + Candidate 4 | NOT_STARTED | — |
| 08 | Cross-platform common core + external actor interface | NOT_STARTED | — |
| 09 | Adversarial verification + contradiction audit | NOT_STARTED | — |
| 10 | Presentation proposal package + final handoff | NOT_STARTED | — |

## TASK 03 persisted outputs
- `outputs/03/android-comparison.md`
- `outputs/03/android-sensitivity.md`
- `outputs/03/android-candidate-4-presentation.md`
- `outputs/03/SUPERVISOR_REVIEW_PACKET.md`

TASK 03 verification:
- all candidates evaluated with the TASK 01 rubric;
- analytical scores explicitly distinguished from measurements/statistics;
- sensitivity analysis completed;
- Candidate 4 synthesized rather than mechanically selected;
- each material Candidate 4 rule traced to evidence or explicit inference;
- baseline differences recorded without modifying the baseline;
- mandatory Supervisor Review Packet produced;
- writes limited to authorized Workpack paths.

## Continuation rule
In unattended mode, continue to the first task not COMPLETED only after:
1. the current checkpoint commit is verified at remote HEAD;
2. Issue #2 checkpoint is posted;
3. latest Issue #2 comments are checked;
4. no applicable REWORK/HOLD/ESCALATE or other STOP condition exists.

Conversational memory is non-authoritative.

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
- Supervisor has posted HOLD/REWORK/ESCALATE on the active workpack;
- merge or canonical adoption would be required.
