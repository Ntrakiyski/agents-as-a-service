# ARCHITECTURE — Contracts before components

**Status:** target design, unproven where explicitly marked.

## Services and ownership
| Service | Responsibility | Technology / source |
|---|---|---|
| connections | Workspace-scoped provider accounts, encrypted credentials, action gateway | Existing Ntrakiyski/connections; Better Auth migration pending |
| open-flow | Workflow drafts, revisions, graph, approvals and execution routing | Existing oomol-lab/open-flow (beta); integration requires proof |
| job-runner | Generic durable queue, scheduling, retries, events | Existing Ntrakiyski/workflow-agents release candidate |
| sandbox-provider | Approved workload lifecycle, execution and isolation | Existing Python/BoxLite adapter; Microsandbox candidate |
| capability-api | Workspace-aware capability discovery, run/review/artifact API | New Go service, not yet implemented |
| mcp-server | Thin authenticated remote MCP surface over capability API | New Go service, not yet implemented |
| frontend | Catalog and later chat | TypeScript/React, not yet implemented |

One repo but every service gets its own Dockerfile, release, health endpoint, migrations and Coolify resource. Never silently deploy all services for a single path change.

## Crucial first compatibility boundary
Open Flow's connector proxy and team model may assume OpenConnector endpoints and x-oo-team-id while **our Connections** resolves workspace identity from its authenticated tokens and requires explicit connectionName per action. Do not pass arbitrary workspace/team headers from a caller. Verify the real endpoints, payloads, identity mapping, connector service credentials and denied operations against deployed test instances. Add a thin adapter only if necessary. See engineering/spikes/01-connections-openflow.md.

## Execution flow (target)
Principal -> Capability API / authenticated MCP -> workspace authorization -> immutable capability/workflow revision -> policy grant -> Open Flow -> bounded connector gateway or Job Runner -> Sandbox Provider -> limited agent profile -> artifact store/validators -> scoped result. All protected connector action invocations must be reauthorized server-side against the approved revision, even when triggered through Open Flow, CLI, MCP or background jobs.

## Security rules
- Connection tokens never enter a sandbox; sandbox receives task-scoped data and narrow capabilities.
- Workspace/grants bound to authenticated identity; cross-workspace list, invoke and download must be denied.
- Authorized actions specify account, operation, resources, parameter constraints, expiry and approver.
- Preserve idempotent receipts for non-replayable effects; retries reconcile ambiguous results.
- Human review questions have persisted request IDs, deadlines, response authorization, resume/checkpoint semantics and cancellation.
- File input/output uses immutable hashes, scoped temporary transfer, object storage, separate validation and lineage.
- Keep ordinary JSON logs in Loki and security audit records in durable storage. LiteLLM tracks inference/budget controls, not application service logs.

## Boundaries not yet proved
Connections ↔ Open Flow API compatibility; Better Auth post-migration claims; independently running Agent Review; real artifact import/export; self-hosted Microsandbox KVM/security; Coolify build isolation; reliable recovery after external actions. Tests are specified in engineering/spikes, not presumed successful.

