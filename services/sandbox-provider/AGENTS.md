# Service instructions — sandbox-provider

**State:** Placeholder; source code has not been imported into this new monorepo.

Existing Python/BoxLite provider; non-stable artifact transfer/recovery. Compare real host Microsandbox before adding adapter; require quotas, pinned images, egress denial, durable output and cleanup. Do not assume KVM works inside Coolify container.

## When working here
1. Read root AGENTS.md and sandbox-provider/README.md, assigned Bead and relevant integration contract.
2. Verify exact upstream version, license and deployed source before importing or modifying existing implementation.
3. Keep builds, tests, migrations, health checks, OCI image, environment and Coolify deployment independent.
4. Record cross-service API contract changes before implementation; require compatible clients and security-negative cases.
5. Provide test commands, CI evidence, configuration examples, deployment and rollback instructions when code exists.
6. Do not copy secrets, claim live readiness from docs or create nested AGENTS.md files.

