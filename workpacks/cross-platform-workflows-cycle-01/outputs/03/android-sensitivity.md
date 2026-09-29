# TASK 03 — Android sensitivity analysis

Status: EXPERIMENTAL ANALYTICAL SENSITIVITY — NOT CANONICAL

Baseline totals:
- C1 Minimal: 73.8
- C2 Portable: 85.8
- C3 Verified: 90.0

All numbers are analytical rubric outputs, not empirical measurements.

## S1 — One-at-a-time weight perturbation

Method: vary each criterion weight independently by -20% and +20% relative, renormalizing all other weights proportionally to total 100.

Result:
- tested 34 perturbations (17 criteria × 2 directions);
- ordering remained **C3 > C2 > C1** in every perturbation;
- no hard invariant changed.

Interpretation: no single modest criterion-weight change overturns the baseline ordering.

## S2 — Predeclared priority scenarios

Scenario weights were derived before computing scenario totals by multiplying the named emphasis group, then proportionally renormalizing to 100.

### SECURITY / VERIFICATION
Multiplier 1.5 for C04, C05, C06, C13.

| Criterion | Weight |
|---|---:|
| C01 | 7.86 |
| C02 | 6.11 |
| C03 | 6.11 |
| C04 | 10.48 |
| C05 | 11.79 |
| C06 | 7.86 |
| C07 | 6.11 |
| C08 | 5.24 |
| C09 | 5.24 |
| C10 | 5.24 |
| C11 | 3.49 |
| C12 | 3.49 |
| C13 | 7.86 |
| C14 | 3.49 |
| C15 | 3.49 |
| C16 | 2.62 |
| C17 | 3.49 |

Totals:
- C1: 72.58
- C2: 85.07
- C3: 91.27

### PORTABILITY / DURABILITY
Multiplier 1.5 for C03, C07, C10, C17.

| Criterion | Weight |
|---|---:|
| C01 | 8.04 |
| C02 | 6.25 |
| C03 | 9.38 |
| C04 | 7.14 |
| C05 | 8.04 |
| C06 | 5.36 |
| C07 | 9.38 |
| C08 | 5.36 |
| C09 | 5.36 |
| C10 | 8.04 |
| C11 | 3.57 |
| C12 | 3.57 |
| C13 | 5.36 |
| C14 | 3.57 |
| C15 | 3.57 |
| C16 | 2.68 |
| C17 | 5.36 |

Totals:
- C1: 73.84
- C2: 87.32
- C3: 90.18

### SIMPLICITY / COST
Multiplier 1.75 for C08, C09, C14.

| Criterion | Weight |
|---|---:|
| C01 | 8.04 |
| C02 | 6.25 |
| C03 | 6.25 |
| C04 | 7.14 |
| C05 | 8.04 |
| C06 | 5.36 |
| C07 | 6.25 |
| C08 | 9.38 |
| C09 | 9.38 |
| C10 | 5.36 |
| C11 | 3.57 |
| C12 | 3.57 |
| C13 | 5.36 |
| C14 | 6.25 |
| C15 | 3.57 |
| C16 | 2.68 |
| C17 | 3.57 |

Totals:
- C1: 76.61
- C2: 84.38
- C3: 86.25

Interpretation: C3 remains numerically first, but its margin over C2 falls from 4.2 to 1.87 in the simplicity/cost scenario.

## S3 — Score uncertainty

Decision-critical uncertainty is concentrated in operational simplicity, cost and provider portability because these depend strongly on project scale, CI provider and chosen device matrix.

Stress test:
- increase C2 simplicity and cost (C09/C14) by +1 each;
- decrease C3 simplicity and cost by -1 each.

Result:
- C2: 87.8
- C3: 88.0

The gap nearly disappears.

A second stress test lowering C3 provider independence and lock-in (C10/C17) by 1 each yields:
- C2: 85.8
- C3: 88.0

## S4 — Missing evidence bounds

No criterion is NE in the design-stage comparison, so S4 does not widen the current totals.

This does not mean future implementation facts are known. A real project may introduce NE values (for example actual CI cost, emulator capacity or release-provider constraints) and must recompute bounds.

## Stability label

**CONDITIONALLY_STABLE**

Reason:
- C3 > C2 > C1 is stable under the predeclared one-at-a-time and priority-weight scenarios;
- reasonable score uncertainty around simplicity/cost materially narrows C3 vs C2;
- the robust design conclusion is not "choose C3 unchanged" but "combine C2 portability with C3 verification while preserving C1's minimal default path."

This label is analysis, not approval.
