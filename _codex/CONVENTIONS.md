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
type: goal | project | task | note | decision | sop | aop | doctrine | reference | metric | review | human | agent | robot | drone | skill | tool
status: active | draft | archived | deprecated
created: YYYY-MM-DD
modified: YYYY-MM-DD
owner: {your-name}
operator: human | agent | robot | drone | automated
realm: digital | physical | hybrid
tags: [domain/ui, type/goal, status/active]
related: ["[[Other Note]]"]
ai_summary: "One-line summary ≤20 words — what is this file?"
---
```

### Required Fields

| Field | Why |
|-------|-----|
| `title` | Human-readable name |
| `type` | Entity type from the taxonomy (see below) |
| `created` | Creation date |
| `tags` | At least one tag |
| `ai_summary` | **Critical** — agents read this to decide if they need to open the full file. Without it, they open everything. |

### Recommended Fields

| Field | Why |
|-------|-----|
| `operator` | Who/what owns this: `human`, `agent`, `robot`, `drone`, `automated` |
| `realm` | Where it exists: `digital`, `physical`, `hybrid` |

### `ai_summary` — The Most Important Field

This is the hook agents use for progressive disclosure. Keep it under 20 words. Be specific:

```yaml
# Bad
ai_summary: "Notes"

# Good
ai_summary: "Morning routine checklist: 6am wake, workout, journaling, review Todoist"
```

---

## Entity Types (Document Types)

The CODEX entity system has 17 types across 5 categories. Use the `type` field in frontmatter.

### Intent (what you want)

| Type | Use For |
|------|---------|
| `goal` | Long-term outcome with measurable success criteria |
| `project` | Bounded effort toward a goal, with milestones |
| `task` | Single action item, assignable to an operator |

### Knowledge (what you know)

| Type | Use For |
|------|---------|
| `note` | General knowledge, observations, ideas |
| `decision` | Choices made — with context, options, and rationale |
| `sop` | Standard Operating Procedure — human-readable repeatable process |
| `aop` | Agent Operations Procedure — agent-native execution contract |
| `doctrine` | Core principles, frameworks, system-level truths |
| `reference` | External facts, specs, API docs, guides |

### Measurement (how you track)

| Type | Use For |
|------|---------|
| `metric` | Tracked number or KPI (weight, revenue, pace) |
| `review` | Weekly, monthly, or quarterly reflection |

### Operator (who/what does the work)

| Type | Use For |
|------|---------|
| `human` | Person profile — you, family, team, contractor |
| `agent` | AI agent profile and configuration |
| `robot` | Physical automation device profile |
| `drone` | Autonomous physical agent profile |

### Capability (what you can do)

| Type | Use For |
|------|---------|
| `skill` | Portable ability definition (research, draft, analyze) |
| `tool` | Specific software/hardware (Obsidian, Claude, 3D printer) |

### Legacy Types (still supported)

| Type | Mapped To |
|------|-----------|
| `person` | Use `human` for new files — `person` still works |
| `log` | Use `note` with `cadence/daily` tag — `log` still works |

---

## Tagging System

Tags use a `namespace/value` pattern:

| Namespace | Examples | Purpose |
|-----------|----------|---------|
| `domain/` | `domain/ui`, `domain/hp`, `domain/ge` | Which domain |
| `type/` | `type/goal`, `type/task`, `type/sop`, `type/agent` | Entity type |
| `status/` | `status/active`, `status/draft`, `status/archived` | Lifecycle state |
| `operator/` | `operator/zeus`, `operator/legacy`, `operator/spartan` | Who owns execution |
| `cadence/` | `cadence/daily`, `cadence/weekly` | Review frequency |
| `realm/` | `realm/digital`, `realm/physical`, `realm/hybrid` | Digital vs physical |

---

## Folder Rules

- **Never create top-level folders** — All notes go inside the domain folders (SO, HP, LE, GE)
- **Inbox first when unsure** — Drop uncertain items in `06 Inbox (Queue)/`
- **Numbered domains** — Don't rename or renumber existing domain folders
- **Subfolders are fine** — Create subfolders within domains as needed

---

## ID Format

```
{domain-code}-{domain-number}-{YYYYMMDDHHMMSS}
```

Examples:
- `so-02-20260318143022` — SO domain, subdomain 02, timestamped
- `hp-29-20260318-morning-routine` — HP domain, subdomain 29, descriptive slug
- `ge-75-brand-architecture` — GE domain, subdomain 75

IDs are optional but recommended for notes that other notes will link to.
