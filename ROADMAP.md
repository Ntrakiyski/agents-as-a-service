# ROADMAP — Evidence-gated delivery

This is a dependency order, not a date-based sprint backlog. Use Beads for task graph and Gas Town for parallel engineering, not Jira-like rituals.

| Gate | Work | Evidence required |
|---|---|---|
| P0 | Connections + Open Flow integration | Real approved read/action; workspace and account isolation; exact endpoint mapping |
| P1 | Authentication / workspace contract | Better Auth migration completed externally; real membership, role and revocation checks |
| P2 | Sandbox evaluation | Microsandbox and current BoxLite evaluated on host; lifecycle, cost, egress and KVM |
| P3 | Durable artifact/review protocol | Upload/transform/download with checksums; pause/question/resume after restart |
| P4 | Capability API + remote MCP skeleton | Same authorization for REST and MCP; validated lifecycle |
| P5 | First document capability | Word template edit, structural/visual validation, repeat revisions |
| P6 | Scheduling and event automation | Permission-bound recurring runs, dedupe, revocation |
| P7 | V1 product UI | Authenticated catalog, requests, history, approvals, results |
| P8 | V2 chat orchestration | Conversational workflow proposal, visible graph and approval |
| P9 | Expand capability library | Excel/PPT/PDF/images, each with validators and resource profile |

## P0 is the immediate work
Read engineering/spikes/01-connections-openflow.md and upstream source. Wait for the finished Better Auth contract before locking production identity mapping; a local disposable test workspace can be used to test API shape now. Do not build a connector replacement or modify source until interoperability is demonstrated. Save exact versions, test evidence, negative outcomes and any adapter proposal.

## Engineering acceptance
Every task records scope, allowed paths, contract impact, exact tests, failure cases, security negatives, observable evidence and rollback. Existing repos are references, not implicitly imported. Anything depending on deployed state remains unverified until live inspection.

