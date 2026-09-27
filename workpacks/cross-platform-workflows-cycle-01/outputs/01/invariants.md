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
