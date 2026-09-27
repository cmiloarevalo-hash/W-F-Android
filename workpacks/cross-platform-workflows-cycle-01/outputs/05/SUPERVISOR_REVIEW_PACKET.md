# SUPERVISOR REVIEW PACKET — iOS

STATUS: READY_FOR INDEPENDENT SUPERVISOR REVIEW

## Material assumptions
- native iOS app build/test remains a macOS/Xcode capability boundary;
- provider neutrality is meaningful around, not through, that Apple-required boundary;
- risk-tiered simulator/device testing is preferable to making every change run every device tier;
- production signing and App Store actions should remain isolated from ordinary implementation.

## Trade-offs
- Verified gives stronger evidence/security but higher macOS/device cost.
- Portable minimizes avoidable provider lock-in but adds adapter contracts.
- Minimal lowers ceremony but makes context/device decisions less systematic.
- Candidate 4 combines Portable + Verified while retaining a small default loop.

## Unresolved issues
- no concrete project exists to measure macOS CI duration/cost;
- physical-device matrix depends on actual app capabilities;
- signing ownership/team roles are project-specific;
- App Store requirements are volatile.

## Baseline differences
The frozen baseline names a web-specific AI_STUDIO_OPERATOR and web/Google-specific mechanisms. iOS Candidate 4 instead models a Mac build boundary and optional Apple-service operator. Governance separation is preserved; platform implementation detail is not copied mechanically.

## Semantic risks
1. Treating Apple-required Xcode dependence as avoidable vendor lock-in.
2. Treating Linux Swift support as proof of Linux-native iOS app build capability.
3. Treating simulator success as physical-device equivalence.
4. Treating CI signing ability as release authority.
5. Freezing current Xcode/App Store requirements into permanent workflow rules.
6. Accidentally making Xcode Cloud mandatory because it is first-party.
7. Propagating Workpack-specific no-local-clone rules into the generic iOS proposal.

## Sensitivity
Baseline: 71.8 / 84.2 / 89.2.
Ordering survives fixed weight scenarios; simplicity/cost narrows C3 vs C2.
Stability: CONDITIONALLY_STABLE.

## Review target
Assess whether Candidate 4 correctly distinguishes:
- unavoidable Apple platform constraints;
- avoidable provider coupling;
- simulator/device/release risk tiers.

Allowed Supervisor outcomes remain PASS | REWORK | HOLD | ESCALATE.
