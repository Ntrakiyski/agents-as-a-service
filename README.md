# Agents as a Service — Agent Platform Engineering

**Status: architecture and integration scaffold; no platform code or deployment claimed.**

One GitHub monorepo for an API-first, MCP-native, UI-optional Agent-as-a-Service product. Each service is deployed independently in Coolify. Root-level Codex/Gas Town workers coordinate engineering through Beads; the product delivers permission-bound workflows and isolated capabilities.

## Start here
- [AGENTS.md](AGENTS.md) — authoritative instructions for all agents, including Gas Town worktrees
- [PRODUCT.md](PRODUCT.md) — product vision and six user-facing layers
- [ARCHITECTURE.md](ARCHITECTURE.md) — technical boundaries and workflow authorization
- [DECISIONS.md](DECISIONS.md) — 20 binding design decisions
- [ROADMAP.md](ROADMAP.md) — integration-first delivery gates
- [engineering/spikes/01-connections-openflow.md](engineering/spikes/01-connections-openflow.md) — first real proof

## Directory map
| Directory | Responsibility |
|---|---|
| services/ | Independently deployable products; per-service AGENTS.md |
| capabilities/ | Customer-facing, versioned agent tasks and validation |
| engineering/ | ADRs, research, contracts, specs, integration spikes and evals |
| operations/ | MCP/API inventory, safe access, logs, configuration references, runbooks |
| .agents/skills/ | Project-level Codex skills for agent engineering |
| deploy/ | Per-service Coolify resources and pinned delivery manifests |
| tests/ | Cross-service integration, contracts and security negative tests |

**Current integration priority:** Connections → Open Flow. Connections' migration to Better Auth is being completed separately; do not rewrite or assume migration is finished. Evaluate Microsandbox separately; no sandbox runtime is selected yet.

Repository content documents proposed contracts; it is not proof of deployed readiness. Do not commit credentials or client data.

