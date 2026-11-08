---
name: contract-boundary-review
description: Use when a change crosses microservice APIs, modifies authorization, or affects event and artifact schemas.
---

# contract-boundary-review

Identify authoritative owner of every field, ID and state machine. Compare existing OpenAPI contracts, replay/idempotency, authentication, tenant mapping and error semantics. Add negative tests for cross-tenant data, unauthorized tool actions, impersonation and revision mismatch. An agent tool schema is not a policy. Record versioned contract changes and rollback plan; request approval for breaking changes.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next GitHub issue or task and approvals required. Never claim an untested integration succeeded.

