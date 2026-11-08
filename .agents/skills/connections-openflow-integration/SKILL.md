---
name: connections-openflow-integration
description: Use for the first product integration spike: wiring existing Connections to Open Flow with verified tenant and action boundaries.
---

# connections-openflow-integration

Read engineering/spikes/01-connections-openflow.md; inspect actual source versions/OpenAPI. Map Open Flow's expected Connector proxy/team routing versus Connections' runtime token/workspace and explicit connectionName. Build a compatibility matrix before touching code. Prove read-only action in disposable workspace, then denied wrong workspace/account/action. Do not spoof x-oo-team-id to force a pass. Capture redacted response schemas/audits and propose smallest adapter only if needed.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next GitHub issue or task and approvals required. Never claim an untested integration succeeded.

