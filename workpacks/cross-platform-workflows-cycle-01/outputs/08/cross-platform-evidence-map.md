# TASK 08 — Cross-platform evidence map

STATUS: EXPERIMENTAL TRACEABILITY MAP

| Common rule | Android basis | iOS basis | Web basis | Cross-platform classification |
|---|---|---|---|---|
| Work Item defines authority | outputs/03 Candidate 4 governance | outputs/05 Candidate 4 governance | outputs/07 Candidate 4 governance | PROJECT FACT / INVARIANT |
| Durable repo state | outputs/01 invariants I-05/I-19 | same | same | PROJECT FACT + OpenAI guidance |
| Environment contract | Android A-04/A-05/A-06 | iOS I-01/I-02/I-04 | web W-08 + project-native adapter | INFERENCE from verified facts |
| Tiered verification | A-07..A-13 | I-03..I-05 | W-01..W-03/W-07 | RECOMMENDATION supported by facts |
| CI evidence != approval | invariants I-11/I-13 | same | same | PROJECT FACT / GOVERNANCE |
| Secrets/release separation | A-15..A-18 | I-06..I-10 | W-04..W-06 | VERIFIED EXTERNAL FACT + recommendation |
| External actor optional | Android Candidate 4 | iOS Candidate 4 | web Candidate 4 | RECOMMENDATION |
| Provider-specific service optional | Firebase/Test Lab optional | Xcode Cloud optional | hosting/framework optional | RECOMMENDATION |
| Platform-specific verification adapter | device/emulator | simulator/device/Mac | browser/E2E/preview | VERIFIED platform delta |
| Proposal remains non-canonical | Issue #2 / invariants | Issue #2 / invariants | Issue #2 / invariants | PROJECT FACT |

## Source families
- OpenAI current agent guidance: `outputs/01/source-register.md`.
- Android official evidence: `outputs/02/android-evidence.md`.
- iOS official evidence: `outputs/04/ios-evidence.md`.
- Web standards/tooling evidence: `outputs/06/web-evidence.md`.
- Platform proposals: `outputs/03`, `outputs/05`, `outputs/07`.

## Conclusion
The common core is governance/evidence-oriented. Build, test surface, device/browser execution, signing and distribution remain platform deltas.
