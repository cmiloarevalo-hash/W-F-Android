# Programa de diseño comparativo de workflows — Android, iOS y Web

## Propósito

Este repositorio contiene un programa persistente para diseñar y contrastar tres workflows de ingeniería asistida por agentes:

- Android;
- iPhone / iOS;
- Aplicaciones web.

La ejecución debe sobrevivir cambios de sesión y agotamiento de contexto mediante Issues, comentarios, documentos y evidencia en GitHub.

## Roles

### Humano
Define intención, prioridades, límites, permisos, costes aceptables y decisiones excepcionales.

### Supervisor
Chat Web GPT.

Responsabilidades:

- crear/delimitar Work Items;
- revisar evidencia;
- contrastar investigación material;
- revisar comparaciones y scores;
- detectar sobreingeniería, sesgo o conclusiones sin evidencia;
- emitir REWORK / HOLD / ESCALATE / SEMANTIC_ACCEPTED cuando corresponda;
- decidir si una propuesta está lista para presentación.

### Agente implementador / investigador
Ejecuta la investigación y producción de candidatos.

No ejerce autoridad de Supervisor.

### Actor externo opcional
No existe uno obligatorio.

Un workflow puede reservar un punto de extensión para un actor adicional únicamente cuando haya una función verificable que no convenga asignar al Implementador/Supervisor/CI.

Debe documentarse:

- capability;
- preconditions;
- permissions;
- forbidden actions;
- evidence returned;
- stop conditions;
- escalation path.

## Modelo de trabajo

Cada plataforma pasa por seis etapas:

1. Research Gate.
2. Candidate 1.
3. Candidate 2.
4. Candidate 3.
5. Comparative evaluation.
6. Candidate 4 — propuesta de presentación.

Cada etapa produce un comentario/checkpoint persistente.

## Fuentes

### Primera prioridad
- OpenAI Developers / OpenAI Engineering para prácticas de coding agents.
- Documentación oficial de la plataforma:
  - Android Developers / Google Play para Android.
  - Apple Developer para iOS.
  - estándares web y documentación oficial de frameworks/herramientas seleccionadas para Web.
- GitHub Docs para CI, Actions, repositorios, permisos y branch protections.
- documentación oficial de lenguajes/build systems.

### Segunda prioridad
Comunidad técnica internacional:
- GitHub Issues/Discussions de proyectos oficiales;
- Stack Overflow;
- Hacker News;
- Reddit técnico especializado;
- foros oficiales de proveedores;
- ingeniería publicada por compañías con implementación verificable.

La comunidad sirve para descubrir problemas reales, experiencia operacional y puntos de fricción. Las afirmaciones de capacidad, seguridad, compatibilidad, precio o requisitos deben contrastarse con fuentes primarias cuando existan.

## Evidencia cuantitativa y scoring

No llamar “estadística” a una opinión numérica.

La evaluación puede contener tres clases distintas:

1. **Datos observados**: medidas obtenidas realmente en pruebas/repo/CI.
2. **Datos externos**: cifras publicadas por fuentes verificables.
3. **Score analítico**: valoración construida por el agente con una rúbrica explícita.

Para Candidate 1–3:

- definir criterios y pesos antes de la puntuación;
- usar escala común;
- justificar cada valor;
- separar datos reales de scores analíticos;
- hacer análisis de sensibilidad;
- no elegir Candidate 4 sólo por promedio ponderado.

## Entregables por plataforma

- mapa de recomendaciones oficiales;
- mapa de recomendaciones OpenAI;
- hallazgos de comunidad;
- Candidate 1;
- Candidate 2;
- Candidate 3;
- tabla comparativa;
- evidencia cuantitativa disponible;
- score analítico;
- riesgos;
- análisis de sensibilidad;
- Candidate 4;
- preguntas para Supervisor/Humano.

## Entregable transversal

Después de completar Android, iOS y Web:

- identificar un núcleo común de gobierno;
- identificar diferencias inevitables por plataforma;
- comparar mecanismos de sandbox/CI/test/release;
- proponer una interfaz común para actores externos opcionales;
- verificar que no se fuerce una abstracción artificial entre plataformas;
- producir un paquete de presentación con los tres Candidate 4.

## Condición de finalización

El programa termina cuando:

- las tres actividades de plataforma están `READY_FOR_SUPERVISOR_REVIEW`;
- la síntesis transversal está completa;
- todas las afirmaciones actuales materialmente importantes tienen fuente;
- los scores están claramente diferenciados de estadísticas empíricas;
- el agente ha persistido el handoff final en GitHub.

La respuesta en chat no sustituye estos artefactos.
