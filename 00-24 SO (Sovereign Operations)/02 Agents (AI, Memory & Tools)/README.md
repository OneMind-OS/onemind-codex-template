---
id: so-02-readme
title: "Agents (AI, Memory & Tools)"
type: index
status: active
created: 2026-01-01
owner: zeus
tags: [domain/so, folder/02, type/index]
ai_summary: "Index for AI agents, memory systems, and tool configs in this vault"
---

# 02 — Agents (AI, Memory & Tools)

> Your AI team lives here. Configs, memory, roles, and tool inventories.

---

## What Lives Here

Every AI agent you work with gets a file here. That file tells the agent who it is, what it's responsible for, and what tools it has access to. It also serves as documentation for *you* — so you know exactly what your AI setup looks like.

- Agent configuration files
- Memory system documentation
- Tool inventories and descriptions
- Platform-specific setups (OpenClaw, Cursor, ChatGPT, etc.)
- Agent interaction logs and evaluations

---

## Agent File Structure

Each agent gets its own file following this pattern:

```yaml
---
title: "{Agent Name}"
type: reference
tags: [domain/so, type/agent-config]
ai_summary: "Config for {agent name} — role, tools, memory setup"
---

# {Agent Name}

## Role
{What this agent does in your life}

## Tools
{List of tools/skills available}

## Memory
{How memory is configured}

## Interaction Guidelines
{How to work with this agent effectively}
```

---

## Zeus's Agents (Example)

| Agent | Role | Platform |
|-------|------|----------|
| **Legacy** | Primary AI — runs everything, central intelligence | OpenClaw |
| **Spartan** | Body & physical mastery | OpenClaw |
| **Oracle** | Mind, money & meaning | OpenClaw |
| **Empire** | Business & wealth | OpenClaw |
| **Haven** | Home, family & estate | OpenClaw |

My full agent configs are in the subfolders here. Legacy is the main agent — always on, handles all communication channels, coordinates the other agents.

---

## Getting Started

1. Document whatever AI tools you currently use — even just ChatGPT
2. Note what you use each one for
3. As your setup grows, add config files for each agent
