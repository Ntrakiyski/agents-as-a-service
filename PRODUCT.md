# PRODUCT — Agent-as-a-Service

## Positioning
**Business model:** Agent-as-a-Service. **Product category:** AI Capability Platform. **Execution model:** sandboxed, permission-constrained tasks with validated outputs. **Design:** API-first, MCP-native, UI-optional.

The platform exposes narrow capabilities that deliver real work, not unrestricted chat-based tool access. External clients (ChatGPT, Claude, Hermes, other MCP/REST agents) must receive the same workspace authorization as our own UI.

## Six product layers
1. **Identity & Workspace** — authenticated users, teams, memberships, workspace grants.
2. **Connections** — governed accounts and tools; provider tokens stay server-side.
3. **Capabilities** — versioned task catalog, accepted inputs, outputs, validators, skills.
4. **Workflow & Approval** — Open Flow revisions, visible action graph, authorizations and schedules.
5. **Sandbox Execution** — isolated task-specific agents; least-privilege tools.
6. **Artifacts & Verification** — durable outputs, previews, versions, reproducible checks.

## Two versions
- **V1:** searchable capability catalog; users submit requests/files, review status, answer human-review questions and download validated results.
- **V2:** a conversational agent discovers capabilities and proposes Open Flow workflows; users inspect/approve the graph and use the same execution backend. The catalog remains available.

## Run modes
Manual Run, Scheduled Run, Event-Triggered Run and Proactive Suggestion. A proactive suggestion is not authorization for an external side effect. Human Review Request is an agent-initiated checkpoint; Workflow Approval authorizes an action graph and its scopes.

## Initial proof and first customer capability
First prove **Connections + Open Flow** with a real account and permission tests. Then evaluate the sandbox runtime, artifact transfer and durable review before building first full customer capability: edit an existing Word template with high-fidelity validation.

## Non-goals for this scaffold
No implemented product UI, no hosted multi-tenant production claims, no real credentials or MCP configuration, and no copy/import of existing upstream source without a separate, licensed and version-pinned migration task.

