# Spike 02 — Microsandbox vs current Sandbox Provider

**Status: NOT RUN. Runtime candidate, not selected.**

Candidate: https://github.com/superradcompany/microsandbox (verify exact installed release, license and upstream API). Existing baseline: Ntrakiyski/workflow-agents Python Sandbox Provider with BoxLite Cloud adapter and incomplete scoped artifact transfer/recovery.

## Real target qualification
- Identify actual GMKtec host OS / hypervisor topology and whether /dev/kvm is exposed to the *service process*, not just host.
- Run a documented disposable OCI guest with unprivileged service permissions. Confirm CPU/memory/disk quotas, isolated kernel, lifecycle and cleanup; pin image digest and recorded runtime version.
- Deny egress and test private/link-local/metadata address access, including DNS and redirects. Do not infer network isolation from an SDK option.
- Test guest stop/start after service restart; checkpoint/recovery, stale process handles, duplicate-create and failed execution cases.
- Copy source fixtures into guest and retrieve output bytes through approved scoped transfer. Compare SHA-256 before/after; verify no unrestricted host mounts or secret leakage.
- Inspect SDK/Go API suitability and cost/resource overhead under concurrent lightweight Office jobs. Measure, do not assume high concurrency on 64GB host.
- Compare Micrsosandbox/Microsandbox service API surface to existing Provider adapter; propose *versioned adapter* rather than rewrite.
- Record any licensing, privilege, portability or vendor limitations.

## Exit
A result matrix with actual commands, deployed/tested versions, evidence, blockers, and recommendation (select / defer / reject). No production code migration without passing host and security tests.

