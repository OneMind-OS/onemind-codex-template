---
title: "THE CODEX FRAMEWORK"
type: doctrine
status: active
created: 2026-03-19
owner: zeus
tags: [type/doctrine, status/active]
ai_summary: "Deep dive on the CODEX method — Capture, Organize, Direct, Execute, eXamine — with detailed breakdown of each step"
---

# THE CODEX FRAMEWORK

> Capture → Organize → Direct → Execute → eXamine

---

## The Thesis

Every personal knowledge framework built before 2024 shares the same fatal flaw: **they were designed for a world without AI agents.**

Here's what breaks:

| Problem | Why It Kills Your System |
|---------|------------------------|
| **No context for AI** | Your notes are unstructured prose. An AI agent can't scan 500 files to find what matters. It needs typed metadata, summaries, and status fields — or it drowns in noise. |
| **No structure for AI to act** | Even if an agent reads your notes, there's no execution framework. What's a task? What's a priority? What's delegated? GTD has next actions but no concept of AI delegation. |
| **No permission model** | Who writes what? Can an agent create a new project? Update a status? Agents need guardrails — where they can write, where they can't, what templates to use. |
| **Doesn't survive tool changes** | Systems built on Notion databases, Roam graphs, or Evernote stacks die when you switch tools. Your life OS must be plain files in folders — portable, version-controlled, permanent. |

The CODEX method solves all four. Every document is machine-readable. Execution is built in. Agents have explicit guardrails. And the whole system is plain Markdown files.

---

## The CODEX Method

Five steps. One continuous loop.

```
  ┌─────────┐    ┌───────────┐    ┌────────┐    ┌─────────┐    ┌──────────┐
  │ CAPTURE │───▶│ ORGANIZE  │───▶│ DIRECT │───▶│ EXECUTE │───▶│ eXAMINE  │
  └─────────┘    └───────────┘    └────────┘    └─────────┘    └──────────┘
   Inbox, voice,   4 quadrants,    Prioritize,   Agents run     Weekly &
   quick capture   100 domains,    route to       tasks, skills  monthly
   from anywhere   frontmatter     human or AI    execute SOPs   reviews
                                                                    │
                                                                    │
                          ◀─────── feedback loop ──────────────────┘
```

The loop never stops. eXamine feeds back into Capture — surfacing gaps, updating priorities, and triggering new cycles. A system that doesn't review itself is just a filing cabinet.

---

## C — Capture

**Everything starts as input.** A thought, a voice note, a screenshot, a meeting takeaway, a link, a PDF. Capture is the act of getting it *into the system* before it disappears.

### Sources

- Quick text notes (phone, desktop, voice transcription)
- Conversations (meeting notes, call summaries)
- Web clips (articles, references, research)
- Agent output (AI-generated reports, summaries, analysis)
- External feeds (email digests, RSS, notifications)

### Rules

1. **Capture fast, organize later.** Don't stop to categorize in the moment. Get it in.
2. **Use the inbox.** If you don't know where it goes, it goes to `06 Inbox (Queue)/` in the relevant quadrant — or the top-level staging area if the quadrant is unclear.
3. **Use templates.** Even quick captures should use the appropriate template from `_codex/templates/`. This ensures frontmatter is present from the start.
4. **Frontmatter from birth.** Every document gets YAML frontmatter when created — at minimum: `title`, `type`, `status`, `created`, `tags`.

### The Inbox

Every quadrant has a `06 Inbox (Queue)/` subdirectory for unsorted captures. During the Organize step (or the weekly review), items get routed to their proper domain folder.

---

## O — Organize

**Structure is what makes the system navigable — for humans and AI.**

### The Four Quadrants

| ID Range | Quadrant | Domain |
|----------|----------|--------|
| 00–24 | **UI** — Unified Intelligence | Technology, AI, infrastructure |
| 25–49 | **HP** — Holistic Performance | Health, skills, personal growth |
| 50–74 | **LE** — Legacy Evolution | Family, home, estate |
| 75–99 | **GE** — Generational Entrepreneurship | Business, ventures, wealth |

### The 100-Domain System

Each quadrant has 25 numbered domains (e.g., `00 System Core`, `25 Physical Training`, `50 Home`, `75 Strategy`). Domains are the primary organizational unit — more stable than projects, more granular than quadrants.

Domain folders contain subfolders for topics, projects, and document types as needed. The numbering provides deterministic ordering and makes navigation predictable for both humans and agents.

### Frontmatter

Every document has YAML frontmatter. This is non-negotiable — it's how agents navigate the vault without reading every file.

```yaml
---
title: "Document Title"
type: note                    # note | decision | sop | project | person | review | doctrine | reference | log
status: active                # active | draft | archived | paused
created: 2026-03-19
updated: 2026-03-19
owner: zeus
domain: "00 System Core"
tags: [type/note, domain/system, status/active]
ai_summary: "One-line summary an AI agent can scan without reading the full document"
---
```

### Tags

Tags follow a namespace convention:

- `type/*` — document type (`type/note`, `type/sop`, `type/decision`)
- `domain/*` — knowledge domain (`domain/system`, `domain/health`, `domain/business`)
- `status/*` — document status (`status/active`, `status/draft`, `status/archived`)
- `project/*` — project association (`project/onemind`, `project/farm`)
- `agent/*` — agent relevance (`agent/legacy`, `agent/spartan`)

---

## D — Direct

**Prioritize, decide, and route.** This is the bridge between organized knowledge and action.

### Prioritization

Not everything captured deserves execution. The Direct step is where you:

1. **Triage the inbox** — route captured items to domains or archive them.
2. **Set priorities** — mark what's urgent, important, or deferred.
3. **Assign ownership** — is this a human task or an agent task?
4. **Define success** — what does "done" look like?

### Routing

| Route | When |
|-------|------|
| **Human** | Requires judgment, creativity, or physical presence |
| **AI Agent** | Research, analysis, drafting, monitoring, data processing |
| **Automated** | Recurring tasks, scheduled reports, system maintenance |
| **Deferred** | Not urgent, park it with a review trigger |

### Decision Documents

Non-trivial decisions get their own document using the `decision` template. This captures context, options considered, rationale, and outcome — creating an audit trail that agents and future-you can reference.

---

## E — Execute

**Action happens here.** This is where One Mind diverges from every prior framework — because execution isn't human-only anymore.

### Human Execution

Some things only humans can do: physical tasks, relationship conversations, creative work requiring taste, high-stakes decisions. These get tracked as tasks with clear ownership.

### Agent Execution

AI agents can:

- **Research** — gather information, summarize sources, compare options
- **Draft** — write documents, emails, proposals, reports
- **Analyze** — process data, generate insights, build comparisons
- **Monitor** — watch for changes, alert on conditions, track progress
- **Maintain** — update documents, clean inboxes, enforce conventions

Agents execute against SOPs (Standard Operating Procedures) documented in the vault. An SOP defines the steps, tools, inputs, outputs, and quality criteria — so an agent knows exactly what "do this task" means.

### Skills

Agent skills are defined in `_codex/skills/`. Each skill is a structured definition of a capability — what it does, what tools it uses, what inputs it needs, what outputs it produces. Skills compose into workflows.

---

## X — eXamine

**The feedback loop that makes the system compound.**

Without review, a knowledge system decays into a digital junk drawer. eXamine is the discipline that prevents this.

### Weekly Review

Every week:

1. **Process inboxes** — route or archive every captured item
2. **Update active projects** — status check on in-progress work
3. **Review agent output** — what did agents produce? Is it meeting standards?
4. **Adjust priorities** — what's changed? What's more urgent now?
5. **Capture reflections** — what worked, what didn't, what to change

### Monthly Review

Every month:

1. **Quadrant health check** — are all four quadrants getting attention or is one starving?
2. **Metric review** — track key metrics for each quadrant
3. **System maintenance** — archive stale documents, update templates, refine conventions
4. **Goal alignment** — are daily actions serving quarterly/annual goals?

### Review Profiles

`_codex/profiles/` contains structured review profiles — checklists and prompts for weekly and monthly reviews. These can be run by humans alone or co-piloted with an AI agent.

---

## Progressive Disclosure

Agents (and humans) don't need to read everything to navigate the vault. The system is designed for layered context loading:

| Level | What | When |
|-------|------|------|
| **L0** | `_codex/system/` — pinned context files | Always loaded first. Contains current state, active priorities, operational rules. |
| **L1** | `ai_summary` field in frontmatter | Scan across many files quickly. Read the one-liner to decide if the full document matters. |
| **L2** | Full document content | Read when the summary indicates relevance. |
| **L3** | Linked documents (wiki-links, references) | Follow when deeper context is needed. |

This means an agent can understand the current state of your life by reading ~5 system files (L0), scan 100 documents by reading 100 one-liners (L1), and only deep-read the 3 that matter (L2). Efficient, focused, scalable.

---

## Document Types

| Type | Purpose | Template |
|------|---------|----------|
| `note` | General knowledge capture, observations, ideas | `_codex/templates/note.md` |
| `decision` | Record of a decision with context, options, and rationale | `_codex/templates/decision.md` |
| `sop` | Standard Operating Procedure — step-by-step execution guide | `_codex/templates/sop.md` |
| `project` | Active project with goals, milestones, and status | `_codex/templates/project.md` |
| `person` | Contact profile, relationship context, interaction history | `_codex/templates/person.md` |
| `review` | Weekly/monthly review output | `_codex/templates/review.md` |
| `doctrine` | Core philosophy, framework definition, system-level truth | `_codex/templates/doctrine.md` |
| `reference` | External resource, API doc, specification, guide | `_codex/templates/reference.md` |
| `log` | Timestamped activity log, journal entry, agent output | `_codex/templates/log.md` |

Each type has a dedicated template with the correct frontmatter fields pre-filled. Always use the template — consistency is what makes the system machine-readable.

---

## Build Your CODEX

The framework is the skeleton. Your content is the muscle. Start with Capture — get things into the system. Organize when the inbox fills up. Direct when you sit down to plan. Execute with every action. Examine every week.

The loop compounds. Every cycle makes the system smarter, the agent context richer, and your decisions better-informed.

That's the CODEX.

---

*Part of the One Mind framework. See [ONEMIND-CODEX.md](ONEMIND-CODEX.md) for the master document.*
