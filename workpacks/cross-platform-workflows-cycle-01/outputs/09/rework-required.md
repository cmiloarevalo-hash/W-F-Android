# TASK 09 — Rework required

STATUS: HISTORICAL BLOCKING REWORK RECORDED — CURRENT ACCEPTED CHAIN RE-AUDITED

## Why the original TASK 09 result was invalid

The original TASK 09 checkpoint `9a0da69e4fd031e203080d165eb65b89a9de5c22` stated:
- no blocking rework required;
- material corrections: none;
- prior-output correction log: none.

That was a confirmed false negative.

Supervisor TASK 08 review, Issue #2 comment `5880275506`, subsequently found blocking defects in the original TASK 08 checkpoint `e4063f7cf4fc8eff7b3120a2511d0a723114a849`.

## Actual prior blocking correction

Affected TASK 08 artifacts:
- `outputs/08/common-governance-core.md`;
- `outputs/08/external-actor-interface.md`;
- `outputs/08/cross-platform-evidence-map.md`.

Blocking defects:
1. complete nine-guarantee Common Core non-regression mapping was absent;
2. publication authority was weakened — **HARD VETO**;
3. durable GitHub external-actor activity required by comment `5879863384` was absent;
4. evidence-map traceability was incomplete.

Required publication invariant:
`PUBLISH = HUMAN ACTION`

Required authority invariant:
`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`

Required external-actor lifecycle:
`request → authority → execution → evidence → result → stop/escalation`

Correction commit:
`e1013c3a629032e98a4169b8b58eca77edd84230`

Supervisor result:
TASK 08 `SEMANTIC_ACCEPTED` at the same exact SHA, comment `5881622208`.

## Current post-correction status

The renewed TASK 09 audit of the accepted TASK 01–08 chain finds no unresolved material upstream contradiction.

Current checks:
- nine baseline guarantees: PASS;
- HARD VETO ordering: PASS;
- `PUBLISH = HUMAN ACTION`: PASS;
- `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`: PASS;
- durable external-actor activity `5879863384`: PASS;
- Android/iOS/Web platform deltas: PRESERVED;
- later REWORK regression: NOT DETECTED;
- baseline blob: unchanged at `fa6ce8e396e1ae422ce4feab3f97d7d37bb43f83`.

## Prior-output correction log

| Historical artifact/state | Finding | Correction/status |
|---|---|---|
| Original TASK 09 A-06 | False negative: publication-authority defect reported NOT FOUND | Preserved explicitly in reworked TASK 09 audit |
| Original TASK 08 Common Core | Nine protected guarantees incomplete | Corrected in `e1013c3a...` |
| Original TASK 08 external actor interface | Publication authority weakened | Corrected to `PUBLISH = HUMAN ACTION` |
| Original TASK 08 external actor interface | Durable activity record missing | Corrected per `5879863384` |
| Original TASK 08 evidence map | Missing nine-guarantee/publication/activity trace | Corrected in `e1013c3a...` |
| Original TASK 09 accepted-state trace | Only original checkpoints listed | Reworked to distinguish original checkpoint, REWORK SHA and final SEMANTIC_ACCEPTED SHA |

No historical evidence is deleted or silently rewritten; this TASK 09 REWORK adds the correction record and current post-correction audit.

## Files intentionally not corrected

`source-freshness-audit.md` is unchanged.

Reason:
- the Supervisor-authorized TASK 09 correction is governance/audit staleness;
- no newly discovered source-freshness contradiction requires modifying it;
- this REWORK does not claim a new external-source freshness sweep.

TASK 10, `STATE.md`, baseline and scoring remain outside this REWORK.

## Current rework assessment

UPSTREAM TASK 01–08 BLOCKING REWORK CURRENTLY IDENTIFIED: NO  
TASK 09 HISTORICAL FALSE NEGATIVE RECORDED: YES  
TASK 09 RE-AUDIT COMPLETED: YES  
TASK 09 SEMANTIC_ACCEPTED: NOT CLAIMED  
TASK 10 AUTHORIZED BY THIS FILE: NO  
NEXT ACTION: INDEPENDENT SUPERVISOR REVIEW
