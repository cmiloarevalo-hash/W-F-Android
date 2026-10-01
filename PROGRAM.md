# Program — Android / iOS / Web Operational Workflows

## Purpose

This repository develops and maintains standalone operational workflows for engineering work on:

- Android;
- iOS;
- Web.

The current product form is the consolidated workflow package under `workflows/`.

Historical comparative research established the evidence and architecture used to build these workflows. That research remains provenance; it is no longer the normal operating procedure for product/application work.

## Entry point

Read:

- `workflows/README.md`

Then select the applicable platform workflow.

For normal project work, the effective operating set is:

`ACTIVE WORK ITEM + PLATFORM WORKFLOW + CURRENT PROJECT/PRODUCT SPECIFICATIONS`

For Android Unity/Game:

`ACTIVE WORK ITEM + ANDROID_WORKFLOW + ANDROID_UNITY_GAME_PROFILE + CURRENT PROJECT/GAME SPECIFICATIONS`

## Package contents

- `workflows/WORKFLOW_DOCUMENT_CONTRACT.md`
- `workflows/ANDROID_WORKFLOW.md`
- `workflows/ANDROID_UNITY_GAME_PROFILE.md`
- `workflows/IOS_WORKFLOW.md`
- `workflows/WEB_WORKFLOW.md`
- `workflows/README.md`

The Contract governs workflow-document maintenance. Platform workflows remain standalone for normal platform execution.

## Extension model

Platform-specific reusable operational needs may be represented as bounded subordinate profiles only when the governing workflow defines an extension mechanism and the candidate passes that mechanism.

Android currently validates this model with Unity/Game.

A new technology does not automatically become a profile. The Supervisor first classifies it as one of:
- project specification;
- workflow improvement;
- profile candidate;
- research required;
- not required.

Any authorized workflow/profile change proceeds through a bounded `WORKFLOW_CHANGE_UNIT`.

## Maintenance

Each platform workflow maintains a source/freshness model.

A due freshness check is targeted and lightweight.

`14 DAYS → FRESHNESS CHECK, NOT AUTOMATIC FULL RESEARCH`

Research begins only when a material technical unknown requires it under current authority.

Workflow improvements never self-authorize.

## Governance

Human:
- owns product intent and reserved Human decisions;
- authorizes material workflow adoption/change when required;
- performs product publication.

Supervisor:
- scopes Work Items;
- reviews exact SHA;
- issues `SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE`;
- keeps merge eligibility separate.

Implementer:
- executes only authorized bounded work;
- verifies and hands off;
- does not self-approve, merge by inference, or publish.

## Historical program

Issue #2 contains the completed comparative research/design workpack.

Issue #8 contains the operationalization, platform workflow development, maintenance improvements, Android Unity/Game profile work, and final-package preparation.

These histories remain available for provenance and audit. A fresh normal session should not need to replay them.

## Completion boundary

A package candidate is complete when:
- all package files are present and internally consistent;
- root entry points route correctly;
- platform workflows preserve their accepted invariants;
- package-path changes are reviewed at exact SHA;
- no provenance-only artifact is required for normal execution.

Canonical adoption, merge, and any downstream publication remain separate authorized decisions.
