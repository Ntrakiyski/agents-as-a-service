# DECISIONS — Binding baseline (ADR changes required)

| ID | Decision |
|---|---|
| D01 | One monorepo; separately deployed Coolify services |
| D02 | API-first, MCP-native, UI-optional |
| D03 | Canonical workspace identity across services, independently tested |
| D04 | Versioned capability manifests and schemas |
| D05 | Connections owns credentials and scoped account access |
| D06 | Open Flow owns business graph/revisions; Job Runner owns generic queue execution |
| D07 | Immutable approved workflow revision and server-enforced action grants |
| D08 | Sandbox runtime selected only after real host/e2e evaluation |
| D09 | Agent-initiated Human Review Request as durable checkpoint |
| D10 | Immutable versioned artifacts and independent validation |
| D11 | LiteLLM gateway for models, usage, budgets and approved aliases |
| D12 | Manual, scheduled, event-triggered and proactive run modes |
| D13 | Pinned agent, model alias, skill, image, tool and workflow versions |
| D14 | Deterministic policy enforcement outside LLM prompts and MCP schemas |
| D15 | Loki/Alloy structured logs + separate durable audit trail |
| D16 | Spec/ADR and reproducible acceptance criteria for risky changes |
| D17 | Project skills at .agents/skills/ and verified discovery |
| D18 | Beads + Gas Town for dependency-aware agent engineering |
| D19 | Contract/security/e2e checks and staging gates before promotion |
| D20 | Agent-operated read-only diagnosis; gated production mutations |

**Unproven is not accepted:** Open Flow/Connections compatibility, finished Better Auth identity migration, approved external side effects, sandbox isolation, artifact recovery, cross-workspace negative tests, Codex/Gas Town bootstrapping and independent deployments.

Deviations: write a new entry under engineering/adr/ with alternatives, migration and verification; do not quietly rewrite the decision.

