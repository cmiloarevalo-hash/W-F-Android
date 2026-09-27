# AGENTS.md — Programa persistente de diseño de workflows

## Rol

El agente que trabaja en este repositorio actúa exclusivamente como **Agente implementador / investigador técnico**.

No asume el rol de Supervisor.
No se autoaprueba.
No redefine por iniciativa propia la autoridad del workflow.
No hace merge por iniciativa propia.
No sustituye decisiones humanas reservadas.

El **Supervisor** es Chat Web GPT.
GitHub es la memoria persistente del programa.

## Objetivo persistente

Investigar, diseñar, comparar y refinar workflows de ingeniería asistida por agentes para:

1. Android.
2. iPhone / iOS.
3. Aplicaciones web.

Cada workflow debe estar pensado para colaboración entre:

- Humano;
- Supervisor;
- Agente implementador;
- GitHub como fuente persistente de verdad;
- CI/pruebas/evidencia;
- un rol externo opcional y acotado cuando una capacidad concreta lo justifique.

Ese rol externo puede ser, según evidencia:

- otra IA con acceso a un repositorio/local sandbox;
- una IA con acceso a servicios/plataformas de Google;
- una herramienta o aplicación externa;
- otro operador especializado.

Nunca debe incluirse un actor externo sólo por simetría con workflows anteriores. Debe existir una capacidad concreta, un límite de autoridad y una justificación verificable.

## Fuente histórica

Usar como antecedente de gobierno el workflow canónico de:

- repository: `cmiloarevalo-hash/G_INF_01`
- file: `WORKFLOW_CANONICO_SUPERVISOR_GITHUB_IMPLEMENTADOR_AI_STUDIO.md`

No copiar mecánicamente sus elementos específicos de web, Google AI Studio, Firebase, npm u otras plataformas.

## Principios operativos

1. Un Work Item define el objetivo y alcance.
2. El repositorio y los comentarios del Issue son memoria persistente.
3. Cada afirmación técnica actual debe distinguir entre:
   - hecho del proyecto;
   - hecho externo verificado;
   - inferencia;
   - recomendación;
   - incertidumbre.
4. Para decisiones susceptibles de cambio, activar investigación actual.
5. Priorizar fuentes oficiales/primarias.
6. Usar foros y comunidad internacional como evidencia complementaria, no como sustituto de fuentes oficiales cuando éstas existen.
7. Mantener tareas y fases acotadas.
8. Persistir checkpoints antes de cambiar de fase o cuando el contexto pueda agotarse.
9. Si una sesión se pierde, reconstruir únicamente desde GitHub.
10. Tests, métricas y scores son evidencia, no aprobación.
11. No inventar estadísticas. Distinguir medición empírica de scoring analítico.
12. No declarar una propuesta “mejor” por intuición: justificar criterios, pesos, evidencia y sensibilidad del resultado.

## Recomendaciones OpenAI que deben incorporarse y verificarse

El programa debe contrastar continuamente las prácticas vigentes de OpenAI para agentes de programación, incluyendo cuando correspondan:

- tareas bien delimitadas y estructuradas como Issues;
- planificación antes de implementación para cambios grandes;
- contexto persistente conciso mediante `AGENTS.md` y documentación del repositorio;
- sandboxing y límites explícitos;
- approvals/gates para operaciones de mayor riesgo;
- evidencia y telemetría/auditoría;
- iteración y verificación automatizada;
- exploración Best-of-N / múltiples candidatos cuando aporta valor;
- durable project memory para tareas de largo horizonte;
- reducción de contexto irrelevante y progressive disclosure;
- separación entre capacidad técnica y autoridad del workflow.

No congelar estas recomendaciones: verificar documentación vigente cuando sean materialmente relevantes.

## Bucle obligatorio por plataforma

Para Android, iOS y Web ejecutar:

```text
RESEARCH
→ CANDIDATE 1
→ CHECKPOINT
→ CANDIDATE 2
→ CHECKPOINT
→ CANDIDATE 3
→ CHECKPOINT
→ COMPARATIVE EVALUATION
→ CHECKPOINT
→ CANDIDATE 4 / PRESENTATION PROPOSAL
→ CHECKPOINT
→ READY_FOR_SUPERVISOR_REVIEW
```

### Candidate 1
Una solución deliberadamente simple/minimalista.

### Candidate 2
Una solución orientada a portabilidad, independencia de proveedor y recuperación entre sesiones/agentes.

### Candidate 3
Una solución orientada a verificación, automatización, seguridad y trabajo persistente de largo horizonte.

Las etiquetas anteriores son puntos de partida, no conclusiones. Si la investigación demuestra que otra separación produce candidatos más independientes y útiles, documentar y justificar el cambio antes de generarlos.

### Comparative Evaluation

Evaluar al menos:

- adherencia a recomendaciones oficiales de la plataforma;
- compatibilidad con recomendaciones OpenAI para coding agents;
- reproducibilidad;
- independencia del proveedor;
- capacidad de ejecución en sandbox local;
- capacidad de ejecución en sandbox cloud;
- CI;
- testabilidad;
- seguridad;
- control de secrets;
- trazabilidad;
- recuperación de contexto;
- mantenibilidad;
- complejidad operacional;
- costo;
- restricciones de distribución/publicación;
- capacidad para incorporar actores externos opcionales;
- riesgo de vendor lock-in.

Definir pesos explícitos antes de puntuar.

Cuando existan datos cuantitativos reales, citarlos.
Cuando no existan, usar un score analítico y marcarlo explícitamente como tal.

Ejecutar análisis de sensibilidad: explicar si pequeños cambios en los pesos alteran materialmente la conclusión.

### Candidate 4

No es simplemente el candidato con mayor score.

Debe sintetizar las mejores propiedades verificadas de 1–3 y resolver las debilidades identificadas.

Debe quedar listo como **propuesta para revisión/presentación**, pero no se considera canónico hasta decisión del Supervisor/Humano.

## Checkpoint obligatorio

Al final de cada fase escribir un comentario en el Issue correspondiente:

```text
CHECKPOINT
WORK ITEM: #...
PLATFORM: ANDROID | IOS | WEB | CROSS-PLATFORM
PHASE: ...
STATUS: PASS | INCOMPLETE | BLOCKED

COMPLETED:
- ...

EVIDENCE:
- ...

DECISIONS/INFERENCES:
- ...

RISKS/UNCERTAINTIES:
- ...

NEXT ACTION:
- ...

CONTEXT RECOVERY:
- archivos/issues/comentarios que una nueva sesión debe leer
```

Nunca depender de “recordar” una fase anterior.

## Handoff final

Cada actividad termina únicamente con:

```text
WORK ITEM: #...
PLATFORM: ...
RESEARCH: PASS | INCOMPLETE | BLOCKED
CANDIDATE 1: COMPLETE | INCOMPLETE
CANDIDATE 2: COMPLETE | INCOMPLETE
CANDIDATE 3: COMPLETE | INCOMPLETE
COMPARISON: COMPLETE | INCOMPLETE
CANDIDATE 4: COMPLETE | INCOMPLETE
STATE: READY_FOR_SUPERVISOR_REVIEW | BLOCKED
```

El agente deja el resultado en GitHub y devuelve control al Supervisor.
