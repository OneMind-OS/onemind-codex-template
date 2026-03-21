---
title: "System — Pinned Context"
type: system
status: active
created: 2026-03-19
owner: zeus
tags: [type/system, domain/codex]
ai_summary: "Rules for the _codex/system/ hot zone — files always loaded into agent context"
---

# System — Pinned Context

Files in this directory are **always loaded** into the agent's context window at the start of every interaction. This is the "hot zone" — the most essential files the agent needs regardless of task.

---

## Rules

1. **Keep it small** — Total size should stay under 2,000 tokens. Every token here is consumed on every interaction.
2. **Only facts, not procedures** — Put "how to" instructions in `_codex/skills/`. System holds "what is" context.
3. **Agent-managed** — Agents can move files in and out of `system/` as they learn what's most relevant.
4. **Human override** — Owner can lock files in `system/` by adding `pinned: true` to frontmatter.

## What Belongs Here

- Active goals and priorities (the 3-5 things that matter right now)
- Identity context (who the owner is, core preferences)
- Critical reference data that's needed in >50% of interactions

## What Does NOT Belong Here

- Procedures and SOPs (use `_codex/skills/`)
- Historical logs (use domain folders)
- Large reference documents (use L1/L2 tiered loading)
- Anything over 500 tokens (summarize it instead)

## Self-Organization

Agents are encouraged to manage `system/` contents:
- **Promote**: If a file is accessed in >50% of recent sessions → consider moving to `system/`
- **Demote**: If a `system/` file hasn't been relevant in 7+ days → move it back to its domain folder
- **Summarize**: If a needed file is too large, create a summary version here and keep the full version in its domain
