---
title: "Skill: Search"
type: skill
status: active
created: 2026-03-19
tags: [type/skill, codex/method]
ai_summary: "How to find information in the codex — search hierarchy for humans and AI"
---

# Codex Skill: Search

> How to find specific information in the codex — for humans and AI agents.

---

## Search Hierarchy

Work from fastest to most thorough:

### Level 1 — Direct navigation

If you know where it lives:
```
_codex/INTERFACE.md → domain README → specific file
```

### Level 2 — Tag search

Use Obsidian's tag panel or grep:
```
#type/decision       → all decision records
#type/sop            → all SOPs
#domain/ui           → everything in UI quadrant
#status/active       → only active items
#cadence/weekly      → weekly review notes
```

### Level 3 — Full text search

In Obsidian: `Cmd+Shift+F` → search any term
For agents: use `memory_search` with semantic query

### Level 4 — AI semantic search

Ask your AI: "find everything about X in my codex"
The agent will use semantic search across `ai_summary` fields and content.

---

## Finding Things by Type

| Want to find | Where to look |
|-------------|---------------|
| Current priorities | `_codex/system/active-goals.md` |
| Who is this person? | `25-49 HP/32 Relationships/` |
| Why did we choose X? | Search tag `#type/decision` |
| How do I do X? | Search tag `#type/sop` |
| What happened this week? | `25-49 HP/29 Life Systems/Daily Notes/` |
| What's in progress? | Search `status: active` + `type: project` |
| What's in the inbox? | `00-24 UI/06 Inbox (Queue)/` |

---

## Agent Search Protocol

When an agent needs to find information:

1. Check `_codex/system/` first (always-loaded context)
2. Check the relevant domain README for navigation
3. Use semantic search on `ai_summary` fields (fast, low token cost)
4. Open specific files only when the summary isn't sufficient

**Never open every file looking for something** — read summaries first.
