# Spike 01 — Connections ↔ Open Flow interoperability

**Status: NOT RUN. First implementation gate.** Use disposable test identities and a read-only or otherwise harmless provider action. This file is a test plan, not a claim of API compatibility.

## Source systems
- Connections: https://github.com/Ntrakiyski/connections — independent Better Auth migration in progress; do not rewrite its identity stack here.
- Open Flow: https://github.com/oomol-lab/open-flow — beta, pin tested commit/tag.
- Open Flow connector docs: https://github.com/oomol-lab/open-flow/blob/main/docs/control/contracts/control-api.md
- Connections endpoints documented at its current /openapi.json and /mcp. Connections uses runtime bearer tokens and explicit connectionName for action dispatch.

## Why this spike matters
Open Flow references Connector Teams, uses operator-controlled Connector tokens and a team-resolving proxy; Connections derives workspace membership and runtime grants from its own authentication, with explicit account labels. Similar vocabulary does NOT guarantee request/body, endpoint, error, role or lifecycle compatibility.

## Procedure
1. Record source SHAs, versions and live deployment URLs separately. Prefer staging, not production. Create test workspace A and B with non-sensitive connections; record ownership.
2. Read Open Flow's expected Connector endpoints, auth headers, query semantics and response envelopes. Read Connections' actual OpenAPI, /mcp and runtime token handling. Produce a field-by-field matrix.
3. Configure Open Flow to use the isolated test Connections endpoint through supported configuration only. Do not bypass authorization by injecting x-oo-team-id or spoofed workspace headers.
4. Discover provider catalog, permitted connection identities and allowed action metadata from an Open Flow workflow/CLI client. Compare exact response shapes and statuses.
5. Run a **read-only, deterministic** action using explicit connectionName from workspace A. Confirm the same selected connection and workspace in Connections audit.
6. Negative cases: A token cannot list/use workspace B accounts; invalid connectionName fails; disallowed action fails; expired/revoked token fails; forged team header fails; account label spoofing fails.
7. Create draft Flow with one permitted action → deterministic code transform/output. Validate, run and inspect structured results. Optionally publish version only in disposable staging, with approval.
8. Verify a changed draft does not silently change published revision. Record approval and actor implications, including whether Flow can bypass the gateway.
9. Stop/delete only the test fixtures you created. Redact tokens and personal data from saved evidence.

## Pass criteria
- End-to-end authorized request succeeds on actual services.
- Unauthorized workspace/account/action calls fail at the server boundary.
- No raw provider credentials reach Open Flow graph, agent, guest or logs.
- Identity mapping, connectionName selection and error responses are verified and documented.
- Missing adapter or upstream changes are specified without modifying both products opportunistically.

## Record evidence under engineering/research/
Include: exact command/API call with secret-free headers, versions, public docs, status, response schema (redacted), trace/audit IDs, expected versus observed, limitations, and recommendation: **direct integration / narrow adapter / incompatible**.

