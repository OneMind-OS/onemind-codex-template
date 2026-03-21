---
title: "Tech Stack Decisions"
type: reference
status: active
created: 2026-01-10
owner: zeus
tags: [type/reference, domain/ge, topic/tech]
ai_summary: "Current technology stack — OpenClaw, NATS, Agno, Obsidian, Todoist, Home Assistant, and why each was chosen"
---

# Tech Stack Decisions

## Overview

Technology choices for the One Mind system. Every tool must earn its place — if a plain markdown file can do the job, we don't add a tool.

## Current Stack

| Layer | Tool | Why |
|-------|------|-----|
| **Knowledge** | Obsidian | Local-first, plain markdown, git-syncable |
| **Tasks** | Todoist | Fast capture, natural language, API for agents |
| **Agents** | OpenClaw | Multi-agent gateway, extensible skills |
| **Worker agents** | Agno AgentOS | Python-native, team composition |
| **Messaging** | NATS JetStream | Fast pub/sub, durable streams, cross-runtime |
| **Smart home** | Home Assistant | Local control, massive device support |
| **Database** | PostgreSQL + pgvector | Relational + vector search for agent memory |
| **Automation** | n8n | Visual workflow builder, self-hosted |
| **Voice** | LiveKit | Real-time audio/video, low latency |
| **Version control** | Git + GitHub | The codex is a git repo — everything is versioned |

## Guiding Principles

1. **Plain text first** — The codex is markdown. No proprietary formats.
2. **Self-hosted preferred** — Own the infrastructure when possible
3. **API access required** — If agents can't read/write it, it doesn't make the stack
4. **Replaceable** — Every tool should be swappable without losing data
