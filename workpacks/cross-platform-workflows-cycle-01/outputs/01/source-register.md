# TASK 01 — Source register

Status: EXPERIMENTAL RESEARCH REGISTER — NOT CANONICAL  
Access date for external web sources: 2026-09-27

## A. Project-authoritative sources

| ID | Source | Authority/use | Mutability for Implementer |
|---|---|---|---|
| P-01 | GitHub Issue #2 | Sole Workpack authority; role, scope, sequence, STOP conditions | Issue comments only as authorized; authority cannot be changed by Implementer |
| P-02 | `workpacks/cross-platform-workflows-cycle-01/REPOSITORY_ACCESS.md` | Binding repository-access contract | Writable only within Workpack authority; not modified in TASK 01 |
| P-03 | `workpacks/cross-platform-workflows-cycle-01/WORKPLAN.md` | Persistent execution sequence and review cadence | Workpack path, but no change required in TASK 01 |
| P-04 | `workpacks/cross-platform-workflows-cycle-01/STATE.md` | Persistent task/gate state | Updated only as part of task checkpoint |
| P-05 | `AGENTS.md` | Read-only governance context | READ ONLY |
| P-06 | `PROGRAM.md` | Read-only program design context | READ ONLY |
| P-07 | `references/README.md` | Frozen baseline provenance/write policy | READ ONLY |
| P-08 | `references/WORKFLOW_BASE_ORIGINAL.md` | Frozen historical baseline | READ ONLY; modification forbidden |
| P-09 | `cmiloarevalo-hash/G_INF_01` pinned historical source | Historical reference only | READ ONLY |

## B. Current official OpenAI sources

| ID | Source | Type | Material use in TASK 01 | Freshness note |
|---|---|---|---|---|
| OAI-01 | https://openai.com/business/guides-and-resources/how-openai-uses-codex/ | OpenAI official guide | Well-scoped tasks, Issue-like prompts, persistent AGENTS.md context, Best-of-N, iterative environment setup | Re-verify when used for product-specific behavior |
| OAI-02 | https://openai.com/index/running-codex-safely/ | OpenAI security article, 2026-05-08 | Sandbox boundaries, approvals, network controls, agent-native telemetry/audit | Current as checked 2026-09-27 |
| OAI-03 | https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex | OpenAI Developers cookbook, 2026-05-09 | Persistent objective, completion conditions and constraints | Current as checked 2026-09-27 |
| OAI-04 | https://developers.openai.com/blog/run-long-horizon-tasks-with-codex | OpenAI Developers article | Durable project memory, milestone verification, scoped execution | Current as checked 2026-09-27 |
| OAI-05 | https://openai.com/index/open-source-codex-orchestration-symphony/ | OpenAI engineering article, 2026-04-27 | Task tracker as control plane, dedicated workspaces, human-review handoff | Current as checked 2026-09-27 |
| OAI-06 | https://developers.openai.com/api/docs/guides/agents | OpenAI Developers docs | Durable sessions/orchestration and separation from tools/execution environment | HIGH volatility; re-check when used later |
| OAI-07 | https://developers.openai.com/api/docs/guides/agents/sandboxes | OpenAI Developers docs | Scoped mounted inputs/outputs and artifact checking | HIGH volatility; re-check when used later |
| OAI-08 | https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra | OpenAI Developers article, 2026-09-11 | Avoid stale/bloated instructions; read context relevant to the task | Recent guidance; re-check if model guidance changes materially |
| OAI-09 | https://developers.openai.com/blog/custom-code-review-rules-for-codex | OpenAI Developers article, 2026-07-20 | Agent review complements rather than replaces tests, branch protections and required approvals | Current as checked 2026-09-27 |

## C. Community evidence in TASK 01

No community source is used to establish a material technical fact in TASK 01. The methodology defines how community evidence will be collected in later platform tasks: as complementary evidence for operational friction/counterexamples, with primary-source cross-checking for capability, security, compatibility, pricing and policy claims.

## D. Source handling rules

- URLs in this register identify the source; later outputs must cite the specific claim they support.
- A source entry is not blanket evidence for every statement about a product.
- Current-state claims must preserve version/date scope.
- If a source conflicts with another, register the contradiction and resolve or STOP if material.
- Source count is not a proxy for evidence quality.
