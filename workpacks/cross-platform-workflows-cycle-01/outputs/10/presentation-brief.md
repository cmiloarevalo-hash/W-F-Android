# Presentation Brief — Cross-platform workflow cycle 01

STATUS: PROPOSAL PACKAGE — NOT CANONICAL

## Executive summary

The accepted research chain supports one shared governance model with three distinct platform execution models.

Shared governance:
- six-field Work Item contract;
- Semantic Scope + Path Scope as independent constraints;
- exact-SHA Supervisor review;
- `SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE`;
- same-objective REWORK continuity;
- Supervisor-only merge with `SEMANTIC_ACCEPTED != MERGE_ELIGIBLE`;
- `PUBLISH = HUMAN ACTION`;
- GitHub-based session recovery;
- baseline functional non-regression gate / HARD VETO.

Authority rule:

`TECHNICAL CAPABILITY != WORKFLOW AUTHORITY`

A HARD VETO cannot be offset by score, CI/tests, automation, portability, cost or actor capability.

## Platform execution remains distinct

- **Android:** Gradle/JDK/Android SDK; host build plus risk-triggered emulator/physical-device evidence; Android signing; APK/AAB/store distribution.
- **iOS:** unavoidable macOS/Xcode native build boundary; simulator/physical-device evidence; Apple signing/provisioning; TestFlight/App Store.
- **Web:** project-selected runtime/build; browser/E2E/accessibility/human UX; preview/provider-specific deployment; no universal mobile-style signing gate.

No provider or tool is made mandatory for symmetry.

## External actor rule

External actors are optional and capability-specific.

Every invocation must persist a durable GitHub activity under the governing Work Item per Issue #2 comment `5879863384`, including authority bounds, expected baseline, evidence, result, stop conditions and closure state.

Lifecycle:

`request → authority → execution → evidence → result → stop/escalation`

The activity record is evidence/continuity only; it creates no Workflow authority and never grants publication authority.

## Publication boundary

`PUBLISH = HUMAN ACTION`

Build/sign/upload/deploy capability, credentials, provider roles, CI success or ordinary Work Item technical permission do not transfer publication authority to Implementer, CI or an external actor.

## Analytical comparison context

Candidate 1–3 comparisons are analytical rubric results, not empirical benchmarks:

- Android: 73.8 / 85.8 / 90.0
- iOS: 71.8 / 84.2 / 89.2
- Web: 74.6 / 85.8 / 90.0

Candidate 4 is synthesis, not automatic adoption of the highest numerical score. Eligibility and HARD VETO checks precede scoring.

## Accepted exact-SHA chain

- TASK 01: `a863f099cd0adf9b62fc9185c990dddda614a795`
- TASK 02: `e57b4aa6cbca215fc162ae4a0d7aa8800e706dd5`
- TASK 03: `6e061a0793e039f3eccdc7514d7b89b62bbb747b`
- TASK 04: `1e594bfce5abbd9c2b13933aa13aa293b66a19d8`
- TASK 05: `018cecbb6446db682fd4061d1b03b7d81e3e5d64`
- TASK 06: `8d7038cf774db3aada3d48270b6d0077ef84e88d`
- TASK 07: `8ca5f3c9bc26484e2a26e1098afd475e6754169a`
- TASK 08: `e1013c3a629032e98a4169b8b58eca77edd84230`
- TASK 09: `c1fe4ba3e80dd5d9077188026fd1d1988fb066bc`

These are the final semantic-acceptance SHAs for TASK 01–09. Earlier checkpoints remain historical evidence only.

## Adversarial audit — accurate history

Historical:
- original TASK 09 checkpoint `9a0da69e4fd031e203080d165eb65b89a9de5c22` missed a real publication-authority defect;
- Supervisor comment `5880275506` classified the original TASK 08 publication weakening as a HARD VETO;
- TASK 08 required blocking REWORK;
- TASK 09 later required REWORK to preserve that false negative and re-audit the corrected accepted chain.

Current:
- TASK 08 corrected state was accepted at `e1013c3a629032e98a4169b8b58eca77edd84230`;
- renewed TASK 09 audit found no unresolved material contradiction in the corrected accepted TASK 01–08 chain;
- TASK 09 was accepted at `c1fe4ba3e80dd5d9077188026fd1d1988fb066bc`.

Therefore the correct statement is not “no blocking rework occurred.” Blocking rework occurred and is part of the durable evidence trail; the current accepted chain is the corrected result.

## Vendor/provider posture

- Firebase/Test Lab: optional Android device provider.
- Xcode Cloud: optional iOS macOS CI provider.
- Playwright: possible Web browser implementation, not a requirement.
- Google AI Studio/Firebase/npm baseline specifics: not generic cross-platform requirements.
- CI/hosting/coding-agent provider: project choice within authorized constraints.

## Decisions reserved for Supervisor/Human

1. Whether any proposal should be adopted through a future Work Item.
2. Which platform proposal, if any, should be piloted.
3. Concrete CI/device/browser providers and cost limits.
4. Technical signing/deployment credential custody.
5. Project-specific verification matrices.
6. Whether external actors are required.
7. Human publication action for any production/store release.

## Adoption warning

Nothing in this package is canonical merely because it is technically coherent, well-scored or semantically accepted as a proposal artifact.

No merge or canonical adoption is authorized by this brief.
