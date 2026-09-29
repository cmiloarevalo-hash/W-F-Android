# TASK 04 — iOS capability matrix

Status: EXPERIMENTAL COMPARISON INPUT — NOT CANONICAL

| Capability | Candidate 1 Minimal | Candidate 2 Portable | Candidate 3 Verified |
|---|---|---|---|
| Durable GitHub task/state | Core | Core | Core |
| Swift/SwiftUI awareness | Core | Core | Core |
| macOS/Xcode build lane | Single lane | Provider-neutral adapter | Hardened controlled lane |
| Linux use | Source/domain-only where possible | First-class non-Apple prep lane | Restricted to non-Apple work |
| Swift Testing/XCTest | Basic | Core | Core + policy |
| Simulator tests | Targeted | Adapter | Risk-tiered |
| Physical-device tests | Manual/rare | Adapter | Risk/high-value tier |
| .xcresult retention | Basic | Standard | Structured/audited |
| Signing credentials | Manual gate | Release adapter | Isolated protected release domain |
| Provisioning | Manual/automatic Xcode | Adapter/explicit contract | Audited release contract |
| TestFlight | Manual gate | Optional release adapter | Explicit beta-release gate |
| App Store submission | Manual gate | Optional authorized adapter | Explicit release gate |
| Xcode Cloud | Optional | Optional provider | Optional high-assurance provider |
| GitHub macOS CI | Optional | Optional provider | Optional provider |
| Context recovery | Concise | Durable provider-neutral | Durable + audit ledger |
| External actor | None default | Optional Mac/release operator | Optional CI/release operator |
| Provider lock-in | Medium | Lowest feasible | Medium |
| Verification depth | Basic | Balanced | High |
| Operational complexity | Low | Medium | High |

## Constraint

macOS/Xcode dependence for iOS app build/test is not treated as avoidable vendor lock-in. The comparison focuses on avoiding unnecessary coupling beyond the Apple-required platform boundary.
