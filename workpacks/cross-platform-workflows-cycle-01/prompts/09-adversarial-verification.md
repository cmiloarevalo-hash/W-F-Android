# TASK 09 — Adversarial verification and contradiction audit

## OBJECTIVE
Attempt to falsify the material assumptions of Tasks 01–08 before presentation.

## REQUIRED OUTPUTS
- `outputs/09/contradiction-audit.md`
- `outputs/09/baseline-traceability.md`
- `outputs/09/source-freshness-audit.md`
- `outputs/09/semantic-propagation-risks.md`
- `outputs/09/rework-required.md`

Explicitly test for the failure observed in the prior experiment: a semantic error that survives several later tasks.

If a prior candidate contains a correctable error inside this workpack scope, record the required correction and update the affected experimental output transparently; do not rewrite history silently.

## VERIFICATION
Every correction must cite the detected contradiction and affected outputs.

## CHECKPOINT COMMIT
`workpack cycle 01 task 09: adversarial verification`

## NEXT TASK
10 only if no unresolved STOP condition remains.
