# SUPERVISOR REVIEW PACKET — Web

STATUS: READY_FOR INDEPENDENT SUPERVISOR REVIEW

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
74.6 / 85.8 / 90.0; simplicity/cost reduces C3-vs-C2 margin to 1.87.
Stability: CONDITIONALLY_STABLE.

Allowed Supervisor outcomes: PASS | REWORK | HOLD | ESCALATE.
