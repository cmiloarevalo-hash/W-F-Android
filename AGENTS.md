# AGENTS.md — Operational Workflow Package Entry Point

## Current operating model

This repository contains the consolidated candidate package for operational engineering workflows:

- Android;
- iOS;
- Web;
- optional bounded platform profiles such as Android Unity/Game.

For normal work, do **not** reconstruct the historical Candidate 1–4 research cycle.

Start from:

1. the active GitHub Work Item / Issue;
2. `workflows/README.md`;
3. the applicable platform workflow;
4. current project/product specifications explicitly required by that workflow or Work Item.

GitHub is durable authority and memory. Chat/session memory is not authority.

## Role

Use only the role authorized by the active Work Item.

An Implementer MUST NOT:
- self-approve;
- expand Objective, Semantic Scope, or Path Scope;
- infer merge authority;
- infer publication authority;
- modify a workflow merely because an improvement appears useful.

A Supervisor independently reviews exact SHA and may issue only:
- `SEMANTIC_ACCEPTED`;
- `REWORK`;
- `HOLD`;
- `ESCALATE`.

## Platform selection

Android:
- `workflows/ANDROID_WORKFLOW.md`
- for Unity/Game Android work, additionally `workflows/ANDROID_UNITY_GAME_PROFILE.md` when explicitly activated.

iOS:
- `workflows/IOS_WORKFLOW.md`

Web:
- `workflows/WEB_WORKFLOW.md`

Workflow maintenance:
- also read `workflows/WORKFLOW_DOCUMENT_CONTRACT.md`.

## Core invariants

- `MEJORA = BASELINE FUNCIONAL + ADAPTACIÓN JUSTIFICADA`
- `GITHUB STATE > SESSION MEMORY`
- `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`
- `LOCAL CAPABILITY != WORKFLOW AUTHORITY` when a Local Execution Agent is used
- `PATH PERMISSION != SEMANTIC PERMISSION`
- `CI/TEST PASS != SEMANTIC_ACCEPTED`
- `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`
- `PUBLISH = HUMAN ACTION`
- `PERSISTENCE != BLIND START`
- `WORKFLOW IMPROVEMENT CANDIDATE != WORKFLOW CHANGE AUTHORITY`

## Workflow changes

A possible workflow improvement is not implementation authority.

Use the platform/Contract maintenance path:

`IMPROVEMENT_CANDIDATE → Human decision → bounded WORKFLOW_CHANGE_UNIT → implementation/research as authorized → exact-SHA Supervisor review`.

A new Android engine/toolchain specialization must first be classified. Project-specific behavior remains project specification; only reusable operational deltas justified as a subordinate profile enter Android profile governance.

## Baseline and provenance

`references/**` is frozen reference material.

`REFERENCES_WRITES = FORBIDDEN` unless a future explicit authority changes that repository rule.

Historical Issue #2/Issue #8 research, matrices, ADRs, reports, and handoffs are provenance/evidence. They are not normal execution dependencies.

## Package status

The files under `workflows/` on the final-package candidate branch remain a candidate until a separate authorized canonical-adoption/integration decision is persisted.

Package existence or semantic acceptance does not itself authorize merge or canonical adoption.
