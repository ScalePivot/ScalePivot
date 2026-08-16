<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./hero-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./hero-light.svg">
  <img alt="JUNSHU Security open-source visual identity" src="./hero-light.svg" width="100%">
</picture>

# JUNSHU Security

### The Security Control Plane for AI Agents

Open-source security infrastructure for agents, tools, MCP, and autonomous runtime.

钧枢安全 · 智能体运行时安全

<code>Agent Security</code>&nbsp; <code>Runtime Security</code>&nbsp; <code>MCP Security</code>&nbsp; <code>Open Source</code>

**Observe &rarr; Understand &rarr; Decide &rarr; Control**

</div>

## Security at the Point of Execution

Prompt security is only the beginning. The real security boundary emerges when an agent starts acting: reading files, invoking tools, executing code, accessing credentials, controlling browsers, or coordinating sub-agents.

JUNSHU Security is designing an open-source control plane for continuous security decisions across agent identity, context, behavior, tools, runtime state, graphs, and policy. The work is at an early foundation stage; the architecture and repositories below describe the intended direction, not production readiness.

## Agent Security Control Plane

<picture>
  <source media="(prefers-color-scheme: dark) and (max-width: 600px)" srcset="./control-plane-mobile-dark.svg">
  <source media="(prefers-color-scheme: light) and (max-width: 600px)" srcset="./control-plane-mobile-light.svg">
  <source media="(prefers-color-scheme: dark)" srcset="./control-plane-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./control-plane-light.svg">
  <img alt="Agent action flows through a runtime sensor, identity and context, behavior graph, detection, policy decision, and enforcement" src="./control-plane-light.svg" width="100%">
</picture>

This is not only a `Prompt -> Model -> Output Filter` pipeline. Security decisions continue as the agent acts and its runtime context changes.

## What We Protect

| Security domain | Protected surfaces |
| --- | --- |
| **Identity** | Agents, sessions, credentials, delegated authority, sub-agents |
| **Runtime** | Shell and code execution, processes, checkpoints, runtime state |
| **Tools** | Agent tools, MCP servers, MCP tools, browser actions, external APIs |
| **Data** | Files, memory, context, resources, secrets, sensitive output |
| **Graph** | Agent-to-agent communication, tool relationships, execution lineage |
| **Behavior** | Action sequences, historical context, anomalies, cross-agent activity |
| **Policy** | Intent, permissions, risk thresholds, approval requirements |
| **Response** | Allow, ask, redact, block, sandbox, isolate |

## Security Architecture

| Observe | Understand | Decide | Control |
| --- | --- | --- | --- |
| Runtime telemetry | Identity and authority | Detection engines | Policy enforcement |
| Tool and MCP calls | Context and memory | Behavior correlation | Runtime isolation |
| Process and file access | Agent security graph | Continuous risk | Containment and response |

Core research and engineering areas include identity security, context security, tool and MCP security, runtime and memory security, agent graph security, behavioral detection, policy enforcement, and runtime isolation.

### Runtime Decision Flow

```text
Agent Action
     |
Runtime Observation
     |
Context Enrichment
     |
Risk Detection
     |
Policy Decision
     |
     +------ ALLOW
     +------ ASK USER
     +------ REDACT
     +------ BLOCK
     +------ SANDBOX
     +------ ISOLATE
```

Every decision can incorporate current action, historical context, cross-agent relationships, and live runtime state.

## Agent Security Graph

The planned security graph connects the entities required to explain risk, trace authority, and enforce decisions across long-running execution.

```text
Agent --owns--> Session --executes--> Task --invokes--> Tool
  |                 |                    |              |
Identity         Memory              Process       MCP Server
  |                 |                    |              |
Policy <------- Finding <---------- Resource <----- Credential
```

> **Single action + historical context + cross-agent relationship + runtime state = continuous risk**

## Open Source Projects

The namespace is intentionally quiet while security models, interfaces, and release boundaries are designed. These repositories are **planned**; they have not been presented as stable or production-ready.

<details>
<summary><strong>View the planned repository matrix</strong></summary>

| Repository | Display name | Purpose | Primary language | Priority | Suggested license | Status |
| --- | --- | --- | --- | --- | --- | --- |
| `agentsec` | JUNSHU AgentSec | Security control plane and shared contracts | Go | P0 | Apache-2.0 | Planned |
| `runtime` | JUNSHU Runtime | Runtime sensing, enforcement, and isolation | Rust | P0 | Apache-2.0 | Planned |
| `engines` | Detection Engines | Modular detection and risk evaluation | Python | P0 | Apache-2.0 | Planned |
| `sdk` | JUNSHU SDK | Agent and framework integration contracts | Multi-language | P0 | Apache-2.0 | Planned |
| `agent-graph` | Agent Security Graph | Runtime entities, lineage, and risk correlation | Rust | P1 | Apache-2.0 | Planned |
| `mcp-security` | MCP Security | MCP server, tool, and resource security | TypeScript | P1 | Apache-2.0 | Planned |
| `benchmark` | Agent Security Benchmark | Reproducible evaluation scenarios and metrics | Python | P1 | Apache-2.0 | Planned |
| `datasets` | Security Datasets | Curated benchmark and research data | Data | P2 | CDLA-Permissive-2.0 | Planned |
| `examples` | Integration Examples | Framework and runtime integration patterns | Multi-language | P2 | Apache-2.0 | Planned |
| `docs` | Documentation | Architecture, threat models, and operator guides | Markdown | P1 | CC-BY-4.0 | Planned |

Naming follows the GitHub namespace: short repository names are preferred over repeated brand prefixes.

</details>

## Research Areas

| Runtime and identity | Tools and ecosystems | Graph and behavior |
| --- | --- | --- |
| Agent runtime security | MCP security | Agent graph security |
| Agent identity and delegation | Tool invocation security | Behavioral detection |
| Memory and checkpoint security | Autonomous execution security | Long-running agent risk |
| Context integrity | Browser and code execution | Security benchmarks |

Research outputs will aim to connect defensible threat models with reproducible engineering artifacts. Claims, benchmarks, and datasets will be published only when their methodology and provenance can be reviewed.

## Security Philosophy

> **The model proposes. The runtime acts. Security must govern the action.**

Once an agent can affect files, processes, credentials, browsers, tools, APIs, or other agents, the effective security boundary moves from the model to the runtime. JUNSHU Security focuses on observable actions, contextual risk, explicit policy decisions, and enforceable outcomes.

## Open Source Roadmap

No release dates are implied. Status reflects direction, not delivery commitments.

| Phase | Focus | Current status |
| --- | --- | --- |
| **1 · Foundation** | Profile, architecture, documentation, SDK contracts, security model | Designing |
| **2 · Runtime** | Runtime sensor, telemetry, policy, SDK | Exploring |
| **3 · Graph** | Agent graph, behavior analysis, risk correlation | Planned |
| **4 · Ecosystem** | MCP, framework integrations, examples, benchmarks, datasets | Planned |

## Community and Security

- Read the [contribution guidelines](https://github.com/ScalePivot/.github/blob/main/CONTRIBUTING.md) before proposing a change.
- Follow the [Code of Conduct](https://github.com/ScalePivot/.github/blob/main/CODE_OF_CONDUCT.md) in all project spaces.
- Use the [support guide](https://github.com/ScalePivot/.github/blob/main/SUPPORT.md) to choose the right channel.
- Report vulnerabilities privately according to the [security policy](https://github.com/ScalePivot/.github/blob/main/SECURITY.md). Do not disclose vulnerabilities in public issues.

---

<div align="center">

**JUNSHU Security · 钧枢安全**

Security infrastructure for the agentic era.

<sub>The visual mark in this repository is a temporary open-source GitHub identity, not a declaration of final corporate trademark artwork. Project names and brand identifiers are not licensed for endorsement or impersonation.</sub>

</div>
