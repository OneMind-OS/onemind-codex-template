---
id: ui-09-readme
title: "09 Automation — Workflows & n8n"
type: index
status: active
created: 2026-01-13
owner: zeus
tags: [domain/ui, type/index, domain/automation]
ai_summary: "Automation workflows, n8n pipelines, scheduled tasks, and trigger-based operations"
---

# 09 Automation — Workflows & n8n

> *Let the machines do the repetitive work. You focus on the thinking.*

## Purpose

This domain tracks every automated workflow in the OneMind system — n8n pipelines, scheduled tasks, NATS-triggered automations, and recurring operations that run without human input.

---

## What Lives Here

```text
09 Automation (Workflows)/
├── n8n/                 # n8n workflow documentation
├── Schedules/           # Cron jobs and scheduled tasks
├── Triggers/            # Event-driven automation rules
└── Logs/                # Automation run logs and outcomes
```

## Key Workflows

| Workflow | Trigger | Frequency | Status |
|----------|---------|-----------|--------|
| Morning Briefing | 6:00 AM | Daily | Active |
| Weekly Review Prep | Sunday 8 PM | Weekly | Active |
| Codex Sync | File change | Real-time | Active |
| Invoice Generator | Month end | Monthly | Active |

## Tools

- **n8n** — visual workflow builder (self-hosted on VPS)
- **NATS JetStream** — event bus for trigger-based flows
- **Cron** — system-level scheduled tasks
- **Webhooks** — inbound triggers from external services

## Quick Links

- [n8n Dashboard](http://localhost:5678)
- [NATS Monitor](http://localhost:8222)
