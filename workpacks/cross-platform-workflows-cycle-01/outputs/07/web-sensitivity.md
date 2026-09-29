# TASK 07 — Web sensitivity analysis

Status: EXPERIMENTAL ANALYTICAL SENSITIVITY — NOT CANONICAL

Baseline ANALYTICAL_SCORE:
- Minimal 74.6
- Portable 85.8
- Verified 90.0

These base scores are unchanged. Sensitivity tests analytical uncertainty only; it is not empirical measurement, semantic acceptance or approval.

## S1 — one-at-a-time weight perturbation

All 34 ±20% one-at-a-time criterion-weight perturbations preserve C3 > C2 > C1.

## S2 — priority scenarios

Scenario definitions are fixed before computing totals. The named emphasis criteria receive the stated multiplier, then all raw weights are proportionally renormalized to exactly 100.

Normalization rule:

`scenario_weight_i = raw_weight_i / Σ(raw_weights) × 100`

Display formulas below are exact; calculations use the exact normalized weights rather than rounded percentages.

### SECURITY / VERIFICATION

Multiplier: **1.5** for C04, C05, C06 and C13.  
Raw-weight total: **114.5**.

| Criterion | Base weight | Raw weight | Exact normalized weight |
|---|---:|---:|---:|
| C01 Official platform guidance adherence | 9 | 9 | 9 / 114.5 × 100 |
| C02 OpenAI coding-agent practice fit | 7 | 7 | 7 / 114.5 × 100 |
| C03 Reproducibility | 7 | 7 | 7 / 114.5 × 100 |
| C04 Testability / verification | 8 | 12 | 12 / 114.5 × 100 |
| C05 Security and secrets control | 9 | 13.5 | 13.5 / 114.5 × 100 |
| C06 Traceability / auditability | 6 | 9 | 9 / 114.5 × 100 |
| C07 Context recovery / durability | 7 | 7 | 7 / 114.5 × 100 |
| C08 Maintainability | 6 | 6 | 6 / 114.5 × 100 |
| C09 Operational simplicity | 6 | 6 | 6 / 114.5 × 100 |
| C10 Provider independence / portability | 6 | 6 | 6 / 114.5 × 100 |
| C11 Local sandbox capability | 4 | 4 | 4 / 114.5 × 100 |
| C12 Cloud sandbox capability | 4 | 4 | 4 / 114.5 × 100 |
| C13 CI integration | 6 | 9 | 9 / 114.5 × 100 |
| C14 Cost efficiency | 4 | 4 | 4 / 114.5 × 100 |
| C15 Distribution / release compliance | 4 | 4 | 4 / 114.5 × 100 |
| C16 Optional external-actor extensibility | 3 | 3 | 3 / 114.5 × 100 |
| C17 Vendor lock-in risk | 4 | 4 | 4 / 114.5 × 100 |

Resulting ANALYTICAL_SCORE:
- C1: **73.28**
- C2: **85.07**
- C3: **91.27**

### PORTABILITY / DURABILITY

Multiplier: **1.5** for C03, C07, C10 and C17.  
Raw-weight total: **112**.

| Criterion | Base weight | Raw weight | Exact normalized weight |
|---|---:|---:|---:|
| C01 Official platform guidance adherence | 9 | 9 | 9 / 112 × 100 |
| C02 OpenAI coding-agent practice fit | 7 | 7 | 7 / 112 × 100 |
| C03 Reproducibility | 7 | 10.5 | 10.5 / 112 × 100 |
| C04 Testability / verification | 8 | 8 | 8 / 112 × 100 |
| C05 Security and secrets control | 9 | 9 | 9 / 112 × 100 |
| C06 Traceability / auditability | 6 | 6 | 6 / 112 × 100 |
| C07 Context recovery / durability | 7 | 10.5 | 10.5 / 112 × 100 |
| C08 Maintainability | 6 | 6 | 6 / 112 × 100 |
| C09 Operational simplicity | 6 | 6 | 6 / 112 × 100 |
| C10 Provider independence / portability | 6 | 9 | 9 / 112 × 100 |
| C11 Local sandbox capability | 4 | 4 | 4 / 112 × 100 |
| C12 Cloud sandbox capability | 4 | 4 | 4 / 112 × 100 |
| C13 CI integration | 6 | 6 | 6 / 112 × 100 |
| C14 Cost efficiency | 4 | 4 | 4 / 112 × 100 |
| C15 Distribution / release compliance | 4 | 4 | 4 / 112 × 100 |
| C16 Optional external-actor extensibility | 3 | 3 | 3 / 112 × 100 |
| C17 Vendor lock-in risk | 4 | 6 | 6 / 112 × 100 |

Resulting ANALYTICAL_SCORE:
- C1: **74.55**
- C2: **87.32**
- C3: **90.18**

### SIMPLICITY / COST

Multiplier: **1.75** for C08, C09 and C14.  
Raw-weight total: **112**.

| Criterion | Base weight | Raw weight | Exact normalized weight |
|---|---:|---:|---:|
| C01 Official platform guidance adherence | 9 | 9 | 9 / 112 × 100 |
| C02 OpenAI coding-agent practice fit | 7 | 7 | 7 / 112 × 100 |
| C03 Reproducibility | 7 | 7 | 7 / 112 × 100 |
| C04 Testability / verification | 8 | 8 | 8 / 112 × 100 |
| C05 Security and secrets control | 9 | 9 | 9 / 112 × 100 |
| C06 Traceability / auditability | 6 | 6 | 6 / 112 × 100 |
| C07 Context recovery / durability | 7 | 7 | 7 / 112 × 100 |
| C08 Maintainability | 6 | 10.5 | 10.5 / 112 × 100 |
| C09 Operational simplicity | 6 | 10.5 | 10.5 / 112 × 100 |
| C10 Provider independence / portability | 6 | 6 | 6 / 112 × 100 |
| C11 Local sandbox capability | 4 | 4 | 4 / 112 × 100 |
| C12 Cloud sandbox capability | 4 | 4 | 4 / 112 × 100 |
| C13 CI integration | 6 | 6 | 6 / 112 × 100 |
| C14 Cost efficiency | 4 | 7 | 7 / 112 × 100 |
| C15 Distribution / release compliance | 4 | 4 | 4 / 112 × 100 |
| C16 Optional external-actor extensibility | 3 | 3 | 3 / 112 × 100 |
| C17 Vendor lock-in risk | 4 | 4 | 4 / 112 × 100 |

Resulting ANALYTICAL_SCORE:
- C1: **77.32**
- C2: **84.38**
- C3: **86.25**

Each scenario's exact normalized weights sum to **100 by construction**.

## S3 — score uncertainty

Decision-critical uncertainty is concentrated in actual E2E/browser-matrix burden, preview/hosting cost and human design-review burden. All perturbations below are explicit, remain within [0,5], use the fixed TASK 01 base weights and change only analytical score assumptions for the stated stress test.

### Stress A — simplicity / cost

Explicit perturbations:
- Candidate 2 C09 Operational simplicity: **3 → 4 (+1)**
- Candidate 2 C14 Cost efficiency: **4 → 5 (+1)**
- Candidate 3 C09 Operational simplicity: **2 → 1 (-1)**
- Candidate 3 C14 Cost efficiency: **2 → 1 (-1)**

All other scores remain unchanged.

Resulting ANALYTICAL_SCORE:
- C1: **74.6** unchanged
- C2: **87.8**
- C3: **88.0**

Interpretation: the C3–C2 gap narrows from 4.2 to 0.2 points under a plausible simplicity/cost uncertainty combination.

### Stress B — browser / verification burden

Explicit perturbations:
- Candidate 2 C04 Testability / verification: **4 → 5 (+1)**
- Candidate 2 C09 Operational simplicity: **3 → 4 (+1)**
- Candidate 3 C04 Testability / verification: **5 → 4 (-1)**
- Candidate 3 C09 Operational simplicity: **2 → 1 (-1)**

All other scores remain unchanged.

Resulting ANALYTICAL_SCORE:
- C1: **74.6** unchanged
- C2: **88.6**
- C3: **87.2**

Interpretation: a plausible concrete-project reassessment of browser-verification fit and operating burden can reverse the C2/C3 analytical ordering. This does not select C2 automatically; it reinforces Candidate 4 synthesis rather than score-winner adoption.

## S4 — missing evidence

No NE criteria exist at design stage. Concrete stacks may introduce NE for actual browser-matrix cost, preview/hosting cost or deployment integration evidence; those would require explicit lower/upper bounds under TASK 01.

## Stability

**CONDITIONALLY_STABLE.**

The candidate ordering can narrow or reverse under plausible S3 uncertainty, while the synthesis conclusion remains supported: combine C2 portability with C3 assurance while retaining C1's minimal default path. No sensitivity result can override a HARD VETO or create semantic approval.
