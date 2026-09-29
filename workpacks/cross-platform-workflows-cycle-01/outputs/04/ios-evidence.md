# TASK 04 — iOS evidence

Status: EXPERIMENTAL RESEARCH — NOT CANONICAL
Access date: 2026-09-27

## Claim ledger

| ID | Claim | Class | Evidence | Notes |
|---|---|---|---|---|
| I-01 | Xcode command-line tools such as xcodebuild/simctl ship with Xcode and require Xcode to be installed/selected. | EXTERNAL_FACT | https://developer.apple.com/documentation/xcode/xcode-command-line-tool-reference | HIGH |
| I-02 | Current Apple Xcode system requirements list Xcode 27 as released and Xcode 27.1/27.2 as beta; Xcode runs on supported macOS versions. | EXTERNAL_FACT | https://developer.apple.com/xcode/system-requirements | HIGH; version-sensitive |
| I-03 | Swift Testing is the modern Apple testing framework for Swift unit/integration tests; XCTest remains supported and is required for UI automation use cases. | EXTERNAL_FACT | https://developer.apple.com/documentation/testing ; https://developer.apple.com/documentation/xctest | HIGH |
| I-04 | xcodebuild can run selected test plans/suites/tests and produces .xcresult bundles. | EXTERNAL_FACT | https://developer.apple.com/documentation/xcode/running-tests-and-interpreting-results | HIGH |
| I-05 | Xcode supports testing on simulators and physical devices; Apple warns simulators do not reproduce all physical-device performance/features. | EXTERNAL_FACT | https://developer.apple.com/documentation/xcode/building-and-running-an-app | HIGH |
| I-06 | Provisioning profiles bind signing certificates, devices (where applicable), and bundle identifiers; App Store Connect provisioning is part of distribution. | EXTERNAL_FACT | https://developer.apple.com/documentation/appstoreconnectapi/profiles ; https://developer.apple.com/help/account/provisioning-profiles/create-an-app-store-provisioning-profile | HIGH |
| I-07 | TestFlight is an App Store Connect beta-distribution boundary; builds are uploaded to App Store Connect and external testing can require review. | EXTERNAL_FACT | https://developer.apple.com/help/app-store-connect/test-a-beta-version/testflight-overview | HIGH |
| I-08 | App Store Connect API can manage provisioning, TestFlight and app metadata/submission-related resources. | EXTERNAL_FACT | https://developer.apple.com/documentation/AppStoreConnectAPI | HIGH |
| I-09 | Since 2026-04-28, App Store Connect uploads must be built with Xcode 26+ using the iOS 26 SDK or corresponding platform SDK. | EXTERNAL_FACT | https://developer.apple.com/news/upcoming-requirements/ | HIGH; release-policy claim |
| I-10 | Apple has announced that starting April 2027 iOS/iPadOS submissions must use the iOS/iPadOS 27 SDK or later and target iOS 15+. | EXTERNAL_FACT | https://developer.apple.com/app-store/submitting/ | HIGH; future requirement |
| I-11 | Xcode Cloud provides Apple-hosted CI/CD for build, test and TestFlight/App Store workflows, but requires Apple Developer Program/account setup. | EXTERNAL_FACT | https://developer.apple.com/documentation/xcode/xcode-cloud ; https://developer.apple.com/documentation/xcode/setting-up-your-project-to-use-xcode-cloud | HIGH |
| I-12 | GitHub-hosted Actions offers macOS runners, including macOS 26 and xcode-27 preview labels as of the checked documentation. | EXTERNAL_FACT | https://docs.github.com/en/actions/reference/runners/github-hosted-runners | HIGH; hosted image labels are volatile |
| I-13 | Swift source/package logic can be designed to be testable outside iOS UI/runtime surfaces, but iOS application build/sign/simulator execution remains Xcode/macOS-bound. | INFERENCE | I-01..I-05 | HIGH architectural inference |
| I-14 | Apple-service coupling is partly unavoidable at distribution/signing boundaries but avoidable in core task/state/evidence orchestration. | INFERENCE | I-06..I-11 | HIGH architectural inference |

## Platform boundary

### Portable layer
Can include:
- repository/task state;
- Swift package/domain logic where platform-independent;
- source review/static reasoning;
- provider-neutral evidence schema.

### macOS/Xcode layer
Required for:
- iOS app compilation with Apple SDKs;
- xcodebuild-driven app/test workflows;
- iOS Simulator;
- archive/export and signing workflows.

A Linux runner must not be described as an iOS app build runner unless it delegates the Apple build step to macOS.

## Test ladder

1. Swift Testing / XCTest unit tests for pure/domain logic.
2. xcodebuild build/test for affected schemes.
3. simulator integration/UI tests.
4. selected physical-device testing for hardware/performance/real-device behavior.
5. archive/export/signing validation.
6. TestFlight/App Store validation for release candidates.

## Signing/release boundary

- Signing certificates/private keys and provisioning material are secrets/controlled assets.
- Ordinary implementation environments should not receive production distribution credentials by default.
- TestFlight/App Store upload is a separately authorized release/beta action.
- Current Xcode/SDK submission requirements must be checked at release time.

## CI/provider implications

Possible macOS build providers include:
- local/self-hosted Mac;
- GitHub Actions macOS runner;
- Xcode Cloud;
- another authorized macOS CI provider.

Xcode Cloud is useful but not a mandatory core dependency.

## Community evidence

No community report is used as a material capability fact in TASK 04. Operational claims about CI cost/flakiness remain project-specific until measured or separately sourced.
