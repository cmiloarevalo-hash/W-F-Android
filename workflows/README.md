# Workflow Package — Entry Point

STATUS: PACKAGE CANDIDATE — NOT CANONICAL

GOVERNING WORK ITEM: Issue #8

This directory is the cold-start entry point for the consolidated Android / iOS / Web operational workflow package.

The package is designed so a fresh authorized agent can determine how to work from the repository + active Work Item + applicable platform workflow + current project specifications, without reconstructing Issue #2 or Issue #8 history.

## 1. Select the applicable workflow

### Android

Read:

1. `workflows/ANDROID_WORKFLOW.md`
2. the active Work Item;
3. current project/product engineering specifications.

If the Work Item materially targets Unity/Game on Android, additionally read:

- `workflows/ANDROID_UNITY_GAME_PROFILE.md`

The Unity/Game profile extends Android. It does not replace Android and does not create new authority.

Future Android specializations must enter through the profile-extension governance defined by `ANDROID_WORKFLOW.md`. A new engine, toolchain, or project class is not automatically a profile merely because it is different.

### iOS

Read:

1. `workflows/IOS_WORKFLOW.md`
2. the active Work Item;
3. current project/product engineering specifications.

### Web

Read:

1. `workflows/WEB_WORKFLOW.md`
2. the active Work Item;
3. current project/product engineering specifications.

## 2. Workflow maintenance

For changing or maintaining the workflows themselves, also read:

- `workflows/WORKFLOW_DOCUMENT_CONTRACT.md`

Normal product/application implementation does not require reading the Contract unless the Work Item makes it material.

Workflow maintenance uses the registered-source / freshness / Human-authorized `WORKFLOW_CHANGE_UNIT` mechanism defined by the Contract and platform workflows.

## 3. Package source lock

This candidate was assembled from semantically accepted development artifacts at these exact source heads:

| Artifact | Accepted source |
|---|---|
| Workflow Document Contract | `014afbffbda466cc62511eb073689994ca82610d` |
| Android Workflow | `d6f68bee8e37545998d3bfea6dabd4ae63c83cae` |
| Android Unity/Game Profile | `d6f68bee8e37545998d3bfea6dabd4ae63c83cae` |
| iOS Workflow | `6bf6177ad1a32aa33773a306ece123f3145f62d0` |
| Web Workflow | `3870f38bb63cce97d90f950d6e2e8790817d9067` |

The package copy preserves accepted semantics. Package-path references may differ from development workpack paths.

## 4. Authority and status

This package candidate does not create authority by existing.

Always reconstruct current authority from GitHub.

Core invariants:

- `GITHUB STATE > SESSION MEMORY`
- `TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`
- `PATH PERMISSION != SEMANTIC PERMISSION`
- `CI/TEST PASS != SEMANTIC_ACCEPTED`
- `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`
- `PUBLISH = HUMAN ACTION`
- `WORKFLOW IMPROVEMENT CANDIDATE != WORKFLOW CHANGE AUTHORITY`

Formal Supervisor semantic decisions remain only:

- `SEMANTIC_ACCEPTED`
- `REWORK`
- `HOLD`
- `ESCALATE`

Until a separate Human/Supervisor adoption decision and authorized integration occurs:

`PACKAGE CANDIDATE != CANONICAL PACKAGE`

## 5. Provenance boundary

The following are development/provenance evidence, not normal cold-start procedure:

- frozen baseline comparison material;
- baseline adaptation matrices;
- ADR-001;
- Issue #2 candidate/research outputs;
- Issue #8 development activities and handoffs;
- observability research;
- model-fit research;
- Supervisor chat recovery artifacts.

Consult them only when the active Work Item, maintenance investigation, audit, or provenance question makes them material.

Direct access to the applicable operational workflow is preferred over reconstructing development history.
