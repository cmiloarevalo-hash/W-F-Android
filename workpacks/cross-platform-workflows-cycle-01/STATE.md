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

The START signal releases execution of the sequence already authorized by Issue #2. It does not alter authority or scope.

## Task state

| Task | Description | Status | Checkpoint commit |
|---|---|---|---|
| 01 | Research framework + invariants + scoring model | COMPLETED | `dfe67727fe7e41e4fb817745ef811e2f0bde2af9` |
| 02 | Android Candidates 1–3 | COMPLETED | this TASK 02 checkpoint commit; exact SHA persisted in Issue #2 and verified as remote HEAD |
| 03 | Android comparison + Candidate 4 | NOT_STARTED | — |
| 04 | iOS Candidates 1–3 | NOT_STARTED | — |
| 05 | iOS comparison + Candidate 4 | NOT_STARTED | — |
| 06 | Web Candidates 1–3 | NOT_STARTED | — |
| 07 | Web comparison + Candidate 4 | NOT_STARTED | — |
| 08 | Cross-platform common core + external actor interface | NOT_STARTED | — |
| 09 | Adversarial verification + contradiction audit | NOT_STARTED | — |
| 10 | Presentation proposal package + final handoff | NOT_STARTED | — |

## TASK 01 persisted outputs
- `outputs/01/research-method.md`
- `outputs/01/source-register.md`
- `outputs/01/invariants.md`
- `outputs/01/scoring-model.md`

## TASK 02 persisted outputs
- `outputs/02/android-evidence.md`
- `outputs/02/android-capability-matrix.md`
- `outputs/02/candidate-1-minimal.md`
- `outputs/02/candidate-2-portable.md`
- `outputs/02/candidate-3-verified.md`

TASK 02 verification:
- Android claims are sourced or explicitly marked inference/community evidence;
- candidates are structurally distinct (minimal vs adapter/portable vs tiered verified);
- local/cloud host build is separated from emulator/device capability;
- signing/AAB/Google Play remain explicit release boundaries;
- Firebase/Google Cloud are optional rather than silently mandatory;
- baseline and read-only paths were not modified;
- scope review limited writes to the authorized Workpack path.

## Continuation rule
After START has been issued, continue from the first task whose status is not COMPLETED.
Never infer progress from chat memory.

Continuity uses remote GitHub state:
Issue #2 → remote branch/ref → remote GitHub commit history → STATE.md → current prompt → required outputs.

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
