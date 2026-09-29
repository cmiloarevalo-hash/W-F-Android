# TASK 08 — Platform deltas

STATUS: PROPOSAL — NOT CANONICAL

| Dimension | Android | iOS | Web |
|---|---|---|---|
| Primary build boundary | Gradle + JDK + Android SDK | macOS + Xcode + Apple SDK | Project-selected runtime/build system |
| Portable host execution | High for JVM/build tasks | Partial; pure Swift/domain may be portable, iOS app build is Mac-bound | Generally high, stack-dependent |
| UI/device verification | Emulator/physical Android device | Simulator/physical Apple device | Browser/E2E/real-browser/device |
| Special capability constraint | Emulator virtualization/device lab | Xcode/macOS required | Browser/runtime matrix |
| Release artifact | APK/AAB; usually AAB for Play | Archive/IPA/App Store Connect flow | Stack/provider-specific deploy artifact |
| Signing | Android upload/release signing | Apple certificates/profiles | Provider/TLS/package-specific; no universal app-signing equivalent |
| Distribution authority | Google Play/other stores/sideload depending project | TestFlight/App Store/enterprise as authorized | Hosting/deployment environment |
| First-party cloud option | Firebase Test Lab/Google services optional | Xcode Cloud optional | No universal first-party platform CI |
| Accessibility/UX boundary | Android accessibility/device UX | Apple accessibility/device UX | WCAG/browser + human UX review |
| Provider neutrality ceiling | High outside store/device services | Lower because Apple toolchain/distribution is unavoidable | High |
| Core external actor example | device-lab operator | Mac/device/release operator | browser/design/security/deploy operator |

## Non-symmetry rules

- Do not claim Android emulator capability merely because a host can compile.
- Do not claim Linux can natively build/test iOS apps because Swift runs on Linux.
- Do not treat web preview as equivalent to mobile store beta distribution.
- Do not invent a mobile-style signing gate for generic web deployments.
- Do not make Firebase, Xcode Cloud or a web host mandatory for symmetry.
- Do not force one verification matrix across platforms.
