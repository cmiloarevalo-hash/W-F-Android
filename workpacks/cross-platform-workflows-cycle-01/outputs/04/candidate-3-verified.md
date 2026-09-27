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

## Strengths
Highest assurance and release-domain separation.

## Weaknesses
Highest macOS CI/device cost and operational complexity; can be excessive for small apps.
