---
id: "skill-{slug}"
title: "Skill: {Skill Name}"
type: skill
status: active
created: "{YYYY-MM-DD}"
owner: "{your-name}"
tags: [type/skill, "domain/{domain}"]
related: []
ai_summary: "Skill: {what this capability does in ≤10 words}"
---

# Skill: {Skill Name}

<!-- Skills are portable capability definitions — the "what" an agent can do.
     They are agent-agnostic: any AI that reads this file can learn the skill.
     Save in _codex/skills/ or in the relevant domain folder.
     Skills define WHAT to do. Tools define WITH WHAT. AOPs define the full procedure. -->

## What This Skill Does

{One paragraph: what capability does this skill provide?
What can an agent (or human) accomplish with this skill?}

## When To Use

- {Trigger or situation where this skill is needed}
- {Another trigger}

## Inputs

| Input | Description | Required |
|-------|-------------|----------|
| {input 1} | {what it is} | yes/no |
| {input 2} | {what it is} | yes/no |

## Process

1. {Step 1 — what to do}
2. {Step 2}
3. {Step 3}
4. {Step 4}

## Outputs

| Output | Format | Description |
|--------|--------|-------------|
| {output 1} | {markdown, JSON, etc.} | {what it contains} |

## Tools Required

- {Tool 1 — e.g., web search, Claude, spreadsheet}
- {Tool 2}

## Quality Criteria

- {How to judge if this skill was executed well}
- {Minimum acceptable standard}

---
<!-- AI AGENT NOTE: Skills are your playbook.
     When assigned a task, check if a matching skill exists before improvising.
     Skills can be composed — use multiple skills together for complex tasks. -->
