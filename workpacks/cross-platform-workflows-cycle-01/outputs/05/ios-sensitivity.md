# TASK 05 — iOS sensitivity analysis

Status: EXPERIMENTAL ANALYTICAL SENSITIVITY — NOT CANONICAL

Baseline:
- Minimal: 71.8
- Portable: 84.2
- Verified: 89.2

## S1 — one-at-a-time weights
All 34 ±20% single-criterion perturbations preserved ordering C3 > C2 > C1.

## S2 — priority scenarios

- SECURITY/VERIFICATION emphasis: C1 70.83, C2 83.67, C3 90.57.
- PORTABILITY/DURABILITY emphasis: C1 71.16, C2 85.54, C3 89.11.
- SIMPLICITY/COST emphasis: C1 74.82, C2 82.95, C3 85.54.

All values are ANALYTICAL_SCORE.

## S3 — score uncertainty

Material uncertainty is concentrated in:
- actual macOS runner cost/availability;
- physical-device need;
- whether release automation is desired;
- provider-specific maintenance burden.

A plausible increase in C2 simplicity/cost and decrease in C3 simplicity/cost narrows the comparison materially, reinforcing synthesis rather than direct adoption of C3.

## S4 — missing evidence
No NE criterion exists in the design-stage comparison. Concrete projects may introduce NE for actual runner/device cost or release infrastructure.

## Stability
**CONDITIONALLY_STABLE**

The stable conclusion is that high-assurance controls are valuable, but should be layered over a portable minimal core rather than making the heaviest workflow mandatory for every iOS change.
