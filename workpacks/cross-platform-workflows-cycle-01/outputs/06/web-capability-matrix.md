# TASK 06 — Web capability matrix

Status: EXPERIMENTAL COMPARISON INPUT — NOT CANONICAL

| Capability | Candidate 1 Minimal | Candidate 2 Portable | Candidate 3 Verified |
|---|---|---|---|
| Framework-neutral governance | Core | Core | Core |
| Project build/test command contract | Simple | Explicit adapter | Explicit/audited |
| Unit/integration tests | Core | Core | Core |
| Multi-browser E2E | Targeted | Pluggable | Risk-tiered/blocking |
| Accessibility | Basic automated + review | Contract | Automated + human gate |
| Preview environment | Optional | Provider adapter | Controlled evidence environment |
| Secrets | No client secrets | Provider-neutral secret interface | Least privilege + OIDC where possible |
| Frontend/backend boundary | Documented | Explicit interface | Explicit + threat/evidence checks |
| Deployment | Manual/authorized | Deployment adapter | Protected deployment domain |
| Provider lock-in | Low/medium | Low | Medium if richer provider integrations |
| Context recovery | Concise | Strong | Strong + audit |
| External actor | None default | Optional preview/design/operator | Optional security/design/deploy operator |
| Operational complexity | Low | Medium | High |
| Verification depth | Basic | Balanced | High |
