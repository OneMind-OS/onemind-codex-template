---
title: "Decision: Obsidian as Primary Vault Tool"
type: decision
status: active
created: 2026-01-05
decided_by: zeus
tags: [type/decision, domain/hp, topic/tools]
ai_summary: "Chose Obsidian over Notion for codex — local-first, plain markdown, git-syncable, plugin ecosystem"
---

# Decision: Obsidian as Primary Vault Tool

## Context

Needed a tool to host the codex vault. Requirements: works offline, stores as plain markdown, syncs via git, supports wiki-links, and has plugin ecosystem for automation.

## Options Considered

1. **Notion** — Full-featured, cloud-native, great sharing
   - Pros: Beautiful UI, real-time collaboration, API access
   - Cons: Proprietary format, requires internet, vendor lock-in, slow with large vaults

2. **Obsidian** — Local-first markdown editor with plugins
   - Pros: Plain markdown files, works offline, git-friendly, massive plugin ecosystem
   - Cons: No real-time collab, learning curve for non-technical users

3. **Logseq** — Outliner-based, open source
   - Pros: Open source, block-level references
   - Cons: Outliner format fights long-form docs, smaller community

## Decision

Obsidian. The codex is designed to be **tool-agnostic** — it's just markdown files in folders. Obsidian happens to be the best viewer, but the vault works in any text editor, VS Code, or even `cat` on the command line.

## Rationale

The codex must survive tool changes. If Obsidian dies tomorrow, every file still works because it's plain markdown. This was impossible with Notion's proprietary blocks.

## Review Date

N/A — This decision is architectural. The vault format (markdown) is permanent.
