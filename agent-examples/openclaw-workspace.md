---
title: OpenClaw Workspace Integration
type: example
domain: agent
tags: [openclaw, workspace, agent, integration]
ai_summary: Shows how an OpenClaw agent workspace connects to a codex vault — boot context, skill procedures, semantic search, and daily logs.
---

# OpenClaw Workspace Integration

How an [OpenClaw](https://github.com/openclaw/openclaw) agent workspace connects to and operates on a codex vault.

## Overview

OpenClaw agents run inside a **workspace** — a directory of markdown files and Node.js skill packages that define the agent's behavior. The codex serves as the agent's long-term knowledge base, indexed for semantic search and written to during daily operations.

## How It Works

### Boot Context

When the OpenClaw gateway starts, the agent loads its workspace files:

- **SOUL.md** — Personality, tone, values, boundaries
- **AGENTS.md** — Operating instructions and dispatch rules
- **USER.md** — Owner profile and preferences
- **TOOLS.md** — Tool usage guidance
- **BOOT.md** — Startup ritual (runs once on gateway restart)

These map conceptually to `_codex/system/` — they're the agent's pinned context that's always loaded.

### Skill Procedures

OpenClaw skills are Node.js packages in the `skills/` directory. Codex skills map to these:

| Codex Skill | OpenClaw Equivalent |
|-------------|-------------------|
| `_codex/skills/capture.md` | Inbox routing + `write` tool |
| `_codex/skills/organize.md` | File move/rename + frontmatter update |
| `_codex/skills/search.md` | `memory_search` (semantic + BM25 hybrid) |
| `_codex/skills/reflect.md` | Heartbeat routine + daily log generation |

### Semantic Search

OpenClaw's `memory_search` indexes the entire codex:

- **Provider**: OpenAI text-embedding-3-small
- **Search**: Hybrid (BM25 keyword + vector semantic, 0.7/0.3 weight)
- **MMR**: Enabled (diverse results, not just top-similarity)
- **Sync**: Watch mode — auto-reindex when files change

The agent searches the codex when it needs context for a task, decision, or conversation.

### Writing Back

The agent writes to the codex in two ways:

1. **Daily logs** — Written to `memory/YYYY-MM-DD.md` in the workspace, then routed to codex domains
2. **Direct writes** — Using `write` and `edit` tools to create or update codex notes

All writes follow codex conventions (frontmatter, naming, domain routing).

### Heartbeat

A recurring routine (e.g., every 30 minutes) where the agent:

1. Checks a proactive task list (HEARTBEAT.md)
2. Scans for items that need attention
3. Writes observations to the daily log
4. Routes actionable items to the appropriate codex domain

## Sample Directory Structure

```
agent-workspace/
├── SOUL.md                    ← personality (like _codex/system/IDENTITY.md)
├── AGENTS.md                  ← instructions (like _codex/CONVENTIONS.md)
├── USER.md                    ← owner profile
├── TOOLS.md                   ← tool guidance
├── BOOT.md                    ← startup ritual
├── HEARTBEAT.md               ← proactive check list
├── memory/                    ← daily logs
│   ├── 2026-03-18.md
│   └── 2026-03-19.md
├── skills/                    ← Node.js tool packages
│   ├── nexus-bridge/          ← cross-runtime dispatch
│   ├── home-assistant/        ← smart home control
│   └── github-api/            ← GitHub access
└── lobster/                   ← named automation routines

codex/                         ← the knowledge base (indexed by memory_search)
├── _codex/                    ← meta layer
│   ├── system/                ← boot context
│   ├── skills/                ← procedures
│   └── templates/             ← note templates
├── 00-24 UI/                  ← tech & infrastructure notes
├── 25-49 HP/                  ← health & personal notes
├── 50-74 LE/                  ← family & legacy notes
└── 75-99 GE/                  ← business & wealth notes
```

## Key Patterns

### Workspace ↔ Codex Separation

The workspace is the agent's **runtime config** — personality, tools, routines. The codex is the **knowledge base** — notes, decisions, projects, reference material. They're separate directories, connected by search indexing and file write paths.

### Agent Writes Follow Conventions

When the agent creates a codex note, it uses the standard frontmatter:

```yaml
---
title: Meeting Notes — Q2 Planning
type: log
domain: business
tags: [meeting, planning, q2]
created: 2026-03-19
ai_summary: Quarterly planning meeting covering revenue targets and hiring timeline.
---
```

### Multi-Agent Support

Multiple agents can share the same codex. Each agent has its own workspace but reads from and writes to the shared codex. A file watcher (e.g., `codex-watch` service) auto-commits changes and syncs across machines.

## Getting Started

1. Install OpenClaw: `npm install -g openclaw`
2. Set up a workspace with SOUL.md, AGENTS.md, USER.md
3. Point `memorySearch.extraPaths` to your codex directory in the gateway config
4. Set `watch: true` for auto-reindexing
5. Start the gateway: `openclaw gateway`

The agent will index the codex on startup and begin using it for context in conversations.
