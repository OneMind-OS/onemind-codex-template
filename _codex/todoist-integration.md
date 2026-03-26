---
title: "Todoist Integration Guide"
type: reference
status: active
tags: [type/reference, status/active, tools/todoist]
---

# Todoist × Obsidian Integration

This guide walks through setting up the Todoist Sync plugin and embedding live tasks in your codex notes.

## Setup (One-Time)

### 1. Install the Plugin

1. Open Obsidian → **Settings → Community Plugins**
2. If "Restricted Mode" is on → click **"Turn off restricted mode"** → confirm
3. Click **Browse** → search **"Todoist Sync"** (by jamiebrynes7)
4. Click **Install** → then **Enable**

### 2. Get Your Todoist API Token

1. Open [todoist.com](https://todoist.com) → sign in
2. Go to **Settings → Integrations → Developer**
3. Copy your **API token**

### 3. Connect the Plugin

1. Back in Obsidian → **Settings → Todoist Sync**
2. Paste your API token
3. Click **Submit** — you should see a success message

---

## Query Block Syntax

Embed live Todoist tasks anywhere in a note using a `todoist` code block:

````markdown
```todoist
filter: "#ProjectName"
```
````

The block renders as a live, interactive task list in Reading/Preview mode.

### Available Options

| Option | Description | Example |
|--------|-------------|---------|
| `filter` | Todoist filter query (required) | `"#Work"`, `"today"`, `"@urgent"` |
| `name` | Title displayed above the task list | `"My Tasks"` |
| `groupBy` | Group results by category | `project`, `section`, `date` |
| `autorefresh` | Auto-refresh interval in seconds | `180` (every 3 minutes) |
| `sorting` | Sort order (list) | `date`, `priority` |

---

## Example Queries

### All Tasks Due Today

```todoist
filter: "today"
name: "Due Today"
sorting:
  - priority
  - date
```

### Overdue Tasks

```todoist
filter: "overdue"
name: "⚠️ Overdue"
sorting:
  - date
```

### Tasks From a Specific Project

Replace `OneMind` with your actual Todoist project name:

```todoist
filter: "#OneMind"
name: "OneMind Project Tasks"
groupBy: section
sorting:
  - date
  - priority
```

### All Tasks Due This Week

```todoist
filter: "7 days"
name: "This Week"
groupBy: date
sorting:
  - date
  - priority
```

### High Priority Tasks Only

```todoist
filter: "p1"
name: "🔴 Priority 1"
sorting:
  - date
```

### Combined Filter — Project + Due Soon

```todoist
filter: "#OneMind & 7 days"
name: "OneMind — Due This Week"
sorting:
  - date
  - priority
```

### Tasks Tagged with a Label

```todoist
filter: "@codex"
name: "Codex-Tagged Tasks"
sorting:
  - date
```

---

## Using in Your Codex Notes

### Embed in a Goal Note

Add this to any goal note to see tasks related to that goal:

````markdown
## Related Tasks

```todoist
filter: "#GoalProjectName"
groupBy: section
autorefresh: 300
```
````

### Embed in Mission Control Dashboard

Add this block to your Mission Control note alongside Dataview queries:

````markdown
## 📋 Todoist — Due Today

```todoist
filter: "today | overdue"
name: "Action Required"
sorting:
  - priority
  - date
```
````

### Embed in Weekly Review

Add to your × Multiply review template:

````markdown
## Tasks Completed This Week

```todoist
filter: "completed before: today & completed after: -7 days"
name: "Done This Week ✅"
```
````

---

## Filter Syntax Quick Reference

| Filter | What It Shows |
|--------|--------------|
| `"today"` | Tasks due today |
| `"overdue"` | Past-due tasks |
| `"7 days"` | Tasks due in next 7 days |
| `"no date"` | Tasks with no due date |
| `"#ProjectName"` | All tasks in a project |
| `"#ProjectName & today"` | Project tasks due today |
| `"@label"` | Tasks with a specific label |
| `"p1"` | Priority 1 (urgent) tasks |
| `"p1 | p2"` | Priority 1 or 2 tasks |
| `"assigned to: me"` | Tasks assigned to you |
| `"today | overdue"` | Due today or overdue |

Full filter syntax: [Todoist Filter Docs](https://todoist.com/help/articles/introduction-to-filters-V98wIH)

---

## Interaction

When viewing a rendered todoist block:
- **Click a task checkbox** → marks it complete in Todoist (two-way sync)
- **Click a task name** → opens task details
- Tasks auto-refresh based on `autorefresh` setting (or manually refresh with the plugin command)

---

*Part of the One Mind CODEX framework. See [CODEX-FRAMEWORK](../CODEX-FRAMEWORK.md) for the full plugin stack.*
