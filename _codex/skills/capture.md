---
title: "Skill: Capture"
type: skill
status: active
created: 2026-03-19
tags: [type/skill, codex/method]
ai_summary: "How to add new information to the codex — the C step in CODEX"
---

# Codex Skill: Capture

> How to add new information to the codex. Any incoming data — ideas, notes,
> decisions, voice memos, agent outputs — enters through this process.

---

## The Capture Flow

```text
Input (any source)
  → Classify the type
  → Apply the right template from _codex/templates/
  → Fill frontmatter + content
  → Save to 06 Inbox (Queue)/ OR directly to the known domain folder
```

## Steps

1. **Classify the input** — What kind of information is this?
   - Idea, observation, or reference → `note`
   - A choice that was made → `decision`
   - A repeatable process → `sop`
   - Information about a person → `person`
   - A project or initiative → `project`
   - A time-stamped event or daily log → `log`

2. **Pick the template** — Open the matching file from `_codex/templates/`

3. **Fill the frontmatter** — At minimum: `title`, `type`, `created`, `tags`, `ai_summary`
   - `ai_summary` is the most important field — write it like a search result snippet

4. **Name the file** — lowercase-with-hyphens, e.g. `home-internet-setup.md`
   - For dated entries: `YYYY-MM-DD-slug.md`

5. **Choose the destination**
   - If the domain is obvious → save there directly
   - If uncertain → save to `00-24 UI/06 Inbox (Queue)/`
   - Never create new top-level folders

## Capture Sources

The codex captures from anywhere:

| Source | How to capture |
|--------|---------------|
| Voice/speech | Transcribe → paste into note, use daily.md template |
| Text/message | Copy + paste, add context in frontmatter |
| Screenshot | Save to `assets/`, reference in note |
| AI output | Save agent's response as a note with type/log or type/note |
| Email | Extract the decision or action, capture just that |
| Meeting | Capture decisions made + actions assigned |

## The 2-Minute Rule

If you can classify and file it in under 2 minutes — do it now.
If not — drop it in `06 Inbox (Queue)/` with at minimum a title and one line of context.
