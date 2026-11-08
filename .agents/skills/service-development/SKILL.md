---
name: service-development
description: Use when building or modifying an independently deployed Go, TypeScript or Python service in this monorepo.
---

# service-development

Start from root AGENTS.md then the specific services/<name>/AGENTS.md. New backend defaults to Go; frontend uses TypeScript. Preserve existing Node/Python sources unless migration approved. Define healthcheck, migration, config example, Dockerfile and standalone tests. Run service-local checks and affected cross-service contract tests; capture commands/output. Never assume a directory placeholder contains imported application code.

## Output evidence
Report verified environment/version, affected paths, tests and actual results, unresolved risks, next GitHub issue or task and approvals required. Never claim an untested integration succeeded.

