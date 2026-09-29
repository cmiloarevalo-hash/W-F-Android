# TASK 01 — Scoring model and sensitivity method

Status: EXPERIMENTAL ANALYTICAL RUBRIC — NOT A STATISTICAL MODEL  
Authority: Issue #2

## 1. Scale

Each criterion is scored 0–5 only when evidence is sufficient.

| Score | Anchor |
|---:|---|
| 0 | Verified contradiction, unsupported critical capability, or unacceptable failure for this criterion |
| 1 | Major gaps; substantial manual/risky workaround required |
| 2 | Partial/fragile support; important limitations remain |
| 3 | Adequate for intended use with manageable limitations |
| 4 | Strong support with good evidence and limited material gaps |
| 5 | Very strong support with direct evidence, robust controls and no material unresolved gap for the criterion |
| NE | Not evidenced sufficiently to assign a numeric score |

Rules:
- 0 means verified poor performance/absence, not "unknown".
- NE is excluded from the point estimate and must be visible.
- A candidate with a hard-veto invariant violation is not eligible for ranking regardless of numeric total.

## 2. Fixed criteria and weights

Weights sum to 100.

| ID | Criterion | Weight | What a high score means |
|---|---|---:|---|
| C01 | Official platform guidance adherence | 9 | Aligns with current first-party platform guidance and supported patterns |
| C02 | OpenAI coding-agent practice fit | 7 | Uses scoped tasks, durable context, bounded execution, verification and review effectively |
| C03 | Reproducibility | 7 | Another authorized agent/human can reconstruct and repeat the workflow |
| C04 | Testability / verification | 8 | Clear automated/manual checks tied to completion conditions |
| C05 | Security and secrets control | 9 | Least privilege, explicit write/network boundaries, safe secret handling, approvals |
| C06 | Traceability / auditability | 6 | Decisions, evidence, tool actions and checkpoints are reviewable |
| C07 | Context recovery / durability | 7 | Survives session/agent turnover without conversational memory |
| C08 | Maintainability | 6 | Rules/artifacts are understandable, updateable and resistant to drift |
| C09 | Operational simplicity | 6 | Low unnecessary ceremony and manageable operator burden |
| C10 | Provider independence / portability | 6 | Core workflow can move between compatible tools/providers with limited redesign |
| C11 | Local sandbox capability | 4 | Can support bounded local execution where platform permits |
| C12 | Cloud sandbox capability | 4 | Can support bounded remote/cloud execution where useful |
| C13 | CI integration | 6 | CI can enforce/record meaningful checks and evidence |
| C14 | Cost efficiency | 4 | Avoids unnecessary paid/runtime/tool cost for equivalent assurance |
| C15 | Distribution / release compliance | 4 | Handles platform publication/signing/release constraints explicitly |
| C16 | Optional external-actor extensibility | 3 | Can add a justified external actor with explicit capability/authority contract |
| C17 | Vendor lock-in risk | 4 | Avoids or clearly contains hard-to-exit proprietary dependencies |

## 3. Weighted score

For candidate c with numeric scores s(c,i):

`WeightedScore(c) = Σ(weight_i * score_i / 5)`

This yields 0–100 only when all criteria are evidenced.

If any criterion is NE:
- Report `EvidenceCoverage = Σ(weights with numeric score)`.
- Report a point score only over evidenced criteria as `ObservedWeighted = Σ(weight_i * score_i/5)`, clearly not normalized to 100.
- Report uncertainty bounds for missing criteria:
  - conservative lower bound: missing criteria = 0;
  - permissive upper bound: missing criteria = 5.
- Do not present a normalized "final score" until material evidence coverage is adequate.

Minimum evidence gate for comparative ranking:
- no hard-veto invariant violation;
- C01, C04, C05, C07 and C15 must be numeric (platform/release relevance permitting; if C15 is genuinely not applicable, justify N/A separately);
- EvidenceCoverage >= 90/100;
- all NE items are listed.

## 4. Evidence requirements per score

Every numeric score must include:
- criterion ID;
- numeric value;
- evidence references;
- 1–3 sentence rationale;
- material caveat/uncertainty;
- classification of quantitative inputs as EMPIRICAL_OBSERVATION, EXTERNAL_STATISTIC, or neither.

A score may use measured data, but the score itself remains ANALYTICAL_SCORE.

## 5. Sensitivity analysis

Run all applicable tests after baseline scoring.

### S1 — One-at-a-time weight perturbation
For each criterion:
- vary its weight by -20% and +20% relative;
- proportionally renormalize all other weights so the total remains 100;
- record whether candidate ordering changes.

### S2 — Priority scenarios
Evaluate at least three predeclared scenarios without changing score values:
- SECURITY/VERIFICATION: increase C04+C05+C06+C13 emphasis;
- PORTABILITY/DURABILITY: increase C03+C07+C10+C17 emphasis;
- SIMPLICITY/COST: increase C08+C09+C14 emphasis.

Scenario weights must be written before computing scenario results and must sum to 100.

### S3 — Score uncertainty
For every criterion whose confidence is MEDIUM/LOW, perturb the candidate score by ±1 within [0,5] and test plausible combinations around decision-critical criteria.

### S4 — Missing-evidence bounds
For every NE criterion, compute lower/upper bounds (0/5) until evidence is resolved. If bounds overlap enough to change the apparent ordering, the comparison is not stable.

## 6. Stability labels

These labels describe the analytical comparison only; they are not approval:

- ROBUST: no candidate ordering relevant to the recommendation changes under S1/S2, and plausible S3/S4 does not overturn the material conclusion.
- CONDITIONALLY_STABLE: ordering changes in some scenarios, but Candidate 4 synthesis remains supported by the same invariant-respecting strengths.
- SENSITIVE: small reasonable changes in weights/scores materially change the conclusion.
- INDETERMINATE: evidence gaps or contradictions prevent a defensible comparison.

## 7. Candidate 4 rule

Candidate 4 is not selected mechanically from the maximum WeightedScore.

It must:
1. satisfy all hard invariants;
2. use the comparison to identify justified strengths/weaknesses;
3. synthesize compatible strengths where evidence supports doing so;
4. address high-impact weaknesses;
5. state added complexity/cost introduced by synthesis;
6. remain a PROPOSAL — NOT CANONICAL.

## 8. Anti-gaming rules

- Criteria/weights are fixed by TASK 01 and cannot be silently changed after seeing candidate results.
- If later evidence shows a criterion definition is invalid, record the proposed change and its impact; do not rewrite history.
- Do not double-count the same fact across criteria without explaining why it affects distinct dimensions.
- Do not convert lack of evidence into a favorable assumption.
- Do not use decimal precision beyond what evidence justifies; default scores are integers.
- A weighted score cannot override a STOP condition, authority rule, baseline rule or hard invariant.

## 9. Verification for TASK 01

- Criteria defined: YES
- Weights explicit and sum to 100: YES
- Common scale defined: YES
- EMPIRICAL_OBSERVATION vs EXTERNAL_STATISTIC vs ANALYTICAL_SCORE separated: YES
- UNKNOWN/NE handling defined: YES
- Sensitivity method defined before candidate scoring: YES
- Candidate 4 not mechanically selected by mean: YES


## 10. Baseline functional non-regression eligibility gate

The weighted model applies **only after** the baseline functional non-regression gate in `outputs/01/invariants.md` I-21 through I-29 and `outputs/01/research-method.md` §10 passes.

Before a candidate can receive an eligible comparative ranking, it MUST provide an explicit baseline-function mapping using:

- `PRESERVED AS-IS`;
- `PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION`;
- `NOT APPLICABLE` with justification.

Protected baseline functions include at minimum:
- Work Item contract structure;
- Semantic Scope + Path Scope;
- exact-SHA review binding;
- SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE;
- same-objective REWORK continuity;
- Supervisor-only merge under exact-SHA semantic acceptance + merge-eligibility conditions where integration is authorized;
- `PUBLISH = HUMAN ACTION`;
- GitHub-based session recovery.

### Hard-veto rule

Any unexplained baseline functional loss, weakening, substitution, or reinterpretation is a **HARD VETO**.

For a hard-veto candidate:
- do not normalize or rank it as eligible;
- do not allow weighted score, sensitivity scenario, cost advantage, provider portability, automation depth, or test success to offset the veto;
- report the violated baseline guarantee and required correction/escalation.

A platform-specific implementation is not a regression when it preserves the same functional guarantee and makes the mechanism explicit.

### Relationship to the existing score

No criterion, weight, scale anchor, or sensitivity formula is changed by this correction.

The evaluation order is now explicit:

`BASELINE FUNCTIONAL NON-REGRESSION GATE → HARD INVARIANTS → EVIDENCE COVERAGE → WEIGHTED SCORE → SENSITIVITY → SYNTHESIS`

A score is therefore conditional on eligibility; it never grants eligibility.

## 11. Updated TASK 01 verification

- Baseline functional non-regression gate defined: YES
- Work Item contract protected: YES
- Semantic Scope and Path Scope independently protected: YES
- Exact-SHA review binding protected: YES
- SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE protected: YES
- Same-objective REWORK continuity protected: YES
- Supervisor-only merge boundary protected: YES
- PUBLISH = HUMAN ACTION protected: YES
- GitHub session recovery protected: YES
- Unexplained weakening is HARD VETO: YES
- Weighted scoring cannot compensate for baseline regression: YES
- Existing weights and scoring results changed by this TASK 01 correction: NO
