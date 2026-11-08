# Agent bootstrap and control

## Standalone Codex or other coding agent
Start in a checkout of this repository or locate its root from an isolated worktree. Read root AGENTS.md, PRODUCT.md, ARCHITECTURE.md, DECISIONS.md and the relevant service AGENTS.md. Verify project-level skills in .agents/skills/ are discovered in the current agent session.

## Work coordination
Use scoped GitHub issues and pull requests when tracking cross-service work. Each change must have a concrete problem statement, allowed paths, acceptance checks, independent review when warranted, and verifiable evidence. Isolated branches/worktrees are optional and do not require an external orchestration system.

## Operations
Use operations/inventory and operations/mcp to discover approved systems. Configuration files are documentation, not live MCP registrations. Verify exact available tools and scopes before making changes.

## Safety
Do not enable global dangerous approval bypass flags as a workaround for missing tooling. Use short-lived scoped credentials, separate dev/prod access, least-privilege MCP registrations and verified read-only probes. Never store tokens in the repository.

## Acceptance
A fresh independent worker reads root AGENTS.md, discovers .agents/skills/, loads the target service AGENTS.md, identifies the assigned task and produces a traceable dry-run report without production mutations.
