---
id: codex-interface
title: "Codex Interface — Universal Entry Point"
type: system
status: active
created: 2026-01-01
owner: "{your-name}"
tags: [type/system, domain/codex]
ai_summary: "Entry point for any agent or human navigating this vault — read first"
---

# Codex Interface

> **Read this file first.** Whether you're a human setting up for the day or an AI agent dropped into a new session — this is where you start.

---

## What This Is

This is a **One Mind Codex** — a structured knowledge base in plain Markdown, organized using the CODEX method (Capture → Organize → Direct → Execute → × Multiply). It is the single source of truth for all knowledge, decisions, plans, relationships, and operations.

**Format**: Markdown + YAML frontmatter + `[[wiki-links]]` + tags
**Storage**: Git repository (versioned, portable, forkable)
**Editor**: Obsidian (optional — works in any text editor or AI system)

---

## How It's Organized — 4 Quadrants

```text
00-24  SO  — Sovereign Operations      Tech, AI, infrastructure, architecture
25-49  HP  — Holistic Performance      Health, money, identity, skills, relationships
50-74  LE  — Legacy Evolution          Family, home, children, estate
75-99  GE  — Generational Entrepreneurship  Business, ventures, wealth
```

Each domain group contains **numbered domain folders**. Each domain folder has a `README.md` explaining what lives there.

---

## Navigation Map

### For Humans

| Need | Where to go |
|------|------------|
| **Brand new? Start here** | [`QUICK-START.md`](../QUICK-START.md) — 30-minute guided setup |
| Starting fresh | `00-24 SO/00 Framework (Doctrine)/README.md` |
| Daily log | `_codex/templates/daily.md` → save to your HP or SO domain |
| Capture something fast | Drop it in `00-24 SO/06 Inbox (Queue)/` |
| Set a goal | `_codex/templates/goal.md` |
| Track a task | `_codex/templates/task.md` |
| Make a decision record | `_codex/templates/decision.md` |
| Start a project | `_codex/templates/project.md` |
| Track a metric | `_codex/templates/metric.md` |
| Run a weekly review | `_codex/templates/review.md` |
| Find a contact | `25-49 HP/32 Relationships/` |

### For AI Agents

**Loading order:**
1. Load all files in `_codex/system/` — these are always-on pinned context
2. Read this file (`INTERFACE.md`) for vault structure
3. Read `_codex/CONVENTIONS.md` for naming/tagging rules
4. Use `ai_summary` frontmatter fields to decide which files to open
5. Only open full files when the summary isn't sufficient

**Key principles:**
- Never create top-level folders — route to existing domains
- Unknown items go to `06 Inbox (Queue)/`
- Owner's identity and active goals are in `_codex/system/`
- Use `[[wiki-links]]` for cross-references

---

## The CODEX Method

```text
C — CAPTURE    Everything that enters your awareness enters the vault
O — ORGANIZE   Route it to the right domain and apply the right template
D — DIRECT     Command: decide what matters, assign operators, define done
E — EXECUTE    Do the work, delegate to AI, complete tasks
× — MULTIPLY   Review, measure, extract lessons — each cycle compounds value
```

This is a loop, not a checklist. You run it daily (micro), weekly (review), and quarterly (planning). The × step multiplies the system's intelligence with every cycle.

---

## System Health

Signs your codex is working:
- `06 Inbox (Queue)/` is regularly processed and emptied
- `_codex/system/` has current goals (updated at least weekly)
- You're running weekly reviews using `_codex/templates/review.md`
- Notes have `ai_summary` filled in

Signs your codex needs attention:
- Inbox has 20+ unprocessed items
- `_codex/system/active-goals.md` is stale (> 2 weeks old)
- Files without `type` or `ai_summary` are accumulating

---

## Owner

> **Replace this section with your own info when you fork.**

This vault is maintained by **Zeus Delacruz** — builder of the One Mind framework.

- Website: [zeusdelacruz.com](https://zeusdelacruz.com)
- Community: [onemindcodex.com](https://onemindcodex.com)
