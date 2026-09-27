# Web Candidate 1 — Minimal

STATUS: CANDIDATE — EXPERIMENTAL — NOT CANONICAL

## Intent
Small framework-neutral workflow with a credible verification floor.

```text
Issue/task
→ identify frontend/backend scope
→ implement
→ lint/type/unit
→ integration/build
→ targeted browser E2E
→ optional preview
→ human UX review when visual behavior changes
→ review/deployment gate
```

Rules:
- use repository-native commands; do not impose npm/framework choices;
- never put secrets in browser code;
- run browser tests only where behavior warrants them;
- deployment and production secrets remain separately authorized;
- preview is optional evidence, not approval.

Strengths: simple, low lock-in, low ceremony.
Weaknesses: thinner audit trail and less systematic cross-browser/security coverage.
