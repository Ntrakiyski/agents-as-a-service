# Service instructions — open-flow

**State:** Placeholder; source code has not been imported into this new monorepo.

Existing beta Open Flow. Inspect pinned upstream docs/contracts and current connector proxy requirements before implementation. Prove x-oo-team-id versus Connections identity and approval semantics. Do not invent bypass auth headers.

## When working here
1. Read root AGENTS.md and open-flow/README.md, assigned Bead and relevant integration contract.
2. Verify exact upstream version, license and deployed source before importing or modifying existing implementation.
3. Keep builds, tests, migrations, health checks, OCI image, environment and Coolify deployment independent.
4. Record cross-service API contract changes before implementation; require compatible clients and security-negative cases.
5. Provide test commands, CI evidence, configuration examples, deployment and rollback instructions when code exists.
6. Do not copy secrets, claim live readiness from docs or create nested AGENTS.md files.

