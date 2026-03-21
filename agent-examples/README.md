---
title: "Agent Examples"
type: index
status: active
created: 2026-03-19
tags: [type/index, domain/codex]
ai_summary: "Index of agent integration examples — OpenClaw, Cursor, Letta patterns for working with a codex vault"
---

# Agent Examples

Practical examples showing how AI agents work with a codex vault. Each example demonstrates a different agent platform connecting to the same underlying structure.

The codex is agent-agnostic — any system that can read markdown files and follow conventions can use it.

## Examples

| File | Description |
|------|-------------|
| [openclaw-workspace.md](openclaw-workspace.md) | How an OpenClaw agent workspace connects to and operates on a codex |
| [letta-context-repo.md](letta-context-repo.md) | Using a codex as a Letta agent's Context Repository with memory tiers |
| [cursor-rules.md](cursor-rules.md) | Setting up Cursor, Claude Code, or Copilot to work with a codex |

## How Agents Use The Codex

Every agent integration follows the same core pattern:

1. **Boot** — Read `_codex/system/` for pinned context (identity, conventions, domain map)
2. **Search** — Index domain folders for semantic retrieval
3. **Execute** — Follow procedures from `_codex/skills/`
4. **Write** — Capture new knowledge back into the codex using conventions

The specifics vary by platform, but the structure stays the same.
