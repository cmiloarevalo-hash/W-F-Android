# ADR-001 — Standalone baseline-derived platform workflows

STATUS: PROPOSED — NOT CANONICAL
GOVERNING WORK ITEM: Issue #8
DECISION AUTHORITY IN PRINCIPLE: Supervisor comment 5882543491
IMPLEMENTATION AUTHORITY: comment 5882550265

## Context

Issue #2 produced accepted cross-platform research and proposals, but the final platform artifacts were too compressed to operate as standalone engineering workflows.

The failure mode was architectural: semantic preservation alone did not guarantee preservation of the full operational lifecycle.

## Decision

Platform workflows shall be standalone operational adaptations of the functional baseline.

They shall be produced using:
1. one shared Workflow Document Contract;
2. one section-by-section baseline adaptation matrix per platform;
3. one standalone platform workflow per platform.

Additional decisions:
- Android is the first exemplar of document architecture, not platform mechanics.
- Accepted Issue #2 research is reused as evidence; broad Candidate/scoring research is not repeated absent a concrete freshness trigger.
- Normal platform closure is BUILD → independent exact-SHA review → focused same-objective REWORK only if needed.
- Normative derivation must be lossless: summaries may not weaken or omit normative behavior.
- Source precedence is explicit: current Work Item authority → functional baseline → accepted Common Core → accepted platform evidence → summaries.
- Platform workflows may intentionally duplicate critical governance to remain standalone.

## Alternatives considered

### A. Short platform proposal + links to research
Rejected. This reproduces the Issue #2 failure mode: research remains correct while the operational product is incomplete.

### B. One monolithic cross-platform workflow
Rejected. It increases forced-symmetry risk and obscures platform-specific build, verification, signing and distribution mechanics.

### C. Shared Common Core + thin platform wrappers
Rejected as the primary operational architecture. It reduces duplication but violates standalone consumption by requiring document hopping.

### D. Three standalone workflows from one shared contract + per-platform matrices
Accepted. It preserves standalone use, explicit baseline coverage and platform-specific mechanics.

### E. Copy the baseline three times and edit ad hoc
Rejected. It preserves volume but lacks explicit adaptation justification, provenance and architecture control.

## Scope

This ADR records:
- standalone platform workflow product shape;
- shared document contract;
- per-platform baseline matrices;
- Android-first exemplar sequence;
- accepted-evidence reuse;
- short BUILD/review/REWORK loop;
- lossless normative derivation;
- source precedence.

## Consequences

Positive:
- operational completeness is testable;
- baseline loss becomes visible;
- authority boundaries survive summarization;
- session recovery improves;
- later platform cycles become shorter;
- Issue #2 research is reused efficiently.

Costs:
- platform documents intentionally duplicate some governance;
- platform workflows are longer than the prior proposals;
- architecture changes may require coordinated platform updates;
- baseline coverage review is stricter before implementation.

## Outside this ADR

This ADR does not define:
- actual ANDROID_WORKFLOW.md / IOS_WORKFLOW.md / WEB_WORKFLOW.md content;
- volatile SDK/toolchain/store/provider facts;
- credentials, accounts or costs;
- project-specific device/browser matrices;
- individual Work Item scope;
- current external research evidence;
- semantic acceptance of a platform workflow;
- merge authority;
- canonical adoption;
- product publication authority;
- changes to the frozen functional baseline.

PUBLISH = HUMAN ACTION remains governed by the Workflow; this ADR does not alter it.
