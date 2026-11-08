# Agent bootstrap and control

## Standalone Codex
Start in a checkout of this repository. Read root AGENTS.md. Verify project-level skills in .agents/skills/ are discovered in your Codex session. Follow the assigned Bead, then service AGENTS.md when changing a service.

## Beads
Install Beads using its current official instructions (https://github.com/gastownhall/beads). Use installed 'bd help' to verify commands and initialize via the supported CLI; do not handcraft .beads data. Verify a harmless task can be created, dependencies inspected and state persisted across fresh agent sessions.

## Gas Town
Install using official current documentation (https://github.com/gastownhall/gastown). Configure this Git repository as a rig in an external Town. Town/HQ state stays where Gas Town creates it; workers may use separate clones or worktrees. With Codex, verify gt prime is invoked using the supported wrapper / installed bootstrap rather than assuming the built-in preset loads it automatically. Inspect 'gt help' before a real assignment.

## Safety
Do not enable global dangerous approval bypass flags as a workaround for missing tooling. Use short-lived scoped credentials, separate dev/prod access, least-privilege MCP registrations and verified read-only probes. Never store tokens in the repository.

## Acceptance
A fresh independent worker reads root AGENTS.md, correctly discovers .agents/skills/, loads one service AGENTS.md, sees an assigned Bead, and produces a traceable dry-run report without production mutations.

