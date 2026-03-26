---
title: "Agent Instructions"
type: system
status: active
created: 2026-03-19
owner: zeus
tags: [type/system, domain/codex]
ai_summary: "Operating instructions for AI agents working with this Codex vault"
---

# Agent Instructions

> Read this before touching anything in this vault.

---

## What This Is

This is a **One Mind Codex vault** — a structured knowledge base built with the CODEX method (Capture → Organize → Direct → Execute → × Multiply). It uses plain Markdown files with YAML frontmatter, organized into three life domains and one operating layer:

| ID Range | Quadrant | Domain |
|----------|----------|--------|
| 00–24 | **SO** — Sovereign Operations | Technology, AI, infrastructure |
| 25–49 | **HP** — Holistic Performance | Health, skills, personal growth |
| 50–74 | **LE** — Legacy Evolution | Relationships, community, home |
| 75–99 | **GE** — Generational Endeavor | Career, ventures, impact, wealth |

System files live in `_codex/`. The master documents are `ONEMIND-CODEX.md` and `CODEX-FRAMEWORK.md` at the vault root.

---

## How to Navigate

1. **Start with `_codex/INTERFACE.md`** — the navigation guide. Understand the vault structure before reading individual documents.
2. **Load `_codex/system/`** — pinned context files. These contain the current state, active priorities, and operational rules. Always load these first.
3. **Scan `_codex/CONVENTIONS.md`** — naming rules, tagging conventions, and formatting standards.

---

## Progressive Disclosure

Do not read every file. Load context in layers:

| Level | What to Load | Purpose |
|-------|-------------|---------|
| **L0** | `_codex/system/` | Pinned context. Current state, priorities, rules. Always first. |
| **L1** | `ai_summary` fields in frontmatter | Scan many files fast. Read the one-liner to decide if the full document is relevant. |
| **L2** | Full document content | Read when the summary indicates relevance to the current task. |
| **L3** | Linked documents (wiki-links, references) | Follow links only when deeper context is needed. |

This approach lets you understand the vault's state from ~5 system files, scan 100 documents by reading 100 one-liners, and deep-read only what matters.

---

## File Conventions

- **Naming**: lowercase-hyphens for filenames (e.g., `weekly-review-2026-03-19.md`).
- **Frontmatter**: every document must have YAML frontmatter with at minimum: `title`, `type`, `status`, `created`, `tags`, `ai_summary`.
- **Templates**: always use templates from `_codex/templates/` when creating new documents. This ensures consistent structure and metadata.
- **Document types**: See CODEX-FRAMEWORK.md for the full entity taxonomy. Core types: `goal`, `project`, `task`, `note`, `decision`, `sop`, `aop`, `metric`, `review`, `doctrine`, `reference`, `skill`, `tool`, `agent`, `human`, `robot`, `drone`. Each has its own template.

---

## Capture Rules

- New content should use the appropriate template from `_codex/templates/`.
- If the target domain is uncertain, place the document in `06 Inbox (Queue)/` within the most likely domain group.
- If even the domain group is unclear, place it in the staging area and flag it for triage.
- Always populate `ai_summary` in frontmatter — this is how other agents (and future you) discover documents without reading them fully.
- Never create new top-level folders. The vault structure is fixed: `_codex/`, the domain folders (SO, HP, LE, GE), and root doctrine documents.

---

## Write Guardrails

- **Write to domain subfolders only.** Agents must not create new top-level directories.
- **Never delete or overwrite doctrine files** (`ONEMIND-CODEX.md`, `CODEX-FRAMEWORK.md`) without explicit human approval.
- **Use templates.** Don't create bare Markdown files — always start from the template for the document type.
- **Preserve frontmatter.** When editing existing documents, never strip or corrupt the YAML frontmatter block.
- **Update `updated` field.** When modifying a document, update the `updated` date in frontmatter.

---

## Review Cadence (× Multiply)

- **Weekly review**: process inboxes, update active projects, review agent output, adjust priorities. Each review multiplies the system's value. Use profiles in `_codex/profiles/`.
- **Monthly review**: domain health check, metric review, system maintenance, goal alignment.
- **Quarterly review**: pattern analysis, decision audit, long-term project recalibration, OKR setting.
- Review documents use the `review` template and are stored in the appropriate domain folder.

---

## Summary

1. Read `_codex/INTERFACE.md` first.
2. Load `_codex/system/` for pinned context.
3. Use progressive disclosure — don't read everything.
4. Follow templates and naming conventions.
5. Never create top-level folders.
6. Always include `ai_summary` in frontmatter.

---

*Part of the One Mind framework. See [ONEMIND-CODEX.md](ONEMIND-CODEX.md) for the master document.*
