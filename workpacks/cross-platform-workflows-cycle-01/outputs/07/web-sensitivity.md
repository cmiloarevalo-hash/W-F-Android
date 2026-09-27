# TASK 07 — Web sensitivity analysis

Status: EXPERIMENTAL ANALYTICAL SENSITIVITY — NOT CANONICAL

Baseline:
- Minimal 74.6
- Portable 85.8
- Verified 90.0

## S1
All ±20% one-at-a-time criterion-weight perturbations preserve C3 > C2 > C1.

## S2
Predeclared scenarios:
- SECURITY/VERIFICATION: C1 73.28, C2 85.07, C3 91.27.
- PORTABILITY/DURABILITY: C1 74.55, C2 87.32, C3 90.18.
- SIMPLICITY/COST: C1 77.32, C2 84.38, C3 86.25.

## S3
Material uncertainty concerns actual E2E/browser matrix size, preview cost, hosting/provider integration and human design-review burden. Reasonable changes to simplicity/cost scores can make C2 and C3 nearly tied.

## S4
No NE criteria at design stage; concrete stacks may introduce unknowns.

## Stability
CONDITIONALLY_STABLE.

Robust conclusion: combine C2 portability with C3 assurance while retaining C1's minimal default path.
