# Operational approval matrix (proposed policy)

| Action | Agent default | Requirement |
|---|---|---|
| Read repository, contract, non-sensitive health | Allowed | Scoped read identity |
| Read Loki bounded service logs | Allowed when tool granted | Authenticated read-only; redact tenant data |
| Draft Beads tasks or pull requests | Allowed | Traceable repo identity |
| Run tests in isolated worktree | Allowed | Disposable test env only |
| Deploy to staging | Conditional | Reviewed change, staging credentials, rollback |
| Deploy/rollback production | Human approved | Exact service/ref and post-deploy verification |
| Modify workspace/connector grants | Human approved | Exact account/action/resource scope |
| Delete production sandboxes or data | Human approved | High-impact change, backup and recovery proof |
| Rotate secrets | Human approved | Explicit target, dual-key/rollback strategy |

Business workflow approval and human-review question answering are separate protocols from these engineering operations approvals.

