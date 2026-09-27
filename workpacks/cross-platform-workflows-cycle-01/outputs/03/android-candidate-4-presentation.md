# Android Candidate 4 — Presentation proposal

STATUS: PROPOSAL — NOT CANONICAL  
Derived from: Candidates 1–3 + TASK 03 comparison  
Authority: Issue #2 does not authorize adoption.

## Proposal name

**Risk-Tiered Portable Android Workflow**

## Design objective

Provide a default Android agent workflow that is:
- reproducible and recoverable across sessions/providers;
- strict about authority, secrets and release boundaries;
- verification-heavy when risk requires it;
- deliberately lightweight for ordinary low-risk changes;
- not dependent on Firebase, a specific CI vendor, Android Studio automation, or a specific coding-agent vendor.

## Core governance

```text
AUTHORIZED WORK ITEM
→ minimal context reconstruction
→ change plan / acceptance criteria
→ bounded implementation
→ host verification
→ risk classifier
   ├─ host-only evidence sufficient
   └─ device evidence required → device adapter
→ evidence bundle
→ review / checkpoint
→ independent merge/release authority
```

Rules:
1. Work Item defines authority and write scope.
2. Agent capability does not expand authority.
3. GitHub/repository artifacts provide durable state; chat memory is non-authoritative.
4. CI/test success is evidence, not approval.
5. Candidate/proposal status never becomes canonical automatically.

Trace: Workpack invariants I-01..I-07, I-13..I-14; OpenAI source register OAI-01, OAI-02, OAI-04, OAI-05.

## Environment contract

A project adopting this proposal records:
- Gradle wrapper version;
- AGP version and compatibility source;
- JDK/toolchain version;
- compileSdk/targetSdk/minSdk;
- Kotlin and Compose/version-management strategy;
- required SDK components;
- deterministic build/test/lint commands;
- network/dependency policy.

Default principle: pin project versions and verify compatibility; do not encode "latest" as an invariant.

Trace: Android evidence A-04, A-05, A-06.

## Android architecture default

For greenfield native Android:
- Kotlin-first;
- Compose preferred for new UI;
- UDF/state-holder separation;
- business/data logic kept host-testable where practical.

Existing Java/View projects remain valid inputs; migration is not required merely to satisfy this workflow.

Trace: A-01, A-02, A-03.  
Inference: maximizing host-testable logic reduces unnecessary device-test dependence.

## Mandatory host verification

Unless the project specifies stricter checks, every implementation checkpoint runs:
1. relevant local/JVM tests;
2. Android lint;
3. relevant compile/assemble/build task.

A release-affecting change additionally proves the release variant can be produced without exposing production secrets.

Trace: A-07, A-08, A-09, A-15.

## Risk classifier for device testing

Device evidence is required when the change materially affects:
- Compose/View behavior not covered by host tests;
- Android framework integration;
- permissions/intents/services;
- database/framework behavior requiring device semantics;
- lifecycle/configuration changes;
- hardware/sensor/camera/Bluetooth/vendor behavior;
- compatibility across API/form factors;
- release-critical user journeys.

The selected matrix is the smallest one justified by the risk, not automatically every supported API level.

Trace: A-07, A-10, A-11; Candidate 1 simplicity contribution; community A-19/A-20 used only as friction signals.

## Device adapter

Provider-neutral inputs:
- app/test artifacts;
- artifact hashes;
- runner;
- device/API/ABI/form factor;
- test selection;
- retry/flaky policy;
- timeout.

Provider-neutral outputs:
- pass/fail/skip;
- device metadata;
- logs/reports/screenshots where applicable;
- provider matrix/run ID;
- retry history.

Allowed implementations:
- attached device;
- local emulator / Gradle Managed Device;
- authorized cloud runner with virtualization;
- Firebase Test Lab;
- another authorized device farm.

Never assume a host build sandbox can run an Android emulator.

Trace: A-11, A-12, A-13, A-14.

## Secrets and release domain

Normal implementation/test context must not possess production signing authority unless explicitly required.

Release gate:
1. re-check current Play target/API/account/policy requirements;
2. produce and identify release AAB;
3. use protected upload/signing material in an authorized release context;
4. retain artifact/signing evidence;
5. require explicit human/Supervisor/release authority for Play rollout.

With Play App Signing, distinguish upload key from Google-held app-signing key.

Trace: A-15, A-16, A-17, A-18.

## CI topology

```text
PR/checkpoint
├─ HOST: unit + lint + build
├─ DEVICE: only when risk classifier requires
└─ EVIDENCE: structured summary
      ↓
independent review
```

Broader device matrices may run pre-release/nightly if per-change execution is disproportionate, but this must be an explicit project rule.

Inference based on verification/cost trade-off; no universal external cost claim is made.

## Context recovery

Stable repository governance stays concise. Task-specific evidence stays with the active Work Item/output.

Minimum recovery set:
- active Work Item;
- current branch/ref and checkpoint history;
- repository instructions relevant to the task;
- environment contract;
- last verified evidence;
- unresolved risks/decisions.

Trace: OAI-04, OAI-08 and invariants I-05/I-19.

## Optional external actor contract

No external actor is mandatory.

If one is needed:

- CAPABILITY: exact missing capability (for example remote physical-device matrix).
- PRECONDITIONS: authorized provider/account, artifacts, matrix, budget/quota permission.
- AUTHORIZED OPERATIONS: submit/run/retrieve only the named operation.
- FORBIDDEN OPERATIONS: source edits, authority changes, production release unless separately authorized.
- EXPECTED BASELINE: repository ref + artifact hashes + config.
- EVIDENCE RETURNED: machine-readable result, run IDs, logs/artifacts.
- STOP CONDITIONS: credential/billing/policy requirement not authorized; unsupported environment; inconsistent artifact.
- ESCALATION PATH: Supervisor/Human.

Trace: invariant I-17 and Android evidence A-13/A-14.

## What Candidate 4 intentionally does not require

- Firebase.
- Google Cloud beyond normal Android/Play dependencies.
- a particular CI vendor.
- a particular coding-agent vendor.
- a local Android emulator for every change.
- a full device/API matrix on every PR.
- production signing credentials in ordinary CI.
- automatic Play publication.
- self-approval or auto-merge.

## Trade-offs

Benefits:
- retains Candidate 2 portability;
- retains Candidate 3 security/verification depth;
- preserves Candidate 1 low-cost default path;
- keeps provider/device complexity risk-based.

Costs:
- requires a maintained risk classifier;
- adapter/evidence schemas add documentation;
- high-risk changes can still require expensive/slow device evidence;
- release policy remains externally volatile.

## Verification trace summary

| Material rule | Basis |
|---|---|
| Kotlin-first / Compose preferred for greenfield | A-01, A-02 |
| UDF/state separation | A-03 |
| pinned compatible toolchain + explicit JDK | A-04, A-05 |
| host unit/lint/build gate | A-07, A-08, A-09 |
| device tests only when device semantics matter | A-07, A-10, A-11 + explicit inference |
| emulator capability must be verified | A-12 |
| cloud device lab optional | A-13, A-14 |
| protected signing/release domain | A-15, A-16 |
| Play policy freshness at release | A-17, A-18 |
| durable task context and bounded execution | OAI-01, OAI-02, OAI-04, OAI-08 |
| CI evidence != approval | Workpack invariant I-13/I-14 + OAI-09 |

All material rules are traced to evidence or explicitly labeled inference above.
