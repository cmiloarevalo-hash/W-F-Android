# TASK 02 — Android capability matrix

Status: EXPERIMENTAL COMPARISON INPUT — NOT CANONICAL

Legend: **Core** = required by candidate; **Optional** = extension; **Deferred** = outside normal path; **Manual gate** = human/authorized operator boundary.

| Capability | Candidate 1 — Minimal | Candidate 2 — Portable | Candidate 3 — Verified |
|---|---|---|---|
| Persistent authority/state in GitHub | Core | Core | Core |
| Gradle wrapper as automation surface | Core | Core | Core |
| Toolchain pin/compatibility record | Basic | Core | Core + audited |
| Kotlin-first for greenfield | Recommended | Recommended | Recommended |
| Compose for new UI where applicable | Recommended | Recommended | Recommended |
| Existing Views support | Yes | Yes | Yes |
| Host-side build sandbox | Core | Core, provider-neutral contract | Core, hardened/ephemeral |
| Local unit tests | Core | Core | Core |
| Android lint in CI | Core | Core | Core, blocking |
| Debug build/assemble check | Core | Core | Core |
| Release compile/package check without prod secrets | Optional | Core when relevant | Core when relevant |
| Compose/View UI tests | Targeted | Targeted | Risk-based suite |
| Instrumented tests | Small smoke set / change-driven | Pluggable device runner | Required risk-based tier |
| Gradle Managed Devices | Optional | Adapter option | Core virtual-device option |
| Physical device testing | Deferred/manual | Provider adapter | Optional matrix for high-risk paths |
| Firebase Test Lab | Not required | Optional adapter | Optional high-assurance adapter |
| Provider-specific CI | Avoided | Behind runner adapter | Allowed only with explicit evidence/contract |
| Secrets in source/build files | Forbidden | Forbidden | Forbidden + audited secret boundary |
| Upload/release key use | Manual gate | Manual/authorized release adapter | Isolated release gate |
| Play Console publication | Manual gate | Manual/authorized adapter | Manual/authorized, separately approved |
| Play policy freshness check | Before release | Before release | Mandatory release gate |
| Artifact/evidence retention | Basic CI logs | Standard evidence bundle | Structured evidence + provenance |
| Context recovery | Issue + concise docs | Durable task/state/evidence files | Durable files + audit/checkpoint ledger |
| External actor | None by default | Optional provider/device operator contract | Optional device-lab/release operator contract |
| Long-horizon autonomous continuation | Limited | Supported by persistent state | Supported with stronger validation gates |
| Operational complexity | Low | Medium | High |
| Provider portability | Medium | High | Medium/High if adapters preserved |
| Verification depth | Basic | Balanced | High |

## Capability constraints

### Host build != device test
A runner that can execute Gradle/JDK/SDK tasks is not automatically capable of running accelerated Android emulators. Device capability must be verified independently.

### CI != approval
A green CI run supplies evidence. It does not grant release, merge, baseline-change, or canonical-adoption authority.

### Firebase != Android core
Firebase/Test Lab is an optional test provider. No candidate may make it mandatory merely because it is a Google product.

### Release signing != ordinary build
Production signing credentials and Play publication remain isolated from normal implementation/test runs.
