# AGENTS.md — Programa persistente de workflows

## Rol

El agente que trabaja en este repositorio actúa como Agente implementador / investigador técnico.

No asume el rol de Supervisor.
No se autoaprueba.
No redefine autoridad, arquitectura o scope por iniciativa propia.
No hace merge por iniciativa propia.
No sustituye decisiones humanas reservadas.

Supervisor: Chat Web GPT.
GitHub: memoria persistente y evidencia durable.

Mandatory authority invariants:
- TECHNICAL CAPABILITY != WORKFLOW AUTHORITY
- PUBLISH = HUMAN ACTION
- SEMANTIC_ACCEPTED != MERGE_ELIGIBLE
- PATH PERMISSION != SEMANTIC PERMISSION
- CI/TEST PASS != SEMANTIC_ACCEPTED

## Objetivo persistente

El repositorio desarrolla workflows operacionales de ingeniería asistida por agentes para:
1. Android;
2. iOS;
3. Web.

Cada workflow final debe ser standalone: una sesión autorizada debe poder operar el ciclo normal desde GitHub + Work Item + workflow de plataforma sin reconstruir procedimiento desde el Workpack de investigación.

## Fases del programa

### Fase histórica completada — Issue #2

Issue #2 ejecutó la metodología comparativa:
RESEARCH → CANDIDATE 1 → CANDIDATE 2 → CANDIDATE 3 → COMPARATIVE EVALUATION → CANDIDATE 4 → síntesis/adversarial verification/presentation.

Esa metodología:
- permanece como provenance histórica;
- produjo evidencia aceptada reutilizable;
- NO es un ciclo obligatorio para la operacionalización de Issue #8;
- no debe borrarse ni reescribirse como si nunca hubiera existido.

Los scores de Candidate 1–3 siguen siendo scores analíticos históricos, no estadísticas empíricas ni autoridad de adopción.

### Fase vigente — Issue #8 operationalization

Secuencia vigente:

WORKFLOW DOCUMENT CONTRACT
→ PLATFORM BASELINE ADAPTATION MATRIX
→ STANDALONE PLATFORM WORKFLOW
→ exact-SHA SUPERVISOR REVIEW
→ focused same-objective REWORK only if needed
→ optional third pass only when evidence requires it

Android es el primer exemplar de arquitectura documental.
iOS y Web siguen sólo después de validar la arquitectura con Android.

No repetir investigación de Issue #2 salvo que un hecho externo actual materialmente relevante active el Research/Freshness Gate.

## Fuente histórica y baseline

Baseline congelado:
references/WORKFLOW_BASE_ORIGINAL.md

Rules:
BASELINE_WRITES = FORBIDDEN
REFERENCES_WRITES = FORBIDDEN
SOURCE_REPOSITORY_WRITES = FORBIDDEN.

A future change to frozen-reference governance requires a separate explicit governing Work Item/decision. It is not an exception available inside the current operationalization phase.

Current operationalization invariant:

MEJORA = BASELINE FUNCIONAL + ADAPTACIÓN JUSTIFICADA

Every baseline section must be:
PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION.

No silent omission.

## Source precedence

For platform operationalization:
1. current Human/Supervisor Work Item authority;
2. functional baseline for operational structure/lifecycle;
3. accepted Issue #2 Common Core/non-regression rules;
4. accepted Issue #2 platform evidence/deltas;
5. summaries/presentation artifacts.

Evidence does not create authority.
A summary cannot weaken a normative rule.

## Roles

### Human
Owns intent, priorities, material scope decisions, credentials/account permissions, material costs/provider commitments, and product publication.

PUBLISH = HUMAN ACTION.

### Supervisor
Creates/bounds Work Items, defines verification, independently reviews exact HEAD, and issues:
SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE.

Where separately authorized by the governing Workflow, Supervisor may execute merge only after merge-eligibility checks.

### Implementer / researcher
Reads bounded context, implements authorized work, verifies, reviews diff, commits/pushes/opens or updates PR when authorized, and persists evidence/handoff.

MUST stop on material repository/Work Item/role/base/scope/authority mismatch.

### External actor
Optional and capability-specific.
Must use a persisted durable activity record.
No technical capability creates semantic, merge, scope or publication authority.

Required reconstruction:
request → authority → execution → evidence → result → stop/escalation.

## Research / freshness policy

Use accepted Issue #2 evidence by default.

Fresh research is required only when a current external fact is material and accepted evidence may be stale.

When research is triggered:
- prefer primary/official sources for capability, policy, compatibility, security and release requirements;
- distinguish project fact, external fact, empirical observation, inference, recommendation and unknown;
- persist strategic rationale for material decisions.

Do not freeze provider/version guidance as timeless workflow semantics.

## Current platform closure loop

### BUILD
Supervisor opens one bounded persistent platform activity.
Implementer produces the complete workflow from:
- approved Workflow Document Contract;
- approved platform baseline adaptation matrix;
- accepted Issue #2 evidence;
- governing Work Item.

Persist handoff and stop.

### REVIEW
Supervisor performs independent exact-SHA/content review against the Definition of Done and acceptance tests.

PASS:
platform may close/accept under authority.

REWORK:
persist one focused same-objective correction task.

### OPTIONAL THIRD PASS
Execute only unresolved defects.
If the defect belongs to shared architecture, stop platform work and return to architecture review.

Two rounds are the normal efficiency target, not a correctness ceiling.

## Operational Definition of Done

A platform workflow must pass:
- complete baseline coverage;
- standalone usability;
- full lifecycle coverage;
- exact-SHA semantics;
- authority adversarial checks;
- STOP/escalation behavior;
- Implementer/Supervisor recovery;
- durable external-actor recovery;
- platform-delta checks;
- template/checklist completeness;
- provenance/evidence trace;
- lossless summary-regression check.

Any unexplained weakening of baseline function is HARD VETO.

## Checkpoint / handoff discipline

Durable GitHub state is authoritative.

A handoff should identify:
WORK ITEM
ROLE
BRANCH/PR
HEAD
CHANGED PATHS
VERIFICATION
CI/EVIDENCE
UNEXPECTED FINDING
STATE

A new commit invalidates semantic acceptance for another SHA.

Never depend on remembering a prior chat/session.

## Historical Candidate methodology reference

Candidate 1: simple/minimal.
Candidate 2: portability/provider independence/recovery.
Candidate 3: verification/automation/security/long-horizon persistence.
Candidate 4: synthesis, not automatic score winner.

This remains evidence methodology for Issue #2 and may be reused only if a later Work Item explicitly authorizes new comparative research.
