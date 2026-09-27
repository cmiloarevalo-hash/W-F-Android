# Presentation Brief — Cross-platform workflow cycle 01

STATUS: PROPOSAL PACKAGE — NOT CANONICAL

## Executive summary
The research supports one shared governance model with three distinct platform execution models.

Common recommendation:
- durable Work Item/repository state;
- explicit authority and scope;
- reproducible environment contract;
- risk-tiered verification;
- evidence bundles;
- isolated secrets/release boundaries;
- optional bounded external actors;
- independent review.

Platform execution:
- Android: portable Gradle host loop plus risk-triggered device testing and isolated Play/signing.
- iOS: portable governance around an unavoidable macOS/Xcode build boundary plus risk-triggered simulator/device testing and isolated Apple distribution.
- Web: framework/provider-neutral build/test contract plus browser/accessibility/preview/deployment tiers.

## Analytical comparison context
The Candidate 1–3 comparisons were analytical rubric results, not empirical benchmarks.

- Android: 73.8 / 85.8 / 90.0
- iOS: 71.8 / 84.2 / 89.2
- Web: 74.6 / 85.8 / 90.0

All three sensitivity analyses were CONDITIONALLY_STABLE. Candidate 4 therefore synthesizes strengths rather than automatically adopting the top numerical candidate.

## Key design choice
Use a small default verification path and escalate only when platform risk requires additional device/browser/release evidence.

This avoids making the highest-assurance infrastructure mandatory for every low-risk change while preserving a defined route to stronger evidence.

## Vendor/provider posture
- Firebase/Test Lab: optional Android device provider.
- Xcode Cloud: optional iOS macOS CI provider.
- Playwright: example web browser automation, not a requirement.
- Google AI Studio/Firebase/npm baseline specifics: not generic cross-platform requirements.
- CI/hosting/coding-agent provider: project choice within authorized constraints.

## Security/release posture
- normal implementation context should not automatically possess production release secrets;
- ability to sign/upload/deploy does not grant release authority;
- current store/provider policies are rechecked at release time;
- merge and canonical adoption remain independent decisions.

## Adversarial audit
TASK 09 result: PASS.
- baseline unchanged and byte-identical to pinned historical source;
- no out-of-scope writes detected;
- no propagated material semantic contradiction detected;
- no blocking rework required.

## Decisions for Supervisor/Human
1. Whether the common governance core should be adopted in a future Work Item.
2. Which platform proposal, if any, should be piloted.
3. Concrete CI/device/browser providers and cost limits.
4. Release credential custody and authorized release operators.
5. Project-specific verification matrices.
6. Whether external actors are required for any concrete project.

## Adoption warning
Nothing in this package is canonical merely because it is technically coherent or well-scored.
