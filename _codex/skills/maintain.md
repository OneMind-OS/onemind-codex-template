---
title: "Skill: Maintain"
type: skill
status: active
created: 2026-03-19
tags: [type/skill, codex/method]
ai_summary: "How to keep the codex healthy — stale content, missing fields, and structural hygiene"
---

# Codex Skill: Maintain

> How to keep the codex healthy over time. Run this during monthly or quarterly reviews.

---

## Signs a Codex Needs Maintenance

- Files with missing or placeholder `ai_summary` fields
- Stale `status: active` on projects that haven't been updated in 30+ days
- `_codex/system/` files that are outdated or over 2,000 tokens total
- `06 Inbox (Queue)/` with items older than 7 days
- Orphaned files with no `related` links and no tag connections
- Domain folders with READMEs that no longer reflect what's inside

---

## Maintenance Checklist

Run this monthly or whenever the codex feels "heavy":

### 1. Audit `ai_summary` fields

Open any domain folder. Spot-check 5-10 files.
If `ai_summary` is empty, placeholder, or just the filename → rewrite it.
Good example: `"Weekly review for March 2026 — productive sprint, blocked on client contract"`
Bad example: `"Weekly Review — 2026-03-19"` ← just the title, adds no context

### 2. Audit `_codex/system/`

- Total size must stay under 2,000 tokens
- Each file should be relevant to >50% of interactions
- If a `system/` file hasn't been useful in 7+ days → move it back to its domain

### 3. Archive stale projects

Search for `type: project` + `status: active` → check last modified date.
If a project hasn't been touched in 30+ days, change status to `on-hold` and add a note.
If complete, change to `status: archived` and move to an `Archive/` subfolder.

### 4. Clear the inbox

See `_codex/skills/organize.md`.

### 5. Check for broken links

In Obsidian: open the graph view. Orphaned nodes (no connections) may need `related` fields added.
For agents: run a search for `[[` in all files and verify referenced notes exist.

---

## How Often

| Action | Frequency |
|--------|-----------|
| Inbox triage | Weekly |
| `ai_summary` audit | Monthly |
| System/ audit | Monthly |
| Archive stale projects | Quarterly |
| Full vault health check | Quarterly |
