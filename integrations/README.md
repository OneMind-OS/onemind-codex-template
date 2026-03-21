---
title: "Integrations"
type: index
status: active
created: 2026-03-19
tags: [type/index, domain/codex]
ai_summary: "Index of integration patterns — connecting a codex vault to Obsidian, Git, and external tools"
---

# Integrations

Patterns for connecting a codex vault to external tools and platforms. The codex is plain markdown on disk — anything that can read and write files can integrate with it.

## Guides

| File | Description |
|------|-------------|
| [obsidian-setup.md](obsidian-setup.md) | Using the codex as an Obsidian vault with recommended plugins and queries |
| [git-workflow.md](git-workflow.md) | Version-controlling your codex with git, branching, and auto-commit |
| [automation-patterns.md](automation-patterns.md) | Automation patterns — bots, cron, webhooks, voice capture |

## Principle

The codex is intentionally tool-agnostic. It's markdown files with YAML frontmatter in a folder structure. This means:

- **Obsidian** sees it as a vault
- **Git** sees it as a repo
- **AI agents** see it as a searchable knowledge base
- **Scripts** see it as files to parse and transform
- **Automation platforms** see it as a folder to watch

No vendor lock-in. If a tool dies, the knowledge stays.
