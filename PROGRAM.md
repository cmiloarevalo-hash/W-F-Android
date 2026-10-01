# Programa de workflows operacionales — Android, iOS y Web

## Propósito

Este repositorio mantiene un programa persistente para producir workflows operacionales standalone de ingeniería asistida por agentes para:
- Android;
- iOS;
- Web.

El objetivo vigente no es generar propuestas cortas. Es adaptar el Workflow funcional original con pérdida cero de función operativa y sólo con deltas justificados por plataforma.

## Estado del programa

### Issue #2 — fase comparativa completada

Issue #2 realizó:
Research Gate → Candidate 1–3 → comparative evaluation → Candidate 4 → síntesis transversal → adversarial verification → final proposal package.

Resultado:
- evidencia Android/iOS/Web aceptada;
- Common Core aceptado;
- deltas de plataforma aceptados;
- actor externo durable aceptado;
- nueve garantías + HARD VETO preservados;
- parent final revisado: 84172391dce91e9aa14d433b4859ae6f8f5bac0c.

La fase comparativa queda histórica/completada.
No es obligatoria para Issue #8.

### Issue #8 — fase de operacionalización vigente

Método:

ARCHITECTURE CONTRACT
→ PLATFORM BASELINE ADAPTATION MATRIX
→ STANDALONE PLATFORM WORKFLOW
→ exact-SHA SUPERVISOR REVIEW
→ focused REWORK only if needed

Android es el primer exemplar.
iOS y Web se producen después de validar la arquitectura documental con Android.

## Arquitectura documental mínima

Antes de construir un platform workflow deben existir y estar revisados:
1. Workflow Document Contract.
2. Baseline Adaptation Matrix de la plataforma.
3. ADR de arquitectura documental cuando corresponda.

El platform workflow final debe poder consumirse sin reconstruir Issue #2.

## Principio de adaptación

MEJORA = BASELINE FUNCIONAL + ADAPTACIÓN JUSTIFICADA

Cada sección/subsección del baseline:
PRESERVE / ADAPT / EXTEND / NOT_APPLICABLE_WITH_JUSTIFICATION.

No silent omission.
Lossless derivation is mandatory.

## Roles

### Human
Define intención, prioridades, decisiones materiales de producto/scope, credenciales/permisos, costes/proveedores y publicación de producto.

PUBLISH = HUMAN ACTION.

### Supervisor
- crea/delimita Work Items;
- define verificación;
- revisa evidencia y exact HEAD;
- emite SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE;
- verifica MERGE_ELIGIBLE separadamente;
- no convierte CI/test PASS en aprobación.

### Implementer / Technical Researcher
- recupera contexto acotado;
- ejecuta sólo scope autorizado;
- implementa/verifica/revisa diff;
- persiste commit/PR/evidencia/handoff cuando esté autorizado;
- no se autoaprueba;
- no expande scope/authority;
- se detiene ante mismatch material.

### External actor
Opcional y acotado por capability.
Cada invocación persiste actividad GitHub durable:
request → authority → execution → evidence → result → stop/escalation.

TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.

### GitHub / CI
Sistemas de persistencia/evidencia.
No autoridad semántica.

## Source precedence

1. current Work Item Human/Supervisor authority;
2. frozen functional baseline;
3. accepted Issue #2 Common Core/non-regression;
4. accepted Issue #2 platform evidence/deltas;
5. summaries.

A summary cannot weaken normative behavior.

## Research / freshness

Issue #2 is the accepted evidence library.

Do not repeat broad comparative research during operationalization.

Fresh research occurs only for a concrete current material fact when accepted evidence may be stale.

Prefer official/primary sources.
Persist strategic rationale for material choices.
Scores/metrics remain evidence, not approval.

## Platform production loop

For each platform after architecture approval:

1. BUILD
- one bounded persistent task;
- complete standalone workflow;
- handoff;
- STOP.

2. SUPERVISOR REVIEW
- independent exact-SHA/content review;
- PASS closes/accepts when authorized;
- otherwise one focused REWORK.

3. OPTIONAL THIRD PASS
- only unresolved defects;
- architecture defect returns to architecture review instead of being patched independently per platform.

Normal expectation: BUILD + REVIEW, with REWORK only when evidence requires it.

## Definition of Done

A platform workflow is complete only if it passes:
- 100% baseline coverage;
- standalone operation;
- complete Human→Work Item→Implementer→verification→handoff→review→REWORK/HOLD/ESCALATE→integration→publication-boundary lifecycle;
- role/authority safety;
- exact-SHA review semantics;
- recovery for Implementer and Supervisor;
- external-actor durability;
- research/freshness gate;
- platform-specific build/test/device/browser/signing/distribution semantics;
- executable templates/checklists;
- accepted-evidence provenance;
- HARD VETO non-regression;
- summary-regression test.

## Historical methodology — retained, not mandatory

Candidate 1–4/scoring/sensitivity methodology remains valid provenance for Issue #2.

It can be reactivated only by a later explicit Work Item when genuinely new comparative research is needed.

It is not the default production cycle for Issue #8.

## Current delivery order

1. Architecture adoption package.
2. Android standalone workflow.
3. Architecture-conformance check.
4. iOS standalone workflow.
5. Web standalone workflow.

Each platform completes/accepts before moving to the next unless Supervisor/Human explicitly changes the sequence.

## Authority boundaries

SEMANTIC_ACCEPTED != MERGE_ELIGIBLE.
PATH PERMISSION != SEMANTIC PERMISSION.
CI/TEST PASS != SEMANTIC_ACCEPTED.
TECHNICAL CAPABILITY != WORKFLOW AUTHORITY.
PUBLISH = HUMAN ACTION.

Merge, canonical adoption and product publication require the governing authority; technical completion alone never grants them.
