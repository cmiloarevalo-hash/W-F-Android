# Web Candidate 2 — Portable

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Provider/framework-neutral contracts for long-lived portability.

## Adapters
- BUILD_TEST: runtime/package-manager/framework-specific commands.
- BROWSER_TEST: configured browser matrix and artifacts.
- PREVIEW: ephemeral URL + commit identity + expiry.
- DEPLOY: environment, artifact, authorization, evidence.
- EXTERNAL_ACTOR: optional bounded capability.

## Workflow
Portable governance and evidence schemas remain stable while adapters can be replaced.

Browser support is declared by project policy; MDN Baseline informs compatibility but does not replace testing.

Secrets:
- client receives only public/config values intended for exposure;
- server/deploy secrets live in protected runtime/environment stores;
- cloud auth may use short-lived/OIDC mechanisms where available.

Strengths: highest portability and recovery.
Weaknesses: adapter abstraction adds maintenance and cannot erase application-stack differences.
