---
name: coolify-operations
description: Use when inspecting, deploying, verifying or rolling back independently managed services in Coolify.
---

# coolify-operations

Begin with operations/inventory and policies; discover exact current Coolify project, environment, resource ID and deployed SHA through authorized read-only MCP/API. One repo does NOT imply one Compose. Build and deploy only affected service with explicit context. Confirm health, logs, migrations, dependency compatibility and rollback. Production changes require scoped approval. Do not confuse main branch with deployed release or silently alter other resources.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next Beads task and approvals required. Never claim an untested integration succeeded.

