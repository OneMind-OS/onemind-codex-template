---
title: "Skill: Initialize"
type: skill
status: active
created: 2026-03-19
tags: [type/skill, codex/method]
ai_summary: "How to bootstrap a new codex vault or onboard an AI agent to an existing one"
---

# Codex Skill: Initialize

> How to bootstrap a new codex vault from scratch, or onboard a new AI agent to an existing one.

---

## When to Use

- Setting up a brand new codex vault
- Onboarding an AI agent to an existing vault (the agent needs to learn what's here)
- Recovering after a reset or data loss

---

## New Vault — Human Setup (30 min)

### Step 1: Create the skeleton

```text
codex/
├── _codex/                  ← Copy this folder from the template
├── 00-24 SO (Sovereign Operations)/README.md
├── 25-49 HP (Holistic Performance)/README.md
├── 50-74 LE (Legacy Evolution)/README.md
├── 75-99 GE (Generational Enterprise)/README.md
├── assets/
└── CODEX-FRAMEWORK.md
```

### Step 2: Open in Obsidian

Install [Obsidian](https://obsidian.md) (free), open the folder as a vault.
Enable: Settings → Core Plugins → Templates, Daily Notes, Tag Pane, Graph View.

### Step 3: Fill in your identity

Open `_codex/system/identity.md`, replace placeholders with your actual information.
This is what your AI reads to understand who you are.

### Step 4: Set your active goals

Open `_codex/system/active-goals.md`, write your current 3-5 priorities.
Keep this under 500 tokens — it's loaded into every AI interaction.

### Step 5: Create your first domain folders

Start with the 5-10 domains most relevant to your life right now.
Don't build all 100 — build what you will actually use.

### Step 6: Initialize git

```bash
git init
git add -A
git commit -m "init: vault skeleton"
```

---

## New Agent Onboarding (AI)

When an agent needs to learn a vault it's never seen:

1. Load `_codex/INTERFACE.md` — vault structure overview
2. Load all files in `_codex/system/` — pinned context
3. Load `_codex/CONVENTIONS.md` — naming and frontmatter rules
4. Scan each domain index — get the map
5. Read `ai_summary` fields in recently modified files — learn what's active

Do not load every file. Read summaries first, open full files only when needed.

---

## Quickstart Checklist

- [ ] Cloned or forked the vault template
- [ ] Opened in Obsidian
- [ ] Filled in `_codex/system/identity.md`
- [ ] Filled in `_codex/system/active-goals.md`
- [ ] Created at least one domain folder per group
- [ ] Initialized git
- [ ] Created first daily log
