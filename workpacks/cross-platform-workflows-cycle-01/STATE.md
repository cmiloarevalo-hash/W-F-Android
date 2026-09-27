# STATE — cross-platform workflow cycle 01

## Fixed context
- Authority: Issue #2
- Repository access: GitHub integration/API only; NO local clone/worktree
- Remote target branch/ref: `workpack/cross-platform-workflows-cycle-01`
- Writable scope: `workpacks/cross-platform-workflows-cycle-01/**`
- Baseline: `references/WORKFLOW_BASE_ORIGINAL.md` — READ ONLY
- Supervisor: Chat Web GPT
- Implementer: execution/research agent
- Mode: `UNATTENDED_SEQUENTIAL`

## Task state
| Task | Description | Status | Checkpoint commit |
|---|---|---|---|
| 01 | Research framework + invariants + scoring model | COMPLETED | `dfe67727fe7e41e4fb817745ef811e2f0bde2af9` |
| 02 | Android Candidates 1–3 | COMPLETED | `3e3fe5fb144b28cf40343e22895ea67ca14f92df` |
| 03 | Android comparison + Candidate 4 | COMPLETED | `a83d0c88de2cab09566bd534a8a99253469932cb` |
| 04 | iOS Candidates 1–3 | COMPLETED | `db136e8cfd89c731527500e6e718b282ca90a433` |
| 05 | iOS comparison + Candidate 4 | COMPLETED | `51b575094c59a8496fd76f98439be7692942f1bb` |
| 06 | Web Candidates 1–3 | COMPLETED | this TASK 06 checkpoint commit; exact SHA persisted in Issue #2 and verified as remote HEAD |
| 07 | Web comparison + Candidate 4 | NOT_STARTED | — |
| 08 | Cross-platform common core + external actor interface | NOT_STARTED | — |
| 09 | Adversarial verification + contradiction audit | NOT_STARTED | — |
| 10 | Presentation proposal package + final handoff | NOT_STARTED | — |

## TASK 06 outputs
- `outputs/06/web-evidence.md`
- `outputs/06/web-capability-matrix.md`
- `outputs/06/candidate-1-minimal.md`
- `outputs/06/candidate-2-portable.md`
- `outputs/06/candidate-3-verified.md`

Verification:
- governance is framework-neutral;
- stack choices are adapters, not workflow authority;
- browser/E2E, accessibility, preview/UX and deployment boundaries are distinct;
- frontend/backend/secrets boundaries are explicit;
- provider neutrality preserved;
- candidates structurally distinct;
- writes limited to authorized Workpack scope.

## Continuation rule
Before every next task, read latest Issue #2 comments and stop on applicable REWORK/HOLD/ESCALATE or another STOP condition.

## Global STOP
STOP if required GitHub capability is unavailable; local Git/download would be required; out-of-scope write, authority/scope/baseline change, unauthorized credentials/billing/external account change, unresolved material contradiction, unverifiable task/checkpoint, applicable REWORK/HOLD/ESCALATE, merge or canonical adoption is required.
