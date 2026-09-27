# TASK 01 — Research method

Status: EXPERIMENTAL METHODOLOGY — NOT CANONICAL  
Work Item: Issue #2  
Scope: cross-platform workflow research only

## 1. Purpose

This document fixes the evidence method for TASK 02–TASK 10 before any candidate is scored. It does not select a platform workflow or modify the frozen baseline.

## 2. Evidence classes

Every material statement used later MUST be classified as exactly one of:

| Class | Meaning | Minimum evidence |
|---|---|---|
| PROJECT_FACT | Fact established by Issue #2, Workpack files, repository state, or frozen reference metadata | Direct repository/Issue citation |
| EXTERNAL_FACT | Current capability, requirement, limit, price, policy, compatibility, or practice outside this repository | Current primary/official source when available |
| EMPIRICAL_OBSERVATION | Result actually measured in a test, CI run, benchmark, repository experiment, or reproducible execution | Procedure + environment + date + raw result/reference |
| EXTERNAL_STATISTIC | Quantitative value published by an external source | Source, population/scope, date, units, and limitations |
| ANALYTICAL_SCORE | 0–5 judgment produced by the scoring rubric in this Workpack | Criterion definition + evidence + rationale |
| INFERENCE | Reasoned conclusion that is not directly stated by a source | Supporting facts + explicit inference label |
| RECOMMENDATION | Proposed design choice | Evidence/inference basis + trade-offs |
| UNKNOWN | Material fact that could not be verified | What was checked + why unresolved |

Rules:
- ANALYTICAL_SCORE is never called a statistic, measurement, benchmark, or empirical result.
- UNKNOWN is never silently converted to 0, 3, or another neutral-looking number.
- Absence of documentation is not proof that a capability does not exist.
- Community reports may establish that an experience/problem was reported; they do not by themselves establish current platform capability, security, pricing, or policy.

## 3. Source hierarchy

For changeable technical claims, use this order unless a documented reason requires otherwise:

1. Official platform/vendor documentation, standards, release notes, security documentation, source repositories owned by the project/vendor.
2. Primary project artifacts in this repository and its authorized read-only historical source.
3. Official engineering articles and reference implementations.
4. Maintainer discussions/issues with identifiable version/context.
5. High-quality engineering write-ups with reproducible detail.
6. Community discussion (GitHub Discussions/Issues, Stack Overflow, Hacker News, technical Reddit/forums) as complementary operational evidence.

For conflicts:
- Prefer the source that is both more authoritative for the claim and more current for the relevant version.
- Record disagreement instead of averaging incompatible claims.
- If the conflict is material and cannot be resolved within the active task, trigger the Workpack STOP condition.

## 4. Freshness policy

At the time a claim is used:
- Record access date.
- Record product/tool/version/date scope when material.
- Re-check claims that can change quickly: prices, supported versions, distribution rules, CI/runtime availability, hosted sandbox capabilities, security controls, model/tool behavior, quotas and policies.
- A source from an earlier task may be reused only if its claim remains current enough for the later decision.
- TASK 09 must explicitly audit source freshness.

No fixed "days old" threshold is imposed across all sources because stability differs by topic. Instead, freshness is risk-based:
- HIGH volatility: re-check in the task where used.
- MEDIUM volatility: re-check if a later release/policy change is plausible.
- LOW volatility: standards/stable conceptual documentation may be reused with date/version scope.

## 5. Research procedure per later task

1. Reconstruct only the required project context from GitHub.
2. Identify the decision questions and material claims before searching.
3. Gather primary/official sources first.
4. Add international community evidence only where it can reveal operational friction, counterexamples, or missing assumptions.
5. Build a claim ledger with evidence class, source, date/version scope, confidence, and unresolved uncertainty.
6. Generate candidates only after the evidence gate is adequate.
7. Evaluate candidates using the fixed scoring model.
8. Run sensitivity analysis.
9. Separate measured results from published statistics and analytical scores.
10. Run verification and scope checks before persisting the checkpoint.

## 6. Claim ledger schema

Later evidence files SHOULD use:

| Field | Required content |
|---|---|
| Claim ID | Stable local identifier |
| Claim | Atomic statement |
| Class | One evidence class from §2 |
| Platform/scope | Android / iOS / Web / cross-platform |
| Version/date scope | What versions/timeframe the claim covers |
| Source | URL or repository path/Issue |
| Source type | Primary / official engineering / maintainer / community |
| Accessed | YYYY-MM-DD |
| Confidence | HIGH / MEDIUM / LOW, with reason when not HIGH |
| Contradictions | Conflicting evidence or NONE |
| Used by | Candidate/criterion/decision |
| Notes | Limitations and caveats |

## 7. Current OpenAI practice incorporated into the method

Verified current OpenAI guidance used to shape this method:

- Structured, well-scoped tasks and Issue-like prompts improve agent grounding; persistent AGENTS.md context and multiple-solution exploration can be useful.
  Source: https://openai.com/business/guides-and-resources/how-openai-uses-codex/
- Sandboxing defines technical execution boundaries; approval policy governs higher-risk actions; agent-native telemetry improves auditability.
  Source: https://openai.com/index/running-codex-safely/
- Long-horizon work benefits from durable project memory, milestone acceptance criteria, scoped diffs, and verification after milestones.
  Source: https://developers.openai.com/blog/run-long-horizon-tasks-with-codex
- Persistent Goals encode desired outcomes, completion conditions, checks, and constraints for multi-step work.
  Source: https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex
- Issue/task trackers can act as a control plane for agent work, with workflow-defined human-review handoff states.
  Source: https://openai.com/index/open-source-codex-orchestration-symphony/
- Managed agents distinguish durable session/orchestration from the application-selected tools and execution environment.
  Source: https://developers.openai.com/api/docs/guides/agents
- Current September 2026 guidance warns against accumulated/stale instruction bloat and recommends contextual, task-relevant repository instructions.
  Source: https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra

These are EXTERNAL_FACTS about published OpenAI guidance, not proof that a particular candidate is superior.

## 8. Verification gate

Before a later task is marked complete:
- Every material current-state claim is sourced or explicitly marked INFERENCE/UNKNOWN.
- Numerical claims state whether they are EMPIRICAL_OBSERVATION, EXTERNAL_STATISTIC, or ANALYTICAL_SCORE.
- No analytical score is presented as a measured or externally published statistic.
- Any candidate violating an invariant is flagged before weighted comparison.
- Unresolved material contradictions are surfaced, not hidden in an average score.

## 9. Limitations

This method does not guarantee that all future platform facts remain current. It defines how freshness, uncertainty, contradictions and scoring must be handled when those facts are gathered.


## 10. Baseline functional non-regression method

TASK 01 treats the frozen baseline as a read-only functional reference. Research may propose different platform-specific mechanisms, but candidate generation and comparison MUST preserve the baseline's proven control functions unless a Human explicitly authorizes a semantic change.

### 10.1 Work Item contract gate

Before technical research is treated as candidate-ready, verify that the governing Work Item supplies or explicitly resolves:

1. Objective;
2. Acceptance Criteria;
3. Authorized Scope;
4. Relevant Sources;
5. Verification;
6. Base.

Authorized Scope MUST be interpreted as two independent dimensions:

- Semantic Scope: what behavior/change is authorized;
- Path Scope: where changes may be made.

Path Scope alone never authorizes a semantic change.

### 10.2 Baseline-preservation ledger

Every later candidate review MUST include a baseline-preservation ledger with one row per protected baseline function and exactly one status:

- `PRESERVED AS-IS`;
- `PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION`;
- `NOT APPLICABLE` + justification.

Minimum protected functions are those mapped in `outputs/01/invariants.md` I-21 through I-29:
- Work Item contract;
- Semantic Scope + Path Scope;
- exact-SHA semantic review;
- SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE;
- same-objective REWORK continuity in the same Issue/branch/PR;
- Supervisor-only merge after exact-SHA semantic acceptance and merge-eligibility checks where merge is authorized;
- `PUBLISH = HUMAN ACTION`;
- GitHub-based session recovery;
- the non-regression gate itself.

A candidate may implement a function differently on Android, iOS, or Web, but the mapping must explain how the same functional guarantee is retained.

### 10.3 SHA-bound review discipline

Review evidence MUST record:
- exact reviewed commit SHA;
- applicable PR/branch;
- Supervisor decision for that SHA.

A later commit invalidates semantic acceptance for the new HEAD until the Supervisor reviews that new SHA. CI or test evidence may remain reusable as evidence when still applicable, but it does not transfer semantic acceptance.

### 10.4 Review state machine

The semantic state machine is independent of automated verification:

`SEMANTIC_ACCEPTED | REWORK | HOLD | ESCALATE`

Interpretation:
- SEMANTIC_ACCEPTED: the exact reviewed SHA satisfies the Work Item semantically; this is not automatically merge eligibility.
- REWORK: correct within the same objective, normally continuing in the same Issue/branch/PR.
- HOLD: do not continue the affected work until the hold is released.
- ESCALATE: Human/Supervisor decision is required because authority/scope/baseline/material assumptions exceed the current Work Item.

### 10.5 Merge and publication boundaries

Where integration is authorized by the governing Work Item/Human decision:
- Implementer never self-merges;
- Supervisor merge requires exact-SHA semantic acceptance plus baseline merge-eligibility checks.

Publication remains a separate authority boundary:

`PUBLISH = HUMAN ACTION`

Technical build/sign/upload/deploy capability is evidence/capability, not publication authority.

### 10.6 REWORK continuity

When the objective is unchanged, corrections remain in the same Issue/branch/PR by default so that evidence and review history stay continuous.

If the required correction changes Objective, Semantic Scope, Path Scope, authority, baseline semantics, provider/billing/credentials beyond existing authority, or other material contract elements, do not silently stretch the original Work Item: escalate.

### 10.7 Session recovery verification

At every significant handoff, verify that a new authorized Supervisor/Implementer can reconstruct from GitHub:
- Work Item and contract;
- branch/ref and exact HEAD;
- PR if present;
- current state/checkpoints;
- latest applicable Supervisor decision + reviewed SHA;
- evidence and unresolved blockers.

The previous chat transcript is never required as authoritative continuity.

### 10.8 Non-regression gate before scoring

Before any numeric comparison:

1. complete the baseline-preservation ledger;
2. inspect every `PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION` explanation;
3. inspect every `NOT APPLICABLE` justification;
4. flag any unexplained weakening as HARD VETO;
5. only candidates that pass the gate may proceed to weighted scoring.

This gate is logically prior to scoring. It is not another weighted criterion.

## 11. TASK 01 non-regression verification

Baseline correspondence checked against the frozen reference:
- Work Item contract → I-21;
- dual Semantic/Path Scope → I-22;
- exact-SHA review → I-23;
- review state machine → I-24;
- REWORK continuity → I-25;
- merge authority/eligibility → I-26;
- human publication authority → I-27;
- GitHub session recovery → I-28;
- functional non-regression gate → I-29.

Verification result for this methodology correction:
- baseline functionality removed: NO;
- baseline functionality reinterpreted into weaker authority: NO;
- platform-specific implementation allowed only where the function remains equivalent: YES;
- frozen baseline modified: NO;
- TASK 01 remains methodology/evaluation only: YES.
