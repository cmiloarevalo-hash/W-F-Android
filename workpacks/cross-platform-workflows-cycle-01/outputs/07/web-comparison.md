# TASK 07 — Web comparison

Status: EXPERIMENTAL ANALYTICAL COMPARISON — NOT CANONICAL

All values are ANALYTICAL_SCORE under TASK 01.

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
| C10 | Provider independence / portability | 6 | 4 | 5 | 4 |
| C11 | Local sandbox capability | 4 | 5 | 5 | 4 |
| C12 | Cloud sandbox capability | 4 | 4 | 5 | 5 |
| C13 | CI integration | 6 | 4 | 4 | 5 |
| C14 | Cost efficiency | 4 | 5 | 4 | 2 |
| C15 | Distribution / release compliance | 4 | 3 | 4 | 5 |
| C16 | Optional external-actor extensibility | 3 | 2 | 5 | 5 |
| C17 | Vendor lock-in risk | 4 | 4 | 5 | 4 |
| | **Weighted total** | **100** | **74.6** | **85.8** | **90.0** |

EvidenceCoverage: 100/100; no hard-veto invariant violation.

## Interpretation
- C1 contributes a small, framework-neutral loop.
- C2 contributes provider-neutral build/browser/preview/deploy adapters and durable recovery.
- C3 contributes strongest browser/security/accessibility/deployment evidence.
- Candidate 4 synthesizes all three and does not select C3 mechanically.

## No legacy-provider justification
No score assumes Google AI Studio, Firebase, Google Cloud, npm, Vercel, Netlify or any framework/hosting vendor is mandatory. Stack/provider choices are project adapters unless a concrete Work Item authorizes them.

Evidence: `outputs/06/web-evidence.md`; methodology: `outputs/01/scoring-model.md`.
