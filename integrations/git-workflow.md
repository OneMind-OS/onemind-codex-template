---
title: Git Workflow
type: guide
domain: integration
tags: [git, version-control, sync, workflow]
ai_summary: How to version-control a codex with git — init, gitignore, commit conventions, Obsidian Git plugin, branching, multi-device sync, and agent auto-commit.
---

# Git Workflow

How to version-control your codex with git for history, backup, multi-device sync, and agent collaboration.

## Initial Setup

```bash
cd /path/to/your/codex
git init
git add .
git commit -m "capture: initial codex structure"
```

## .gitignore

Create `.gitignore` in the vault root:

```gitignore
# Obsidian runtime state (don't track)
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache

# OS files
.DS_Store
Thumbs.db

# Obsidian trash
.trash/

# Temporary files
*.tmp
*.swp
```

**What TO track:**

- `.obsidian/plugins/` — plugin configs (portable across machines)
- `.obsidian/themes/` — theme files
- `.obsidian/snippets/` — custom CSS
- `.obsidian/app.json`, `appearance.json`, `hotkeys.json` — settings
- All markdown files and `_codex/` meta layer

## Commit Conventions

Use prefixes that match codex operations:

| Prefix | When |
|--------|------|
| `capture:` | New notes added (inbox, daily logs, quick captures) |
| `organize:` | Moving, renaming, re-tagging existing notes |
| `review:` | Updates from weekly/monthly review cycles |
| `decision:` | New or updated decision records |
| `refactor:` | Restructuring folders or conventions |
| `template:` | New or updated templates |
| `fix:` | Correcting errors in existing notes |

Examples:

```
capture: daily log 2026-03-19
organize: route inbox items to HP and GE domains
review: weekly review — archive completed projects
decision: choose NATS over RabbitMQ for messaging
refactor: split 00-24 UI into tech and infrastructure subfolders
```

## Obsidian Git Plugin

The **Obsidian Git** community plugin automates commits and sync:

### Recommended Settings

| Setting | Value |
|---------|-------|
| Auto backup interval | 30 minutes |
| Auto pull interval | 5 minutes |
| Commit message template | `capture: vault auto-backup {{date}}` |
| Pull on startup | ON |
| Push on backup | ON |

### Setup

1. Install "Obsidian Git" from community plugins
2. Ensure git is initialized and a remote is set:
   ```bash
   git remote add origin git@github.com:yourname/your-codex.git
   git push -u origin main
   ```
3. Open Obsidian settings → Obsidian Git → configure intervals
4. Use the command palette: `Obsidian Git: Commit all changes` for manual commits

## Branch Strategy

Keep it simple — two branches:

### `main` — Canonical

The source of truth. All reviewed, organized content lives here.

### `drafts` — Work in Progress

For content that's not ready to be part of the canonical vault:

```bash
git checkout -b drafts
# Write messy notes, brainstorm, draft posts
git add . && git commit -m "capture: rough draft — product launch plan"
# When ready:
git checkout main
git merge drafts
```

Most codex users won't need branches — `main` with auto-commit is fine for personal use.

## Multi-Device Sync

### Via GitHub (Private Repo)

```
Machine A (laptop)          Machine B (desktop)         Machine C (phone/tablet)
     │                           │                           │
     └── git push ──→ GitHub ←── git pull ──────────────────┘
                     (private repo)
```

1. Create a **private** GitHub repo
2. Push from your primary machine
3. Clone on other machines
4. Use Obsidian Git plugin for auto-sync on all devices

### Via Obsidian Sync (Alternative)

Obsidian's paid sync service works too, but you lose git history. Use one or the other — not both on the same vault.

## Agent Auto-Commit

When AI agents write to the codex, you want their changes committed automatically.

### The codex-watch Pattern

A background service watches for file changes and auto-commits:

```bash
#!/bin/bash
# codex-watch.sh — watches codex for changes, auto-commits to git

CODEX_DIR="/path/to/your/codex"
cd "$CODEX_DIR"

while true; do
    # Wait for file changes
    fswatch -1 "$CODEX_DIR" \
        --exclude '.git' \
        --exclude '.obsidian/workspace'

    # Stage and commit
    git add -A
    if ! git diff --cached --quiet; then
        git commit -m "capture: agent auto-commit $(date +%Y-%m-%d-%H%M)"
        git push origin main
    fi

    sleep 5  # debounce
done
```

### As a systemd Service

```ini
[Unit]
Description=Codex auto-commit watcher
After=network.target

[Service]
ExecStart=/path/to/codex-watch.sh
Restart=always
User=yourusername

[Install]
WantedBy=multi-user.target
```

### Key Rules for Agent Commits

- Agent commits use the `capture:` prefix
- Include date/time in commit message for traceability
- Push immediately so other devices/agents see changes
- Never force-push — append only
- Debounce writes (5-10 second delay) to batch rapid changes

## Merge Conflicts

With markdown files, conflicts are rare and simple to resolve:

1. **Same file, different sections** — git auto-merges these
2. **Same line** — manually pick the version you want (both are readable text)
3. **Frontmatter conflicts** — usually caused by concurrent `ai_summary` updates; keep the most recent

**Prevention**: Use the Obsidian Git auto-pull interval to stay in sync, and avoid editing the same note on two devices simultaneously.
