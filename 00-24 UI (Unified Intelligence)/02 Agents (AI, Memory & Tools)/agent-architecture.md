---
title: "Agent Architecture — Multi-Agent Design"
type: note
status: active
created: 2026-01-20
owner: zeus
tags: [type/note, domain/ui, topic/agents]
ai_summary: "Multi-agent architecture with 9 specialized agents — Legacy as central intelligence, 8 domain agents"
---

# Agent Architecture — Multi-Agent Design

## The Core Idea

One general-purpose AI agent can't do everything well. Instead, I run a **central intelligence** (Legacy) supported by **8 domain-specific agents**, each responsible for a quadrant or sub-domain of life.

## Agent Roster

| Agent | Quadrant | Responsibility |
|-------|----------|---------------|
| **Legacy** | All | Central intelligence, orchestration, communication |
| **Spartan** | HP 27-28 | Body, fitness, physical mastery |
| **Oracle** | HP 25-26, 29-34 | Mind, money, meaning, personal growth |
| **Eden** | LE | Food growing, agriculture, sustainability |
| **Empire** | GE 75-84 | Business strategy, wealth building |
| **Haven** | LE 50-58 | Home, family, estate management |
| **Guardian** | UI 11 + HP 31 + LE 57 | Security, legal, protection |
| **Grid** | UI 00-12 | Infrastructure, DevOps, automation |
| **Trinity** | GE 75 + Community | Community building, public presence |

## How They Communicate

All agents connect through a message bus (NATS JetStream). Legacy dispatches tasks, agents report results. Every agent can read the codex for context.

## Why This Matters for Your Codex

The domain numbering system (00-99) maps directly to agent responsibilities. When you assign a domain to an agent, it knows exactly which folders to read, what context to load, and what kind of tasks it handles.
