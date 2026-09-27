# TASK 09 — Semantic propagation risks

STATUS: AUDITED

## Risk register

| Risk | Propagation path tested | Current status | Required control |
|---|---|---|---|
| Technical capability becomes authority | TASK01 → platform proposals → common core | CONTAINED | Keep authority gates explicit |
| Workpack API-only access becomes universal workflow rule | repository contract → Candidate 4 | CONTAINED | Keep it Workpack-specific |
| Baseline AI_STUDIO_OPERATOR becomes universal external actor | baseline → Web → common core | CONTAINED | Optional capability-specific interface only |
| Firebase becomes Android/core dependency | Android evidence → Candidate4 → common core | CONTAINED | Keep device provider optional |
| Xcode Cloud becomes iOS/core dependency | iOS evidence → Candidate4 → common core | CONTAINED | Keep macOS provider replaceable |
| npm/framework becomes Web/core dependency | baseline/web evidence → Candidate4 | CONTAINED | Project-native build adapter |
| Host build implies device/simulator support | platform candidates → common core | CONTAINED | Explicit platform verification adapters |
| Simulator/emulator/browser automation treated as real-world equivalence | platform tests → final proposal | CONTAINED | Risk-trigger physical/human evidence |
| CI pass becomes approval | all tasks | CONTAINED | Evidence != approval invariant |
| Score becomes statistic | comparisons → presentation | CONTAINED | Label ANALYTICAL_SCORE |
| Current versions become permanent workflow constants | evidence → Candidate4 → presentation | CONTAINED | Date/version scope + release-time recheck |
| Preview/beta environment becomes production authority | mobile/web release models | CONTAINED | Separate release/deploy domain |
| Common-core abstraction erases platform constraints | TASK08 → TASK10 | CONTAINED | Preserve platform delta table |

## Highest residual risks for TASK 10

1. Presentation compression risk: shortening proposals could remove authority or platform-boundary qualifiers.
2. Cross-platform language drift: a generic phrase such as device test could obscure Android-vs-iOS-vs-browser differences.
3. Version-fact promotion: current AGP/Xcode/store requirements could be mistaken for permanent architecture requirements.
4. Proposal/adoption ambiguity: a polished final package could be misread as approved/canonical.
5. Score headline bias: presentation may overemphasize 90.0/89.2 values despite sensitivity and synthesis logic.

## TASK 10 controls

The final package must:
- repeat STATUS: PROPOSAL — NOT CANONICAL;
- preserve explicit platform deltas;
- present scores only as analytical context, not as empirical performance;
- keep release/provider facts dated or abstracted to a freshness check;
- retain independent Supervisor/Human adoption boundary.
