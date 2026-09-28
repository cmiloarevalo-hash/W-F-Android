# SUPERVISOR REVIEW PACKET — Web

STATUS: READY_FOR INDEPENDENT SUPERVISOR REVIEW

## TASK 07 REWORK evidence

The accepted evaluation order is now explicit before scoring:

```text
BASELINE FUNCTIONAL NON-REGRESSION GATE
→ HARD INVARIANTS
→ EVIDENCE COVERAGE
→ WEIGHTED SCORE
→ SENSITIVITY
→ SYNTHESIS
```

Candidates 1–3 are explicitly eligible via their accepted TASK 06 ledgers at `8d7038cf774db3aada3d48270b6d0077ef84e88d`.

Candidate 4 now contains the complete nine-row baseline functional non-regression ledger.

Base ANALYTICAL_SCORE values remain unchanged:
- Minimal: 74.6
- Portable: 85.8
- Verified: 90.0

Sensitivity reproducibility is explicit:
- S2 persists scenario multipliers, raw weights, normalization rule and reproduced totals;
- S3 persists exact candidate/criterion perturbations, deltas and resulting totals;
- S1 and S4 remain intact.

The external-actor activity rule from Issue #2 comment 5879863384 is not incorporated into TASK 07; it remains governance input for TASK 08 Common Core.

## Material assumptions
- governance can remain framework/provider-neutral;
- project-native commands are sufficient as the build/test adapter;
- browser matrix should be risk-driven rather than universally maximal;
- preview is evidence, not approval;
- accessibility and UX require human judgment beyond automation.

## Trade-offs
- Minimal: simplest, least systematic assurance.
- Portable: strongest vendor independence/recovery.
- Verified: strongest evidence/security, highest complexity.
- Candidate 4: Portable core + Verified gates + Minimal default path.

## Unresolved issues
- no concrete frontend/backend framework/runtime selected;
- no empirical E2E duration/cost data;
- browser targets are application-specific;
- preview/hosting/deployment provider remains intentionally unselected.

## Baseline differences
The frozen baseline contains project-specific Google AI Studio/Firebase/npm/Web assumptions. Candidate 4 preserves governance concepts but rejects those technologies as generic requirements. No legacy Google/AI Studio assumption is retained without generic evidence.

## Semantic propagation risks
1. Treating npm as universal web package management.
2. Treating preview deployment as approval or production equivalence.
3. Treating automated accessibility scans as full WCAG compliance.
4. Treating Playwright WebKit as identical to every Safari environment.
5. Treating framework choice as workflow authority.
6. Treating hosted CI/deploy credentials as permission to release.
7. Copying baseline AI_STUDIO_OPERATOR into cross-platform common core.

## Sensitivity
Base: 74.6 / 85.8 / 90.0.
S2 results reproduce from persisted exact scenario definitions.
S3 Stress A: 74.6 / 87.8 / 88.0.
S3 Stress B: 74.6 / 88.6 / 87.2.
Stability: CONDITIONALLY_STABLE; synthesis remains the conclusion rather than mechanical adoption of a score winner.

Allowed Supervisor outcomes: PASS | REWORK | HOLD | ESCALATE.
