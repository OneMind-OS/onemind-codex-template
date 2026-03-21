---
title: Cursor / Claude Code / Copilot Integration
type: example
domain: agent
tags: [cursor, claude, copilot, ide, integration]
ai_summary: How to configure IDE coding agents (Cursor, Claude Code, GitHub Copilot) to work with a codex vault using rules files and instruction pointers.
---

# Cursor / Claude Code / Copilot Integration

How to set up IDE-based coding agents to understand and work with your codex vault.

## Overview

IDE agents (Cursor, Claude Code, GitHub Copilot) read instruction files at the root of your project to understand context and conventions. By pointing these files at your codex's `_codex/` meta layer, the agent gets full context on structure, naming, and procedures.

## Setup by Platform

### Cursor — `.cursorrules`

Create `.cursorrules` in your codex vault root:

```
# Codex Vault Rules

You are working in a personal knowledge codex — a structured Obsidian vault.

## Boot Context
Read these files FIRST before any operation:
- _codex/INTERFACE.md — how to interact with this vault
- _codex/CONVENTIONS.md — naming, frontmatter, and structure rules
- _codex/system/IDENTITY.md — what this codex is and who it belongs to

## Domain Structure
- 00-24 UI/ — Technology, AI, infrastructure
- 25-49 HP/ — Health, skills, personal development
- 50-74 LE/ — Family, home, legacy
- 75-99 GE/ — Business, ventures, wealth

## Rules
- Every new file MUST have YAML frontmatter (title, type, domain, tags, ai_summary)
- Use kebab-case filenames with domain prefix (e.g., ui-03-nats-architecture.md)
- Route files to the correct domain folder based on content
- Never create new top-level folders — use existing domains or 06 Inbox/
- ai_summary is required — one sentence, context for search results
- Check _codex/CONVENTIONS.md before creating any file
```

### Claude Code — `CLAUDE.md`

Create `CLAUDE.md` in your codex vault root:

```markdown
# CLAUDE.md

This is a personal knowledge codex — a structured vault of markdown notes.

## First Steps
Before any operation, read:
1. `_codex/INTERFACE.md` — interaction patterns
2. `_codex/CONVENTIONS.md` — naming and structure rules
3. `_codex/system/IDENTITY.md` — vault identity

## Structure
The vault uses numbered domain ranges (00-24, 25-49, 50-74, 75-99).
Each note has YAML frontmatter with: title, type, domain, tags, ai_summary.
See `_codex/CONVENTIONS.md` for the full spec.

## Key Rules
- Always add frontmatter to new files
- Route notes to the correct domain folder
- Never create top-level folders
- New unrouted content goes to `06 Inbox/`
```

### GitHub Copilot — `.github/copilot-instructions.md`

Create `.github/copilot-instructions.md`:

```markdown
# Copilot Instructions

This workspace is a personal knowledge codex (structured Obsidian vault).

Read `_codex/INTERFACE.md` for interaction patterns.
Read `_codex/CONVENTIONS.md` for file naming and frontmatter standards.

All markdown files use YAML frontmatter with: title, type, domain, tags, ai_summary.
Domain folders use numbered ranges: 00-24 (tech), 25-49 (health), 50-74 (family), 75-99 (business).
```

### AGENTS.md (Universal)

`AGENTS.md` works with multiple AI coding agents (Cursor, Copilot, Windsurf, etc.):

```markdown
# AGENTS.md

## What This Is
A personal knowledge codex — structured markdown vault with YAML frontmatter.

## Read First
- `_codex/INTERFACE.md` — how to interact with this vault
- `_codex/CONVENTIONS.md` — naming, structure, frontmatter rules
- `_codex/system/IDENTITY.md` — vault identity and owner

## Domain Map
| Range | Domain | Content |
|-------|--------|---------|
| 00-24 | UI | Technology, AI, infrastructure |
| 25-49 | HP | Health, skills, personal growth |
| 50-74 | LE | Family, home, legacy planning |
| 75-99 | GE | Business, ventures, wealth |

## Rules
1. Every file needs YAML frontmatter (title, type, domain, tags, ai_summary)
2. Route to correct domain folder
3. Use kebab-case filenames
4. New content without a clear domain goes to 06 Inbox/
5. Never create new top-level folders
```

## What The Agent Gets

With any of these setups, the IDE agent will:

1. **Understand structure** — knows the domain folders and what goes where
2. **Follow conventions** — adds proper frontmatter, uses correct naming
3. **Route correctly** — puts new notes in the right domain folder
4. **Search effectively** — knows to use `ai_summary` for quick context
5. **Respect boundaries** — won't create random top-level folders or break structure

## Tips

- **Keep rules files small.** The agent's context window is limited. Point to `_codex/` files rather than duplicating their content.
- **Test with a simple task.** Ask the agent to "create a note about X" and verify it adds frontmatter and routes correctly.
- **Update when conventions change.** If you add a new domain or change naming rules, update your rules file.
- **Symlink for multi-repo.** If your codex is in one repo and code is in another, symlink the rules file or use `_codex/INTERFACE.md` as the canonical reference.
