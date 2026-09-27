# TASK 01 — Workflow invariants

Status: EXPERIMENTAL DESIGN CONSTRAINTS — NOT CANONICAL  
Authority: Issue #2

These invariants are constraints for later candidates. They are not weighted preferences. A candidate may not silently weaken them to gain a higher analytical score.

## I-01 — Authority is external to technical capability

Issue #2 is the sole authority for this Workpack. Tool availability, model capability, repository permissions, test success, score, or convenience cannot enlarge authority.

## I-02 — Fixed roles and independent review

The Implementer / Technical Researcher does not become Supervisor, cannot self-approve, cannot merge, and cannot mark a proposal canonical. Chat Web GPT remains Supervisor.

## I-03 — Scope confinement

Writes are limited to:
`workpacks/cross-platform-workflows-cycle-01/**`

Everything else remains read-only unless Issue #2 is explicitly amended by authorized Supervisor/Human decision.

## I-04 — Frozen baseline integrity

`references/WORKFLOW_BASE_ORIGINAL.md`, `references/**`, and `cmiloarevalo-hash/G_INF_01` are read-only. Candidates are separate proposals, never implicit amendments.

## I-05 — GitHub is durable control/memory for this Workpack

Continuity must be reconstructable from Issue #2, remote branch/ref, remote commit history, Workpack state/prompts and persisted outputs. Chat memory is not authoritative.

## I-06 — Repository access contract

For this Workpack, repository operations use the available GitHub integration/API only. Local clone/worktree/download-as-working-copy and local Git operations remain forbidden.

## I-07 — Atomic task checkpoint

A task is not COMPLETED without all required outputs, verification, scope check, STATE update, exactly one checkpoint commit on the authorized remote branch, remote HEAD verification and Issue checkpoint.

## I-08 — Evidence class separation

PROJECT_FACT, EXTERNAL_FACT, EMPIRICAL_OBSERVATION, EXTERNAL_STATISTIC, ANALYTICAL_SCORE, INFERENCE, RECOMMENDATION and UNKNOWN must remain distinguishable.

## I-09 — No fabricated precision

Analytical scores are judgments under a declared rubric. They are not statistics or measurements. Unknown facts are not assigned neutral-looking numbers.

## I-10 — Current claims require current evidence

Material claims susceptible to change must be checked against current authoritative sources with date/version scope. Community evidence cannot silently substitute for primary capability/policy documentation.

## I-11 — Verification before progression

Later workflows must define verifiable completion conditions and must stop/fix or escalate when required validation fails. Passing tests or checks is evidence, not approval.

## I-12 — Security boundaries are explicit

A candidate must make write boundaries, secrets handling, network/tool permissions and higher-risk approval points explicit enough to audit. Security cannot rely solely on agent discretion.

## I-13 — Human/Supervisor gates cannot be optimized away

Independent review points required by the Workpack remain gates even if automation is technically capable of continuing.

## I-14 — Candidate status remains non-canonical

All outputs remain EXPERIMENTAL / CANDIDATE / PROPOSAL until independent adoption through a future authorized process.

## I-15 — Candidate 4 is synthesis, not score winner

Candidate 4 must synthesize justified strengths and address weaknesses. Highest weighted mean alone cannot automatically determine Candidate 4.

## I-16 — Platform specificity is preserved

Common governance may be shared, but Android/iOS/Web differences in build, signing, sandboxing, CI, distribution and policy must not be erased to force symmetry.

## I-17 — Optional external actors require a contract

An external actor is included only for a verified capability need and must define:
- CAPABILITY
- PRECONDITIONS
- AUTHORIZED OPERATIONS
- FORBIDDEN OPERATIONS
- EXPECTED BASELINE
- EVIDENCE RETURNED
- STOP CONDITIONS
- ESCALATION PATH

## I-18 — No hidden dependency/adoption

A workflow cannot silently require a new paid service, credential, provider, hosted dependency or distribution commitment not authorized by the Work Item. Such a requirement is surfaced for human/Supervisor decision or triggers STOP when required.

## I-19 — Context is progressive, not indiscriminately accumulated

Persistent instructions should keep stable governance/constraints, while task-specific detail is loaded when relevant. Later candidates must avoid requiring every historical document in every step when a narrower context is sufficient.

## I-20 — Auditability of recommendation changes

If later evidence causes a criterion, weight, assumption or recommendation to change, the change must be explicit and justified. Silent post-hoc alteration of the scoring model to favor a candidate is forbidden.

## Invariant handling in comparisons

- Violation of I-01 through I-07 or I-13/I-14 is a hard veto for the Workpack.
- Other invariant violations are material defects requiring correction or explicit Supervisor/Human escalation before adoption.
- Weighted scores never compensate for a hard-veto violation.


## Baseline functional non-regression invariants

The frozen baseline is read-only, but its proven functional guarantees are inputs to candidate evaluation. Platform-specific mechanisms may change; the functions below may not be silently removed, weakened, or reinterpreted.

### I-21 — Work Item contract is structurally preserved

Every implementation/research Work Item MUST preserve the baseline contract structure:

- Objective;
- Acceptance Criteria;
- Authorized Scope;
- Relevant Sources;
- Verification;
- Base.

Platform-specific content may populate these fields differently, but the fields and their control function remain mandatory. Missing or materially weakened contract elements are a hard veto unless a Human-authorized semantic change explicitly supersedes them.

### I-22 — Semantic Scope and Path Scope are independent constraints

Every Work Item MUST preserve both:

- **Semantic Scope**: the behavior/change that is authorized;
- **Path Scope**: the files/modules/paths that may be modified.

Path permission never implies semantic permission. A change can be inside an authorized path and still violate Semantic Scope. Both constraints must pass independently.

### I-23 — Supervisor review is bound to the exact SHA

A Supervisor semantic decision is valid only for the exact reviewed commit SHA.

A new commit creates a new HEAD and invalidates prior semantic acceptance for that new HEAD. Automated checks, unchanged filenames, or a small diff do not carry forward semantic acceptance automatically.

### I-24 — Independent review state machine is preserved

The baseline Supervisor decision states remain:

- `SEMANTIC_ACCEPTED`;
- `REWORK`;
- `HOLD`;
- `ESCALATE`.

These are independent semantic/governance decisions. Tests, CI, scoring, lint, build success, or agent confidence cannot substitute for them.

### I-25 — REWORK continuity is preserved when the objective is unchanged

When a correction remains within the same Objective and authorized scope, REWORK normally continues in the same:

- Issue;
- branch;
- PR.

A correction that requires a changed objective, authority, Semantic Scope, Path Scope, baseline change, or other material scope expansion must escalate instead of silently reusing the existing Work Item.

### I-26 — Merge authority remains with the Supervisor under baseline conditions

The Implementer never self-merges.

Where a Work Item/Human authority permits integration, merge authority remains with Chat Web GPT / Supervisor only after:

1. semantic review of the exact current PR HEAD SHA;
2. `SEMANTIC_ACCEPTED` for that SHA;
3. merge-eligibility checks required by the baseline, including target validity and conflict/integration conditions.

`SEMANTIC_ACCEPTED` alone is not equivalent to `MERGE_ELIGIBLE`.

This Workpack currently authorizes no merge; the invariant preserves the baseline function without creating new merge authority.

### I-27 — Publication authority remains human

The baseline rule is preserved exactly:

`PUBLISH = HUMAN ACTION`

Build, sign, upload, deploy, release-tool access, store credentials, or technical ability to publish do not create publication authority. Any platform-specific release mechanism must preserve this human publication boundary unless a later Human-authorized semantic change explicitly replaces it.

### I-28 — Session recovery is reconstructable from GitHub

A new Supervisor or Implementer session MUST be able to reconstruct the active state from persisted GitHub artifacts without relying on the previous chat transcript.

At minimum, recovery must identify:
- governing Work Item / Issue;
- current branch/ref and exact HEAD;
- active PR when one exists;
- latest applicable Supervisor decision and reviewed SHA;
- current state/checkpoint/evidence;
- unresolved REWORK/HOLD/ESCALATE conditions.

### I-29 — Baseline functional non-regression gate

Before weighted scoring or recommendation, every candidate MUST map each protected baseline functional guarantee to exactly one status:

- `PRESERVED AS-IS`;
- `PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION`;
- `NOT APPLICABLE` with explicit justification.

Any unexplained loss, weakening, substitution, or reinterpretation of a baseline functional guarantee is a **HARD VETO**.

A hard veto:
- makes the candidate ineligible for comparative ranking/adoption;
- cannot be offset by a higher weighted score;
- cannot be cured by CI/test success alone;
- requires correction or explicit Human-authorized semantic change.

## Baseline → TASK 01 preservation map

| Baseline function / section | TASK 01 invariant / gate | Preservation status | Non-regression interpretation |
|---|---|---|---|
| §7 Work Item / Issue contract: Objective + Acceptance Criteria + Authorized Scope + Relevant Sources + Verification + Base | I-21 | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | Contract structure and control function remain mandatory; field contents may vary by platform/project. |
| §8 Two scopes: Semantic Scope + Path Scope | I-22 | PRESERVED AS-IS | Both must independently authorize the change; path access never grants semantic authority. |
| §§18 and 21 review/decision tied to reviewed SHA; new commit invalidates prior acceptance for new HEAD | I-23 | PRESERVED AS-IS | Semantic acceptance never floats across commits. |
| §19 Supervisor decisions: SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | I-24 | PRESERVED AS-IS | Automated evidence cannot replace the semantic state machine. |
| §20 REWORK: same Issue / same branch / same PR for same objective | I-25 | PRESERVED AS-IS | Rework continuity is retained; scope-changing correction escalates. |
| §§23–24 integration/merge: SEMANTIC_ACCEPTED is not MERGE_ELIGIBLE; Supervisor executes merge only after exact-SHA review and eligibility checks | I-26 | PRESERVED AS-IS | Implementer never self-merges; current Workpack remains stricter because merge is not authorized. |
| §27 Human role and superseding publication rule: PUBLISH = HUMAN ACTION | I-27 | PRESERVED AS-IS | Platform release mechanics may differ, but publication authority remains human. |
| §§25–26 session changes and §28 essential rule: reconstruct from GitHub, not prior transcript | I-28 | PRESERVED AS-IS | GitHub artifacts remain the durable recovery source for both roles. |
| Baseline structural/functional preservation requirement, enforced by TASK_01_SUPERVISOR_CHECK | I-29 | PRESERVED AS-IS | Every later candidate requires an explicit mapping; unexplained weakening is a hard veto. |

## Baseline functional non-regression handling in comparisons

The earlier invariant handling remains in force and is strengthened as follows:

- Any violation of I-21 through I-29 is a hard veto unless the invariant itself explicitly describes a permitted platform-specific implementation.
- `NOT APPLICABLE` is valid only with a concrete justification showing that the baseline function has no corresponding operation for the candidate; convenience or implementation difficulty is not sufficient.
- A candidate with an unexplained baseline-function regression MUST NOT be presented as eligible merely because it has a higher analytical score.
- The preservation map is methodology/evaluation evidence. It does not modify the frozen baseline and does not itself authorize later-task edits.
