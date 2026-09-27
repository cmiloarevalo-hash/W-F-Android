# iOS Candidate 3 — Verified

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Maximize verification, security and auditability for long-horizon iOS work.

## Verification tiers

### Tier 0 — environment
- Xcode/macOS compatibility verified;
- schemes/dependencies resolved;
- no production signing secret in ordinary build context.

### Tier 1 — every checkpoint
- Swift unit/integration tests;
- xcodebuild affected scheme;
- retain .xcresult.

### Tier 2 — UI/platform
- simulator integration/UI tests;
- selected OS/device destinations.

### Tier 3 — physical/device-specific
- physical-device testing for camera, sensors, performance, push/background behavior or simulator gaps.

### Tier 4 — release candidate
- archive/export validation;
- protected signing/provisioning context;
- current App Store SDK requirement check;
- TestFlight evidence when authorized;
- no App Store release without explicit release authority.

## Security
- distribution key/certificate/private key isolated;
- Apple account/API credentials least-privilege;
- CI logs/artifacts checked for secret exposure;
- Xcode Cloud or third-party macOS CI is optional and explicitly authorized.

## Audit
Record Xcode version, destination, scheme, test plan, .xcresult, retries, artifact hash, signing mode and unresolved warnings.

## External actor
Optional Apple CI/release operator:
CAPABILITY = execute macOS/Xcode/device/release operation;
PRECONDITIONS = exact artifact/ref/account authority;
FORBIDDEN = source/scope/authority changes and unapproved publication;
EVIDENCE = build/test/release IDs and result artifacts.

## Baseline functional non-regression ledger

Candidate 3 remains **VERIFIED / AUDITABLE**. Stronger verification and audit evidence strengthen the Workflow but do not replace its authority model or Apple platform boundaries.

| Protected baseline guarantee | Status | Preserved behavior in Candidate 3 |
|---|---|---|
| 1. Work Item contract | PRESERVED WITH PLATFORM-SPECIFIC IMPLEMENTATION | The audited iOS Work Item retains Objective, Acceptance Criteria, Authorized Scope, Relevant Sources, Verification, and Base, with additional Xcode/macOS, scheme, destination, artifact and signing evidence layered on top. |
| 2. Semantic Scope + Path Scope | PRESERVED AS-IS | Every audited operation must be authorized both semantically and by path. Xcode, simulator/device, CI, signing or release capabilities cannot enlarge either scope. |
| 3. Exact-SHA Supervisor semantic review | PRESERVED AS-IS | Audit evidence records the exact commit SHA submitted for semantic review. Any later commit creates a new HEAD whose semantic acceptance must be reviewed again regardless of identical test or signing results. |
| 4. SEMANTIC_ACCEPTED / REWORK / HOLD / ESCALATE | PRESERVED AS-IS | These remain the independent Supervisor control states. Tiered tests, .xcresult, device evidence, provenance and audit logs cannot auto-produce or replace a semantic decision. |
| 5. Same-objective REWORK continuity | PRESERVED AS-IS | Corrections within the same Objective remain in the same Issue, branch and PR with evidence appended to the audit trail. Changes to Objective, Semantic Scope, Path Scope, authority or baseline semantics require escalation. |
| 6. Supervisor-only merge; SEMANTIC_ACCEPTED != MERGE_ELIGIBLE | PRESERVED AS-IS | The Implementer, CI and external actors never self-merge. SEMANTIC_ACCEPTED is exact-SHA and distinct from MERGE_ELIGIBLE. Where integration is authorized, the Supervisor merges only after exact-SHA semantic acceptance and baseline merge-eligibility checks. |
| 7. PUBLISH = HUMAN ACTION | PRESERVED AS-IS | Protected signing, provisioning, TestFlight upload, App Store Connect API capability or release automation do not create publication authority. **PUBLISH = HUMAN ACTION** unless explicitly changed by the Human. |
| 8. GitHub-based session recovery | PRESERVED AS-IS | GitHub persists Work Item, branch/ref and exact HEAD, PR, Xcode/environment fingerprint, verification/audit evidence, latest applicable Supervisor decision/reviewed SHA, retries/deviations and unresolved risks so a new session reconstructs state without prior transcript. |
| 9. Baseline functional non-regression gate | PRESERVED AS-IS | The verification/audit pipeline remains subordinate to this gate. Any unexplained loss, weakening, substitution or reinterpretation of a protected baseline function is a **HARD VETO** that deeper testing, stronger audit evidence or later scoring cannot compensate. |

iOS-specific semantics remain unchanged: native iOS build/test remains macOS/Xcode-bound; simulator and physical-device tiers remain distinct; signing certificates/private keys/provisioning remain isolated security assets; TestFlight/App Store actions remain separately authorized; Xcode Cloud and other Mac CI providers remain optional implementation choices.

## Strengths
Highest assurance and release-domain separation.

## Weaknesses
Highest macOS CI/device cost and operational complexity; can be excessive for small apps.
