---
name: sandbox-runtime-evaluation
description: Use when evaluating Microsandbox or another isolation runtime for the home lab and agent workloads.
---

# sandbox-runtime-evaluation

Read engineering/spikes/02-microsandbox-qualification.md. Inspect pinned upstream version/license. Verify host /dev/kvm and permission inside actual target process, not only host. Exercise OCI guest, CPU/memory limits, egress/private-IP denial, stop/restart, artifacts/checksums, failed-run reconciliation and cleanup. Compare existing BoxLite adapter; runtime not selected until real tests pass. No privileged Docker or host socket shortcuts.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next GitHub issue or task and approvals required. Never claim an untested integration succeeded.

