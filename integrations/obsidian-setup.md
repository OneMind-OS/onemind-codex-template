---
title: Obsidian Setup
type: guide
domain: integration
tags: [obsidian, setup, plugins, dataview]
ai_summary: How to use a codex vault in Obsidian — recommended plugins, folder mapping, tag system, wiki-links, and Dataview queries.
---

# Obsidian Setup

How to open and use your codex as an Obsidian vault.

## Quick Start

1. Open Obsidian
2. **Open folder as vault** → select your codex root directory
3. Trust the vault when prompted (enables community plugins)
4. Install recommended plugins (see below)

The codex folder structure maps directly to Obsidian's sidebar file tree.

## Recommended Plugins

### Essential

| Plugin | Purpose |
|--------|---------|
| **Dataview** | Query frontmatter across notes — list projects, filter by tags, show recent captures |
| **Templater** | Use `_codex/templates/` for consistent note creation |
| **Git** (Obsidian Git) | Auto-commit changes, sync via GitHub |

### Recommended

| Plugin | Purpose |
|--------|---------|
| **Calendar** | Navigate daily notes, see capture history |
| **Tag Wrangler** | Rename and manage tags across the vault |
| **Frontmatter Title** | Display `title` from frontmatter instead of filename in sidebar |
| **Hover Editor** | Preview linked notes on hover without leaving current note |

### Optional

| Plugin | Purpose |
|--------|---------|
| **Kanban** | Visualize projects or inbox items as boards |
| **Excalidraw** | Visual diagrams within notes |
| **Tasks** | Track TODO items across the vault |

## Folder Structure Mapping

The codex domains appear as top-level folders in Obsidian's sidebar:

```
Vault Root/
├── _codex/          ← Meta layer (collapse this in sidebar if noisy)
├── 00-24 UI/        ← Tech, infrastructure, AI
├── 25-49 HP/        ← Health, skills, personal
├── 50-74 LE/        ← Family, home, legacy
├── 75-99 GE/        ← Business, ventures, wealth
└── 06 Inbox/        ← Quick capture landing zone
```

**Tip**: Star/bookmark frequently accessed domain folders for quick access.

## Tags

The codex uses Obsidian's native tag system. Tags live in YAML frontmatter:

```yaml
tags: [project, active, q2-2026]
```

Obsidian renders these as clickable tags. Use the Tag Wrangler plugin to rename tags vault-wide.

### Suggested Tag Taxonomy

- **Type tags**: `project`, `decision`, `reference`, `log`, `capture`
- **Status tags**: `active`, `paused`, `completed`, `archived`
- **Domain tags**: `tech`, `health`, `family`, `business`
- **Time tags**: `q1-2026`, `weekly`, `daily`

## Wiki-Links

Use `[[double brackets]]` for cross-domain linking:

```markdown
This architecture decision affects the [[deployment-pipeline]]
and relates to the [[q2-hiring-plan]].
```

Obsidian resolves these across the entire vault regardless of folder location.

## Dataview Queries

Install the Dataview plugin, then use these in any note:

### List All Active Projects

```dataview
TABLE title, domain, tags
FROM ""
WHERE type = "project" AND contains(tags, "active")
SORT domain ASC
```

### Decisions This Month

```dataview
TABLE title, domain, created
FROM ""
WHERE type = "decision" AND created >= date(2026-03-01)
SORT created DESC
```

### Inbox Items (Unrouted)

```dataview
LIST title
FROM "06 Inbox"
SORT created DESC
```

### Recent Captures by Domain

```dataview
TABLE title, type, created
FROM "75-99 GE"
WHERE created >= date(2026-03-01)
SORT created DESC
LIMIT 10
```

### Notes Missing ai_summary

```dataview
LIST
FROM ""
WHERE !ai_summary AND file.name != "README"
LIMIT 20
```

## Templates

Put note templates in `_codex/templates/`. Configure Templater to use this folder:

**Templater Settings** → Template folder location: `_codex/templates`

Then use `Templater: Insert template` or set up folder-specific templates (e.g., notes created in `75-99 GE/` auto-apply the project template).

## Settings Recommendations

| Setting | Value | Why |
|---------|-------|-----|
| Default location for new notes | `06 Inbox/` | Everything starts in inbox, gets routed later |
| Attachment folder path | `assets/` | Keep media organized |
| New link format | Shortest path when possible | Cleaner wiki-links |
| Use [[Wikilinks]] | ON | Standard codex linking |
| Detect all file extensions | ON | Find non-markdown files |
