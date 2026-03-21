---
title: "Codex Conventions"
type: system
status: active
created: 2026-03-19
owner: zeus
tags: [type/system, domain/codex]
ai_summary: "Naming, tagging, frontmatter, and file organization rules for the vault"
---

# Codex Conventions

> Rules for naming, tagging, frontmatter, and organization. Follow these consistently and your AI will understand your vault without explanation.

---

## File Naming

- **Lowercase with hyphens**: `weekly-review.md`, `home-internet-setup.md`
- **No spaces in filenames** — Obsidian shows the display title separately
- **Date-stamped logs**: `YYYY-MM-DD.md` format for daily notes and journals

## Frontmatter (YAML)

Every file should open with frontmatter between `---` markers:

```yaml
---
id: {domain-code}-{YYYYMMDD}-{slug}
title: "Human-Readable Title"
type: note | decision | sop | project | person | review | doctrine | reference | log
status: active | draft | archived | deprecated
created: YYYY-MM-DD
modified: YYYY-MM-DD
owner: {your-name}
tags: [domain/ui, type/note, status/active]
related: ["[[Other Note]]"]
ai_summary: "One-line summary ≤20 words — what is this file?"
---
```

### Required Fields

| Field | Why |
|-------|-----|
| `title` | Human-readable name |
| `type` | What kind of document (see types below) |
| `created` | Creation date |
| `tags` | At least one tag |
| `ai_summary` | **Critical** — agents read this to decide if they need to open the full file. Without it, they open everything. |

### `ai_summary` — The Most Important Field

This is the hook agents use for progressive disclosure. Keep it under 20 words. Be specific:

```yaml
# Bad
ai_summary: "Notes"

# Good
ai_summary: "Morning routine checklist: 6am wake, workout, journaling, review Todoist"
```

---

## Document Types

| Type | Use For |
|------|---------|
| `note` | General knowledge, observations, ideas |
| `decision` | Choices made — with context and rationale |
| `sop` | Step-by-step procedures to follow |
| `project` | Tracked initiative with goals and milestones |
| `person` | Contact/relationship profile |
| `review` | Weekly, monthly, or quarterly reflection |
| `doctrine` | Core principles and frameworks |
| `reference` | External facts, specs, API docs |
| `log` | Time-stamped entries (daily, session) |

---

## Tagging System

Tags use a `namespace/value` pattern:

| Namespace | Examples | Purpose |
|-----------|----------|---------|
| `domain/` | `domain/ui`, `domain/hp`, `domain/ge` | Which quadrant |
| `type/` | `type/sop`, `type/decision`, `type/project` | Document type |
| `status/` | `status/active`, `status/draft`, `status/archived` | Lifecycle state |
| `cadence/` | `cadence/daily`, `cadence/weekly` | Review frequency |

---

## Folder Rules

- **Never create top-level folders** — All notes go inside the 4 quadrants
- **Inbox first when unsure** — Drop uncertain items in `06 Inbox (Queue)/`
- **Numbered domains** — Don't rename or renumber existing domain folders
- **Subfolders are fine** — Create subfolders within domains as needed

---

## ID Format

```
{quadrant-code}-{domain-number}-{YYYYMMDDHHMMSS}
```

Examples:
- `ui-02-20260318143022` — UI quadrant, domain 02, timestamped
- `hp-29-20260318-morning-routine` — HP quadrant, domain 29, descriptive slug
- `ge-75-brand-architecture` — GE quadrant, domain 75

IDs are optional but recommended for notes that other notes will link to.
