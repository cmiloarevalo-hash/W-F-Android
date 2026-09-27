# TASK 05 — iOS sensitivity analysis

Status: EXPERIMENTAL ANALYTICAL SENSITIVITY — NOT CANONICAL

Baseline:
- Minimal: 71.8
- Portable: 84.2
- Verified: 89.2

## S1 — one-at-a-time weights
All 34 ±20% single-criterion perturbations preserved ordering C3 > C2 > C1.

## S2 — priority scenarios

Scenario definitions are fixed before computing totals. Each scenario multiplies the named emphasis criteria, then proportionally renormalizes all raw weights to exactly 100.

Normalization rule:

`scenario_weight_i = raw_weight_i / Σ(raw_weights) × 100`

The exact normalized weights therefore sum to 100 by construction. Decimal values below are display approximations only; calculations use the unrounded normalized weights.

### SECURITY / VERIFICATION

Multiplier: **1.5** for C04, C05, C06 and C13.

Raw-weight total after multiplier: **114.5**.

| Criterion | Raw weight | Normalized weight |
|---|---:|---:|
| C01 | 9 | 9 / 114.5 × 100 |
| C02 | 7 | 7 / 114.5 × 100 |
| C03 | 7 | 7 / 114.5 × 100 |
| C04 | 12 | 12 / 114.5 × 100 |
| C05 | 13.5 | 13.5 / 114.5 × 100 |
| C06 | 9 | 9 / 114.5 × 100 |
| C07 | 7 | 7 / 114.5 × 100 |
| C08 | 6 | 6 / 114.5 × 100 |
| C09 | 6 | 6 / 114.5 × 100 |
| C10 | 6 | 6 / 114.5 × 100 |
| C11 | 4 | 4 / 114.5 × 100 |
| C12 | 4 | 4 / 114.5 × 100 |
| C13 | 9 | 9 / 114.5 × 100 |
| C14 | 4 | 4 / 114.5 × 100 |
| C15 | 4 | 4 / 114.5 × 100 |
| C16 | 3 | 3 / 114.5 × 100 |
| C17 | 4 | 4 / 114.5 × 100 |

Result:
- C1: **70.83**
- C2: **83.67**
- C3: **90.57**

### PORTABILITY / DURABILITY

Multiplier: **1.5** for C03, C07, C10 and C17.

Raw-weight total after multiplier: **112**.

| Criterion | Raw weight | Normalized weight |
|---|---:|---:|
| C01 | 9 | 9 / 112 × 100 |
| C02 | 7 | 7 / 112 × 100 |
| C03 | 10.5 | 10.5 / 112 × 100 |
| C04 | 8 | 8 / 112 × 100 |
| C05 | 9 | 9 / 112 × 100 |
| C06 | 6 | 6 / 112 × 100 |
| C07 | 10.5 | 10.5 / 112 × 100 |
| C08 | 6 | 6 / 112 × 100 |
| C09 | 6 | 6 / 112 × 100 |
| C10 | 9 | 9 / 112 × 100 |
| C11 | 4 | 4 / 112 × 100 |
| C12 | 4 | 4 / 112 × 100 |
| C13 | 6 | 6 / 112 × 100 |
| C14 | 4 | 4 / 112 × 100 |
| C15 | 4 | 4 / 112 × 100 |
| C16 | 3 | 3 / 112 × 100 |
| C17 | 6 | 6 / 112 × 100 |

Result:
- C1: **71.16**
- C2: **85.54**
- C3: **89.11**

### SIMPLICITY / COST

Multiplier: **1.75** for C08, C09 and C14.

Raw-weight total after multiplier: **112**.

| Criterion | Raw weight | Normalized weight |
|---|---:|---:|
| C01 | 9 | 9 / 112 × 100 |
| C02 | 7 | 7 / 112 × 100 |
| C03 | 7 | 7 / 112 × 100 |
| C04 | 8 | 8 / 112 × 100 |
| C05 | 9 | 9 / 112 × 100 |
| C06 | 6 | 6 / 112 × 100 |
| C07 | 7 | 7 / 112 × 100 |
| C08 | 10.5 | 10.5 / 112 × 100 |
| C09 | 10.5 | 10.5 / 112 × 100 |
| C10 | 6 | 6 / 112 × 100 |
| C11 | 4 | 4 / 112 × 100 |
| C12 | 4 | 4 / 112 × 100 |
| C13 | 6 | 6 / 112 × 100 |
| C14 | 7 | 7 / 112 × 100 |
| C15 | 4 | 4 / 112 × 100 |
| C16 | 3 | 3 / 112 × 100 |
| C17 | 4 | 4 / 112 × 100 |

Result:
- C1: **74.82**
- C2: **82.95**
- C3: **85.54**

All scenario totals remain **ANALYTICAL_SCORE**, not empirical measurements.

## S3 — score uncertainty

Decision-critical uncertainty is concentrated in operational simplicity/cost and avoidable provider coupling. Score perturbations remain within [0,5] and use the fixed TASK 01 base weights.

### Stress test A — simplicity / cost

Explicit perturbations:
- Candidate 2 C09 Operational simplicity: **3 → 4 (+1)**
- Candidate 2 C14 Cost efficiency: **4 → 5 (+1)**
- Candidate 3 C09 Operational simplicity: **2 → 1 (-1)**
- Candidate 3 C14 Cost efficiency: **2 → 1 (-1)**

All other candidate scores remain unchanged.

Resulting analytical totals:
- C1: **71.8** unchanged
- C2: **86.2**
- C3: **87.2**

Interpretation: the C3–C2 gap narrows from 5.0 to 1.0 points under a plausible simplicity/cost uncertainty combination.

### Stress test B — avoidable provider coupling

Explicit perturbations:
- Candidate 2 C17 Vendor lock-in risk: **4 → 5 (+1)**
- Candidate 3 C10 Provider independence / portability: **4 → 3 (-1)**
- Candidate 3 C17 Vendor lock-in risk: **3 → 2 (-1)**

All other candidate scores remain unchanged.

Resulting analytical totals:
- C1: **71.8** unchanged
- C2: **85.0**
- C3: **87.2**

Interpretation: uncertainty around provider maintenance/coupling also narrows C3 vs C2, while preserving the synthesis rationale.

These are **ANALYTICAL_SCORE uncertainty tests**, not empirical measurements and not semantic approval.

## S4 — missing evidence
No NE criterion exists in the design-stage comparison. Concrete projects may introduce NE for actual runner/device cost or release infrastructure.

## Stability
**CONDITIONALLY_STABLE**

The stable conclusion is that high-assurance controls are valuable, but should be layered over a portable minimal core rather than making the heaviest workflow mandatory for every iOS change.
