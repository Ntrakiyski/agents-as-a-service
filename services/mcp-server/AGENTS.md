# Service instructions — mcp-server

**State:** Placeholder; source code has not been imported into this new monorepo.

Planned Go adapter. Authenticated remote MCP discovery/launch/status/respond operations must invoke the same policy engine as REST. No arbitrary tool passthrough, direct downstream credentials or schema-as-authorization.

## When working here
1. Read root AGENTS.md and mcp-server/README.md, assigned task or GitHub issue and relevant integration contract.
2. Verify exact upstream version, license and deployed source before importing or modifying existing implementation.
3. Keep builds, tests, migrations, health checks, OCI image, environment and Coolify deployment independent.
4. Record cross-service API contract changes before implementation; require compatible clients and security-negative cases.
5. Provide test commands, CI evidence, configuration examples, deployment and rollback instructions when code exists.
6. Do not copy secrets, claim live readiness from docs or create nested AGENTS.md files.

