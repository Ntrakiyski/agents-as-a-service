# Incident response — agent-operated, read-only first

1. Authenticate operations identity and inspect operations/inventory to identify service owner, environment and allowed tool path. Verify live revision independently from Git main.
2. Get correlation ID, time range, workspace-safe identifier and failing operation. Query Grafana/Loki via approved read-only MCP/API with bounded time windows and labels. Redact payloads, PII, tokens.
3. Compare deploy status, service health, dependency latency and LiteLLM model usage where relevant. Model usage is not service logging; durable audit data is separate from Loki.
4. Form a falsifiable hypothesis and gather evidence. Create/attach a Bead and have Gas Town assign scoped investigation/review if code changes are required.
5. For remediation, record exact target, risk, rollback, owner approval and verification checks. Do not restart/destroy/rotate/redeploy without authorization.
6. Verify restored behavior with independent probes, check error rates and audit actions. Record cause, fix, evidence and follow-up task.

