# AGENTS.md — Repository-wide instructions

You are an engineering/operations agent working on an API-first, MCP-native Agent-as-a-Service product. **This is the authoritative root instruction file.** Additional AGENTS.md files are permitted only immediately inside services/<service>/.

## Boot protocol (every worker, including Gas Town clones)
1. Find the Git root. Read this file, PRODUCT.md, ARCHITECTURE.md, DECISIONS.md, and the relevant ROADMAP.md milestone. Do not equate a worktree path with the canonical checkout.
2. Identify assigned Beads issue: use the installed bd CLI, inspect task dependencies and current claim. If Beads is uninitialized, report that fact and do not fabricate state.
3. If launched by Gas Town, verify the supported gt prime initialization and worktree/rig context. Do not assume every worker starts in the user's original root directory.
4. Locate target services, read their AGENTS.md and README.md, and follow service-local tests before modifying them.
5. Consult .agents/skills/<name>/SKILL.md for matching tasks; README files are directory indexes. Skill presence does not prove Codex discovery: test it.
6. Discover approved MCP/API operations from operations/, but treat configuration manifests as documentation, not live tool connections.

## Global invariants
- One GitHub monorepo, independent service build contexts, separate Coolify resources, versioned contracts, scoped data ownership; no global deployment Compose.
- Go preferred for new backend APIs and MCP. TypeScript/JavaScript for frontend. Preserve existing upstream Node/Python services unless explicitly approved.
- Connections holds provider secrets. No raw connection credentials or broad MCP catalogs in agent sandboxes.
- All external side effects require a **server-enforced, revision-bound authorization** with workspace, account, action, resource, parameter and expiry constraints. A diagram or prompt is never an authorization check.
- Workspace identity is canonical and must propagate across services; verify cross-tenant denial, revocation and service-to-service delegation.
- Open Flow owns workflow definitions, graph revisions, approvals and business orchestration. Job Runner owns generic durable execution/retries where used. Prove compatibility, do not wire blindly.
- Persist run state, human review checkpoints, event receipts and artifacts. Do not blindly retry non-idempotent actions.
- Provide deterministic/independent output validation; agent-written summaries alone are insufficient.
- Model usage and limits: LiteLLM. Logs: structured JSON via Alloy → Loki; durable security/business audits are separate. No secrets or document contents in logs.
- No production mutation without an explicitly scoped approval, rollback approach and post-change verification. Read-only diagnosis by default.
- Keep all keys in runtime secret stores. Commit example env names only. Do not log, print, or commit token values.

## Current execution order
**First:** complete Connections → Open Flow proof in engineering/spikes/01-connections-openflow.md. Start with a low-risk, authorized read, then a controlled action; test cross-workspace denial, connectionName selection and account mapping. Do not claim direct compatibility until real API tests pass. Better Auth migration is being completed in Connections by the owner; integration must adapt to the resulting identity contract.

**Second:** evaluate superradcompany/microsandbox on the actual home-lab virtualization host and compare with the existing BoxLite Provider adapter; runtime is not yet selected. **Later:** artifact exchange + human review + Word/edit capability + V2 conversation.

## Engineering loop
Upstream research → record spec/ADR → Beads dependency tasks → Gas Town assigns isolated worktrees → implement bounded change → automated checks → independent review → staging integration → permitted production rollout → Loki/health verification → evidence-linked completion.
Never invent a passing test or live deployed state. Report exact changed files, observed evidence, blockers and rollback. Separate mocks from real integration.

## Work ownership
services/ is code; engineering/ is design/evidence; operations/ is agent-access documentation/runbooks; capabilities/ is customer workload assets; .agents/skills/ is Codex engineering skills. Existing source in other repositories is **not yet imported** merely because a service folder exists.

