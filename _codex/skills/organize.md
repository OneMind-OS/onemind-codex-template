---
title: "Skill: Organize"
type: skill
status: active
created: 2026-03-19
tags: [type/skill, codex/method]
ai_summary: "How to process the inbox and route content — the O step in CODEX"
---

# Codex Skill: Organize

> How to process the inbox and route content to the right domain folder.
> Run this when `06 Inbox (Queue)/` has accumulated items.

---

## When to Run This

- Daily: quick pass, route anything obvious
- Weekly: full inbox zero — nothing stays in inbox more than 7 days
- After a heavy capture session (travel, sprint, big project)

## Steps

1. **Open `00-24 SO/06 Inbox (Queue)/`**
   List all files. For each one:

2. **Read the title and frontmatter**
   - Does it have `ai_summary`? If not, write one.
   - Does it have `type`? If not, classify it.

3. **Determine the correct domain**

   Use this routing logic:

   | Content type | Destination |
   |-------------|-------------|
   | AI agents, tools, memory | `00-24 SO/02 Agents/` |
   | Protocols, SOPs, procedures | `00-24 SO/03 Protocols/` |
   | Infrastructure, servers, APIs | `00-24 SO/08 Infrastructure/` |
   | Automation, workflows | `00-24 SO/09 Automation/` |
   | Health, body, fitness | `25-49 HP/27 Body/` |
   | Personal finance | `25-49 HP/30 Finance/` |
   | Relationships, contacts | `25-49 HP/32 Relationships/` |
   | Daily habits, routines | `25-49 HP/29 Life Systems/` |
   | Home, property | `50-74 LE/50 Home/` |
   | Family, parenting | `50-74 LE/52 Children/` |
   | Business operations | `75-99 GE/79 Technology/` or relevant GE domain |
   | Personal brand | `75-99 GE/75 Brand/` |

4. **Move the file to its domain folder**

5. **Update `modified` in frontmatter** to today's date

6. **Add `related` links** if obvious connections exist

7. **Mark inbox as empty** — inbox zero is the goal

## Rules

- Every file needs a permanent home — inbox is a staging area, not storage
- If genuinely uncertain after 30 seconds, put it in the most relevant domain group's inbox subfolder
- Never delete inbox items to "clean up" — route them or archive them
