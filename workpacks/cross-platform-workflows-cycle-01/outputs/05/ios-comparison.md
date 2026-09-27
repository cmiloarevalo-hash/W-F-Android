# TASK 05 — iOS comparison

Status: EXPERIMENTAL ANALYTICAL COMPARISON — NOT CANONICAL

All values below are ANALYTICAL_SCORE under TASK 01. No empirical benchmark or external statistic is embedded in the totals.

## Baseline Functional Non-Regression Eligibility Gate

Accepted evaluation order:

```text
BASELINE FUNCTIONAL NON-REGRESSION GATE
→ HARD INVARIANTS
→ EVIDENCE COVERAGE
→ WEIGHTED SCORE
→ SENSITIVITY
→ SYNTHESIS
```

Weighted scoring is conditional on eligibility. Scoring does not establish eligibility, and any unexplained baseline functional regression is a **HARD VETO** that cannot be compensated by weighted score, sensitivity, automation, CI/test success, portability or cost.

The accepted TASK 04 ledgers at `1e594bfce5abbd9c2b13933aa13aa293b66a19d8` explicitly preserve all nine protected baseline guarantees for Candidates 1–3.

Eligibility results:
- **Candidate 1 eligibility gate: PASS**
- **Candidate 2 eligibility gate: PASS**
- **Candidate 3 eligibility gate: PASS**

TASK 04's governance-ledger correction did not change the iOS candidates' technical execution models, evidence, strengths/weaknesses, criteria, weights or score inputs. The base analytical scores therefore remain unchanged.

| ID | Criterion | Weight | C1 Minimal | C2 Portable | C3 Verified |
|---|---|---:|---:|---:|---:|
| C01 | Official platform guidance adherence | 9 | 4 | 4 | 5 |
| C02 | OpenAI coding-agent practice fit | 7 | 3 | 4 | 5 |
| C03 | Reproducibility | 7 | 4 | 5 | 5 |
| C04 | Testability / verification | 8 | 3 | 4 | 5 |
| C05 | Security and secrets control | 9 | 3 | 4 | 5 |
| C06 | Traceability / auditability | 6 | 3 | 4 | 5 |
| C07 | Context recovery / durability | 7 | 3 | 5 | 5 |
| C08 | Maintainability | 6 | 5 | 4 | 4 |
| C09 | Operational simplicity | 6 | 5 | 3 | 2 |
| C10 | Provider independence / portability | 6 | 3 | 5 | 4 |
| C11 | Local sandbox capability | 4 | 4 | 4 | 4 |
| C12 | Cloud sandbox capability | 4 | 3 | 5 | 5 |
| C13 | CI integration | 6 | 4 | 4 | 5 |
| C14 | Cost efficiency | 4 | 5 | 4 | 2 |
| C15 | Distribution / release compliance | 4 | 4 | 4 | 5 |
| C16 | Optional external-actor extensibility | 3 | 2 | 5 | 5 |
| C17 | Vendor lock-in risk | 4 | 3 | 4 | 3 |
| | **Weighted total** | **100** | **71.8** | **84.2** | **89.2** |

EvidenceCoverage: 100/100. No hard-veto invariant violation identified.

## Interpretation

Candidate 3 is strongest on verification/security/audit. Candidate 2 is strongest on avoiding unnecessary provider coupling around the unavoidable Apple toolchain boundary. Candidate 1 contributes a simpler default loop.

Candidate 4 therefore synthesizes:
- Candidate 2's provider-neutral mac-build/test/release adapters;
- Candidate 3's security, evidence and tiered verification;
- Candidate 1's default of not invoking simulator/device/release infrastructure unless required.

## Important scoring interpretation

C17 does not punish Apple-required Xcode/signing/App Store dependencies as though they were optional vendor lock-in. It measures avoidable coupling beyond that boundary.

## Evidence trace

Primary evidence: `outputs/04/ios-evidence.md`, especially I-01 through I-14.
Method: `outputs/01/scoring-model.md`.
