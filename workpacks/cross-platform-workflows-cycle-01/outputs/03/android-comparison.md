# TASK 03 — Android comparison

Status: EXPERIMENTAL ANALYTICAL COMPARISON — NOT CANONICAL  
Method: `outputs/01/scoring-model.md`  
Evidence: `outputs/02/android-evidence.md`

## 1. Baseline Functional Non-Regression Eligibility Gate

Accepted evaluation order:

```text
BASELINE FUNCTIONAL NON-REGRESSION GATE
→ HARD INVARIANTS
→ EVIDENCE COVERAGE
→ WEIGHTED SCORE
→ SENSITIVITY
→ SYNTHESIS
```

Weighted scoring is conditional on eligibility. Scoring does not establish eligibility, and any unexplained baseline functional regression is a **HARD VETO** that cannot be compensated by weighted score, sensitivity, automation, CI/test success, cost, portability or provider independence.

The accepted TASK 02 ledgers at `e57b4aa6cbca215fc162ae4a0d7aa8800e706dd5` explicitly preserve all nine protected baseline guarantees for Candidates 1–3:

| Protected baseline guarantee | C1 Minimal | C2 Portable | C3 Verified |
|---|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 3. Exact-SHA Supervisor semantic review | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 5. Same-objective REWORK continuity in same Issue/branch/PR | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 8. GitHub-based session recovery | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | PRESERVED AS-IS | PRESERVED AS-IS |

Eligibility results:
- **Candidate 1 eligibility gate: PASS**
- **Candidate 2 eligibility gate: PASS**
- **Candidate 3 eligibility gate: PASS**

No candidate is scored as eligible merely because it has a high analytical total. The accepted TASK 02 correction added explicit governance-preservation evidence without changing the candidates' Android execution models, technical evidence, strengths/weaknesses, criteria, weights or score inputs.

## 2. Hard invariants and evidence coverage

All three eligible candidates satisfy the Workpack hard-veto invariants as written. No candidate proposes self-approval, baseline mutation, scope expansion or automatic canonical adoption.

EvidenceCoverage: **100/100** for all candidates for this design-stage comparison.  
Important: the values below are **ANALYTICAL_SCORE**, not measurements or external statistics.

## 3. Weighted score table

| ID | Criterion | Weight | C1 Minimal | C2 Portable | C3 Verified |
|---|---|---:|---:|---:|---:|
| C01 | Official platform guidance adherence | 9 | 4 | 4 | 5 |
| C02 | OpenAI coding-agent practice fit | 7 | 3 | 4 | 5 |
| C03 | Reproducibility | 7 | 4 | 5 | 5 |
| C04 | Testability / verification | 8 | 3 | 4 | 5 |
| C05 | Security and secrets control | 9 | 3 | 4 | 5 |
| C06 | Traceability / auditability | 6 | 3 | 4 | 5 |
| C07 | Context recovery / durability | 7 | 3 | 5 | 5 |
| C08 | Maintainability | 6 | 5 | 4 | 4 |
| C09 | Operational simplicity | 6 | 5 | 3 | 2 |
| C10 | Provider independence / portability | 6 | 4 | 5 | 4 |
| C11 | Local sandbox capability | 4 | 4 | 5 | 4 |
| C12 | Cloud sandbox capability | 4 | 3 | 5 | 5 |
| C13 | CI integration | 6 | 4 | 4 | 5 |
| C14 | Cost efficiency | 4 | 5 | 4 | 2 |
| C15 | Distribution / release compliance | 4 | 4 | 4 | 5 |
| C16 | Optional external-actor extensibility | 3 | 2 | 5 | 5 |
| C17 | Vendor lock-in risk | 4 | 4 | 5 | 4 |
|  | **Weighted total / 100** | **100** | **73.8** | **85.8** | **90.0** |

## 4. Score rationale

### C01 — Official platform guidance
- C1=4: uses Kotlin/Compose-aware architecture, Gradle tasks, lint and targeted device tests but leaves more verification selection to operator judgment.
- C2=4: same Android-aligned primitives with more provider abstraction.
- C3=5: most explicitly maps Android test layers, device testing, signing and release boundaries to current first-party guidance.
Evidence: A-01 through A-18 in `android-evidence.md`.

### C02 — OpenAI coding-agent practice fit
- C1=3: scoped and reviewable but less durable evidence structure.
- C2=4: durable contracts and recovery files align with long-horizon guidance.
- C3=5: combines durable state, milestone verification, bounded execution and explicit audit evidence.
Evidence: TASK 01 source register OAI-01..OAI-09.

### C03 — Reproducibility
- C1=4: wrapper/toolchain discipline is reproducible but some risk decisions are implicit.
- C2=5: explicit host/device/release adapter inputs and outputs.
- C3=5: environment fingerprint and evidence bundle make runs reconstructable.

### C04 — Testability / verification
- C1=3: credible floor but device tests are selectively/manual-risk driven.
- C2=4: device adapter formalizes the path.
- C3=5: explicit Tier 0–4 verification ladder.

### C05 — Security and secrets
- C1=3: keeps production secrets out of normal flow, but has lighter audit controls.
- C2=4: release adapter and provider-secret separation are explicit.
- C3=5: strongest least-privilege, environment separation and evidence handling.

### C06 — Traceability / auditability
- C1=3: basic CI logs/checkpoints.
- C2=4: standardized evidence bundle.
- C3=5: per-checkpoint toolchain/device/retry/artifact ledger.

### C07 — Context recovery / durability
- C1=3: concise recovery is sufficient for smaller work but intentionally thin.
- C2=5: durable task/state/evidence contracts are core.
- C3=5: durable state plus audit/checkpoint detail.

### C08 — Maintainability
- C1=5: few moving parts.
- C2=4: adapter contracts add manageable maintenance.
- C3=4: clear structure, but more gates/evidence artifacts require upkeep.

### C09 — Operational simplicity
- C1=5: smallest operational surface.
- C2=3: adapters and durable evidence add process.
- C3=2: tiered CI/security/audit is deliberately heavier.

### C10 — Provider independence
- C1=4: few provider dependencies but no explicit portability interface.
- C2=5: provider-neutral host/device/release contracts are defining feature.
- C3=4: supports adapters but stronger cloud/device evidence can encourage provider coupling if not controlled.

### C11 — Local sandbox
- C1=4: host tasks work well; device tests depend on local capabilities.
- C2=5: local runner is a first-class adapter.
- C3=4: supported but high-assurance paths may require extra device infrastructure.

### C12 — Cloud sandbox
- C1=3: host build is portable; device capability is less formalized.
- C2=5: explicit host/device split fits heterogeneous cloud environments.
- C3=5: cloud host + optional remote device lab is explicitly modeled.

### C13 — CI integration
- C1=4: test/lint/build fit normal CI.
- C2=4: provider-neutral CI contract is strong but intentionally less prescriptive.
- C3=5: CI topology and evidence aggregation are core.

### C14 — Cost efficiency
- C1=5: avoids broad matrices and paid dependencies by default.
- C2=4: can choose low-cost adapters and defer broad matrices.
- C3=2: higher assurance can consume materially more runner/device time; no external price statistic is asserted.

### C15 — Distribution / release compliance
- C1=4: release boundary and Play checks are explicit.
- C2=4: release adapter is explicit but provider-neutral.
- C3=5: release candidate tier includes protected signing, artifact/provenance and policy freshness gate.

### C16 — Optional external actor
- C1=2: external actor is exceptional and minimally integrated.
- C2=5: actor/provider adapters are explicit.
- C3=5: device/Google service operator contract is fully bounded.

### C17 — Vendor lock-in
- C1=4: little coupling, but implicit environment assumptions may remain.
- C2=5: highest explicit portability and provider substitution.
- C3=4: optional Test Lab/cloud path remains replaceable but richer provider integrations can create switching cost.

## 5. Interpretation

Candidate 3 has the highest baseline analytical total, but Candidate 2 is close and stronger on portability/cost containment. Candidate 1's main contribution is not its aggregate score; it demonstrates that the common loop can remain materially simpler when risk does not justify device matrices or richer audit infrastructure.

Therefore Candidate 4 is synthesized rather than selected:
- use Candidate 2's provider-neutral host/device/release contracts;
- use Candidate 3's tiered verification, security boundary and audit rules;
- preserve Candidate 1's default of the smallest verification set that proves the change.

## 6. Quantitative discipline

No empirical benchmark was run for Candidates 1–3.  
No external statistic was used in the weighted totals.  
All criterion values and totals above are ANALYTICAL_SCORE under the predeclared TASK 01 rubric.
