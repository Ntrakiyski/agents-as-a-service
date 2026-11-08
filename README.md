<div align="center">

# Agents as a Service

### From asking AI to do the work — to actually getting it done.

**A platform for specialized AI capabilities that can use your tools, follow approved workflows, work inside isolated environments, and deliver results you can verify.**

**API-first · MCP-native · UI-optional · Sandbox-first**

[**The Vision**](PRODUCT.md) &nbsp;·&nbsp; [**Architecture**](ARCHITECTURE.md) &nbsp;·&nbsp; [**Roadmap**](ROADMAP.md)

</div>

---

> **Project status:** Early development. This repository currently contains the product blueprint, engineering instructions, integration plans, and service scaffolding—not a publicly available or production-ready platform. The experience below describes what we're building.

## AI should do more than answer questions

Most businesses already know how to use software. They spend their days updating spreadsheets, editing documents, preparing reports, moving information between tools, and repeating the same processes.

They don't need another chatbot that explains how to do those things.

**They need work to get done.**

Imagine asking AI to:

- **Update a Word document** without destroying the original formatting or company template.
- **Analyze five Excel workbooks**, reconcile the numbers, and deliver a finished report.
- **Build a presentation** using existing slides, brand assets, and source material.
- **Run a weekly process** that collects information, updates a report, checks the output, and sends it to the right people.
- **Spot work worth doing**, suggest a workflow, and wait for approval before taking action.

Not a tutorial. Not a collection of prompts. **A finished, reviewable result.**

That's the idea behind **Agents as a Service (AaaS)**.

## One platform. Many capabilities. Any interface.

Every capability is a focused, versioned way to accomplish a real task. It has defined inputs, outputs, tools, execution rules, and quality checks.

A person should be able to run it from whichever interface they already use:

| Interface | Experience |
|---|---|
| **Capability catalog** | Browse a library of tasks, upload files, add instructions, and receive a result. |
| **REST API** | Launch, track, and integrate capabilities from your own applications. |
| **Remote MCP** | Give ChatGPT, Claude, Hermes, or another compatible agent access to the same governed capabilities. |
| **Conversational workspace (planned V2)** | Tell one agent what you want. It discovers capabilities, proposes workflows, and coordinates the work for you. |

**The interface is optional. The capabilities are the product.**

## Designed around six layers

The platform is being designed as six connected layers, each with one clear responsibility.

| Layer | What it does |
|---|---|
| **01 · Identity & Workspace** | Give people and teams their own authenticated, isolated workspace. |
| **02 · Connections** | Securely connect the apps, accounts, and services they already use. |
| **03 · Capabilities** | Make specialized AI tasks discoverable, reusable, and versioned. |
| **04 · Workflow & Approval** | Show what will happen, in what order, with which permissions—and ask for approval where needed. |
| **05 · Sandbox Execution** | Run agent workloads inside isolated, resource-limited environments with narrowly scoped access. |
| **06 · Artifacts & Verification** | Deliver files, revisions, previews, validation evidence, and execution history. |

### Connect your tools. Don't hand the agent the keys.

Connecting Google Workspace, Microsoft 365, or a CRM should **not** grant an arbitrary sandbox agent access to every available action.

Our design follows a stricter principle:

> **An agent may perform only the actions authorized for the approved workflow, with the specified accounts, resources, and limits.**

Connections manage provider accounts and credentials. Open Flow defines business steps and approvals. A server-side policy boundary is responsible for enforcing the permitted actions. Sandboxed agents get only the access required to complete their assigned work.

The system is also designed for **human-in-the-loop reviews**. An agent can pause, ask a question, request a decision, and resume when the authorized user responds.

## From a capability library to an agent-native workspace

### V1 — Pick a task. Get a result.

The first product experience is a searchable library of capabilities.

Choose a task, describe the outcome, provide files or approved connections, and start a run. Follow its progress, respond to review requests, and access the finished artifacts and revisions.

**First planned document capability:** Edit an existing Word template while preserving its layout and validating the output.

### V2 — Just describe what you need.

Instead of manually choosing a capability, talk to a general-purpose agent.

It can identify the right capabilities, ask for missing information, build a workflow, and present the proposed steps for your approval. The approved workflow then coordinates execution.

The V1 library doesn't disappear. **It becomes the execution backbone of V2.**

### Work that doesn't need a new prompt every time

The architecture also supports four ways to initiate work:

- **Manual Runs** — Start a capability whenever you need it.
- **Scheduled Runs** — Execute approved workflows on a recurring schedule.
- **Event-Triggered Runs** — React to permitted events from connected services.
- **Proactive Suggestions** — Have agents identify useful next steps, without treating a suggestion as permission to act.

## Built as a platform, not one giant application

This is a **single GitHub monorepo** with **independently deployable services**, intended to run as separate Coolify resources. The services communicate through versioned APIs rather than sharing private databases or being bundled into one application-wide Docker Compose.

| Building block | Role |
|---|---|
| [**Connections**](https://github.com/Ntrakiyski/connections) | Governed access to external accounts, providers, and actions. |
| [**Open Flow**](https://github.com/oomol-lab/open-flow) | Workflow definition, orchestration, and approvals. |
| **Capability API + MCP Server** | The shared, authenticated interface to the capability library. |
| **Job Runner** | Durable jobs, scheduling, retries, and execution status. |
| **Sandbox Provider** | Isolated execution environments and workload lifecycle. |
| **LiteLLM** | Model routing, approved models, budgets, and usage visibility. |
| **Grafana Loki** | Centralized service and infrastructure logging. |
| **Artifact storage & validation** | Durable inputs, outputs, versions, and quality evidence. |

**Backend preference:** Go for new services; TypeScript/JavaScript for the frontend. Existing working services can retain their current language.

Sandbox technology is being evaluated rather than assumed: the current BoxLite-based provider is one baseline, and [Microsandbox](https://github.com/superradcompany/microsandbox) is a candidate for self-hosted execution.

## Built *by* agents, maintained *by* agents

The engineering process is agent-native too.

This repository is designed to be the central working context for coding and operations agents, not just a collection of source files. We use:

- [**Beads**](https://github.com/gastownhall/beads) for persistent, dependency-aware engineering tasks.
- [**Gas Town**](https://github.com/gastownhall/gastown) for coordinating multiple coding agents and isolated worktrees.
- **Project-level agent skills** in [`.agents/skills/`](.agents/skills/) for repeatable development, integration testing, reviews, deployment, and incident investigation.
- **Operational knowledge** in [`operations/`](operations/) for MCP/API discovery, service inventories, logs, permissions, and recovery procedures.

Agents are expected to research before building, work from explicit contracts, prove integrations with actual tests, review changes independently, and produce verifiable deployment evidence.

**Automation doesn't eliminate controls. It makes good controls more important.**

## Where we are now

The immediate priority is **proving the connection between Connections and Open Flow** using real, scoped test accounts and a simple workflow. That integration must demonstrate both a successful authorized action and failed unauthorized attempts.

After that, the plan is to qualify a sandbox runtime on the intended hardware, prove durable artifact exchange and human-review recovery, and build the first end-to-end document capability.

See the [current integration proof](engineering/spikes/01-connections-openflow.md), [sandbox evaluation plan](engineering/spikes/02-microsandbox-qualification.md), and [roadmap](ROADMAP.md). These are plans and acceptance gates, not claims that the integrations already work.

## Explore the project

| Document | Why it matters |
|---|---|
| [PRODUCT.md](PRODUCT.md) | Product vision, positioning, six layers, V1 and V2. |
| [ARCHITECTURE.md](ARCHITECTURE.md) | Service ownership, contracts, security boundaries, and execution flow. |
| [DECISIONS.md](DECISIONS.md) | The 20 architecture decisions that guide implementation. |
| [ROADMAP.md](ROADMAP.md) | Evidence-gated milestones and integration priorities. |
| [AGENTS.md](AGENTS.md) | Entry point and operating rules for coding and operations agents. |
| [services/](services/) | Service-level boundaries and instructions. |
| [engineering/](engineering/) | Research, ADRs, contracts, evaluations, and integration spikes. |
| [operations/](operations/) | Operational inventories, MCP references, policies, and runbooks. |

---

<div align="center">

### Less prompting. More completed work.

**Specialized agents. Approved workflows. Controlled execution. Verifiable outcomes.**

*Agents as a Service — an agent-native platform in development.*

</div>
