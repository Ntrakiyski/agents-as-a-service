---
name: loki-incident-response
description: Use when investigating service errors or recurring production incidents with Grafana Loki/Alloy logging.
---

# loki-incident-response

Read operations/logging and incident runbook. Use read-only authenticated Grafana/Loki queries. Start with time range, service/environment, correlation ID; never high-cardinality user IDs as Loki labels. Cross-check audit store, Coolify deployment and LiteLLM only for inference usage. Redact secrets/customer data. Escalate fixes through a GitHub issue, independent tests, approval and verified rollout.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next GitHub issue or task and approvals required. Never claim an untested integration succeeded.

