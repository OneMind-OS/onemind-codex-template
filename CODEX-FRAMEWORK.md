---
title: "THE CODEX FRAMEWORK"
type: doctrine
status: active
created: 2026-03-19
updated: 2026-03-26
owner: zeus
tags: [type/doctrine, status/active]
ai_summary: "Deep dive on the CODEX method — Capture, Organize, Direct, Execute, × Multiply — with entity taxonomy, progressive activation, and the full system design"
---

# THE CODEX FRAMEWORK

> Capture → Organize → Direct → Execute → × Multiply

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

## The Codex as a Harness

In 2026, both [OpenAI](https://openai.com/index/harness-engineering/) and [Anthropic](https://www.anthropic.com/engineering/harness-design-long-running-apps) independently arrived at the same conclusion: **AI agents need structured infrastructure around them to work reliably.** They call this infrastructure a "harness."

### What Is Harness Engineering?

A harness is NOT the AI model itself — it's the environment that governs how the model operates:

- **Structured artifacts** — typed files with metadata that agents can read and act on
- **Guardrails** — explicit rules about what agents can and cannot do
- **Feedback loops** — evaluator processes that grade agent output and feed corrections back
- **Context state** — persistent files that carry context across sessions so agents don't "forget"
- **Decomposed tasks** — breaking large work into tractable chunks with clear "done" criteria

Without a harness, agents lose coherence on long tasks, confidently produce mediocre work, and go off the rails over time. With a harness, they produce dramatically better results.

### How This Maps to the CODEX Method

The codex IS a harness — not for a coding project, but for your entire life. Every concept from harness engineering has a direct equivalent in the CODEX method:

| Harness Engineering (for code) | CODEX Method (for life) |
|-------------------------------|------------------------|
| **Planner agent** — expands a prompt into a full spec with sprints | **Direct** — prioritize, assign operators, define success criteria |
| **Generator agent** — builds one feature per sprint | **Execute** — operators (human or AI) run the work |
| **Evaluator agent** — grades output, files bugs, sends feedback | **× Multiply** — review, measure, extract lessons, feed back |
| **Structured artifacts** — typed files with metadata for context handoff | **Entity types** — 17 types with frontmatter (type, status, operator, realm) |
| **Sprint contracts** — agree on "done" before building | **Goal/task templates** — success criteria defined before execution |
| **Context state files** — carry agent memory across sessions | **`_codex/system/`** — pinned context + `ai_summary` fields on every document |
| **File-based agent communication** — one agent writes, another reads | **The codex vault** — agents read and write markdown files with shared conventions |
| **Decomposed tasks** — break big work into tractable chunks | **Progressive activation** — start with 3 domains + SO, expand to 100 domains |

### Why This Matters

OpenAI and Anthropic built temporary harnesses — they scaffold a coding project for hours or days, then the harness is done. **The codex is a permanent harness** — it scaffolds your entire life, indefinitely. Every cycle through C.O.D.E.× doesn't just complete work — it strengthens the harness itself. SOPs get refined. Agent context gets richer. Metrics compound. The system learns.

This is the same engineering pattern that the world's best AI labs use to make agents effective. The difference is scope:

| | Their Harness | Your Codex |
|---|---|---|
| **Scope** | One coding project | Your entire life |
| **Duration** | Hours to days | Permanent (compounds over years) |
| **Agents** | Coding agents (write code) | Life agents (manage health, family, business) |
| **Artifacts** | Code files, specs, test results | Goals, tasks, decisions, SOPs, AOPs, reviews |
| **Evaluator** | Automated test runner | × Multiply loop (weekly/monthly/quarterly reviews) |

### Further Reading

- **OpenAI** — [Harness Engineering](https://openai.com/index/harness-engineering/) — why AI agents need structured infrastructure to work reliably at scale
- **Anthropic** — [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) — the original harness design principles
- **Anthropic** — [Harness Design for Long-Running Apps](https://www.anthropic.com/engineering/harness-design-long-running-apps) — multi-agent architecture (planner → generator → evaluator) with feedback loops and structured artifacts
- **Anthropic** — [Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — how to manage agent context state (the problem `_codex/system/` solves)

> **The takeaway:** When Anthropic and OpenAI tell the engineering world that AI agents need structured harnesses with typed artifacts, feedback loops, and guardrails — they're describing the CODEX. We just built it for life instead of code.

---

## The CODEX Method

Five steps. One compounding loop.

```
  ┌─────────┐    ┌───────────┐    ┌────────┐    ┌─────────┐    ┌──────────┐
  │ CAPTURE │───▶│ ORGANIZE  │───▶│ DIRECT │───▶│ EXECUTE │───▶│ × MULTI- │
  │         │    │           │    │        │    │         │    │   PLY    │
  └─────────┘    └───────────┘    └────────┘    └─────────┘    └──────────┘
   Inbox, voice,   3 domains + SO, Command:       Operators      Review,
   quick capture   100 domains,    prioritize,    run the work:  measure,
   from anywhere   entity types,   assign owner,  humans, agents,extract
                   frontmatter     define done     SOPs, skills   lessons
                                                                    │
                        ◀─── each cycle multiplies the system ─────┘
```

**The X in CODEX is × — the multiplication sign.** Every cycle through the loop doesn't just complete a task. It multiplies the system's intelligence: metrics get tracked, SOPs get refined, agents get smarter, knowledge compounds. CODEX isn't a line — it's a flywheel, and × is what makes it spin faster.

---

## C — Capture

**Everything starts as input.** A thought, a voice note, a screenshot, a meeting takeaway, a link, a PDF. Capture is the act of getting it *into the system* before it disappears.

### The Key Insight

Capture isn't about writing good notes. It's about **reducing friction to zero** so nothing falls through cracks. A bad capture you can find later beats a perfect note you never wrote.

### Sources

| Trigger | Capture Method | Where It Lands |
|---------|---------------|----------------|
| Thought in the shower | Voice memo on phone | Inbox |
| Meeting takeaway | Quick text note | Relevant domain inbox |
| Article worth saving | Web clip + 1-line summary | Inbox |
| Agent produced a report | Auto-saved by agent | Domain folder directly |
| Dream/idea at 2am | Bedside notepad → photo | Inbox |
| Business opportunity | Voice note → transcription | GE inbox |

### Rules

1. **Capture fast, organize later.** Don't stop to categorize in the moment. Get it in. The Organize step handles routing.
2. **Use the inbox.** If you don't know where it goes, it goes to `06 Inbox (Queue)/` in the relevant domain — or the top-level staging area if the domain is unclear.
3. **Use templates.** Even quick captures should use the appropriate template from `_codex/templates/`. This ensures frontmatter is present from the start.
4. **Frontmatter from birth.** Every document gets YAML frontmatter when created — at minimum: `title`, `type`, `status`, `created`, `tags`.

### The Inbox

Every domain group has a `06 Inbox (Queue)/` subdirectory for unsorted captures. During the Organize step (or the weekly review), items get routed to their proper domain folder.

### How Capture Connects to Organize

Your inboxes fill up during the week. During your weekly review (× step), you route them to proper domains. This creates a natural rhythm: **capture freely all week → organize during review**. You never stop mid-thought to file something.

---

## O — Organize

**Give everything an address so it can be found.**

Organize answers ONE question: **WHERE does this live and WHAT is it?**

Organize does NOT decide priority, ownership, deadlines, or what happens next — that's Direct. Organize is purely about **classification and placement**.

### What Organize Does (and Doesn't Do)

| Organize DOES | Organize DOES NOT |
|--------------|-------------------|
| Route to the right domain | Decide if it matters |
| Assign an entity type (goal, note, task, etc.) | Assign who does it |
| Add frontmatter and tags | Set deadlines or priorities |
| Make things findable by humans and AI | Define success criteria |

**Think of it this way:** Organize is the librarian. Direct is the general. The librarian files the book on the right shelf. The general decides which book matters and what to do about it.

### The Three Organizing Actions

1. **Route** — move from inbox to the right domain folder
2. **Type** — assign the entity type (is this a note? a goal? a task? a decision?)
3. **Tag** — add frontmatter so AI can find it without reading it

### Example: Same Item Through O Then D

```
CAPTURED: "I should start running again"

O — ORGANIZE:
   Route:  HP / 27 Body (it's about health)
   Type:   goal (it's something I want to achieve)
   Tag:    type/goal, domain/hp, status/draft
   File:   HP/27-Body/goal-start-running.md
   ✅ Now it has an address and a type. Organize is done.

D — DIRECT:
   Priority:  High (doctor said I need to move more)
   Operator:  Human (I have to do the actual running)
   Done:      "Run 3x/week for 4 consecutive weeks"
   Timeline:  Start this Monday, checkpoint in 30 days
   Breakdown: Create PROJECT "April Running Plan" → TASKS for each run
   ✅ Now it has ownership, priority, criteria, and a timeline. Direct is done.
```

**Without Organize**, Direct has nowhere to put things and no types to work with.
**Without Direct**, Organize creates a beautifully filed system that never takes action.

### The 3 Domains + 1 Operating Layer

| ID Range | Domain Group | What Lives Here |
|----------|----------|--------|
| 00–24 | **SO** — Sovereign Operations | Technology, AI, infrastructure |
| 25–49 | **HP** — Holistic Performance | Health, skills, personal growth |
| 50–74 | **LE** — Legacy Evolution | Relationships, community, home |
| 75–99 | **GE** — Generational Endeavor | Career, ventures, impact, wealth |

### The 100-Domain System

Each group has 25 numbered domains (e.g., `00 System Core`, `25 Identity`, `50 Home`, `75 Brand`). Domains are the primary organizational unit — more stable than projects, more granular than the top-level groups.

**You don't start with 100 domains.** See [Progressive Activation](#progressive-activation) below — you start with 3 domains + SO and activate domains as your life expands. The 100 slots are the ceiling, not the floor.

### How Organize Connects to Direct

Once something has an address and a type, the Direct step can evaluate it. You can't prioritize or assign things that are floating in an inbox without context. Organization makes direction possible — it turns "stuff" into "actionable items with coordinates."

### Entity Types

Every piece of information in the vault has a **type** that tells both humans and AI what it is. The Organize step is where you assign the right type. See [Entity Taxonomy](#entity-taxonomy) for the full list.

### Frontmatter

Every document has YAML frontmatter. This is non-negotiable — it's how agents navigate the vault without reading every file.

```yaml
---
title: "Document Title"
type: goal                    # See Entity Taxonomy for all types
status: active                # active | draft | archived | paused
created: 2026-03-19
updated: 2026-03-19
owner: zeus                   # human name, agent name, or "system"
operator: human               # human | agent | robot | drone | automated
realm: digital                # digital | physical | hybrid
domain: "00 System Core"
tags: [type/goal, domain/system, status/active]
ai_summary: "One-line summary an AI agent can scan without reading the full document"
---
```

### Tags

Tags follow a namespace convention:

- `type/*` — entity type (`type/goal`, `type/task`, `type/sop`, `type/agent`)
- `domain/*` — knowledge domain (`domain/system`, `domain/health`, `domain/business`)
- `status/*` — document status (`status/active`, `status/draft`, `status/archived`)
- `project/*` — project association (`project/onemind`, `project/farm`)
- `operator/*` — who owns execution (`operator/legacy`, `operator/zeus`, `operator/spartan`)

---

## D — Direct

**Decide what matters, who does it, and what "done" looks like.**

Direct answers a DIFFERENT question than Organize. Organize asked "where does this live?" Direct asks: **"What happens to it?"**

### Organize vs. Direct — The Clear Line

| | O — Organize | D — Direct |
|---|---|---|
| **Question** | Where does this live? What is it? | Does it matter? Who does it? When? |
| **Actions** | Route, type, tag | Prioritize, assign, define done, set deadline |
| **Metaphor** | Filing a medical chart | Doctor reading the chart and prescribing treatment |
| **Output** | A classified, findable document | A prioritized, assigned, actionable command |
| **Who does it** | Often during weekly review or at capture time | During planning sessions and daily prioritization |

**The handoff:** Organize creates well-addressed, typed entities. Direct picks them up and turns them into commands with ownership and deadlines.

**Direct is where you stop being a note-taker and become a commander.**

### The Four Commands

Every item that reaches the Direct step gets answered:

```
┌──────────────────────────────────────────────────────────────────────┐
│                          D — DIRECT                                  │
│                                                                      │
│  1. DOES IT MATTER? → Priority  (critical / high / medium / low)    │
│  2. WHO DOES IT?    → Operator  (human / agent / robot / drone)     │
│  3. WHAT IS "DONE"? → Criteria  (measurable success definition)     │
│  4. WHEN?           → Timeline  (deadline, cadence, or trigger)     │
│                                                                      │
│  INPUT:  Organized entities with addresses and types                 │
│  OUTPUT: Commanded work with clear ownership and success criteria    │
└──────────────────────────────────────────────────────────────────────┘
```

Note: "What TYPE is it?" is NOT a Direct question — that was handled in Organize. Direct works with already-typed entities.

### Why "Direct" Beats "Distill"

| | Forte's "Distill" | One Mind's "Direct" |
|---|---|---|
| **What it does** | Highlight the important parts of a note | Decide what gets done, by whom, when, and what "done" means |
| **Who benefits** | You (you read your own highlights later) | The entire system — humans AND agents get marching orders |
| **Output** | A shorter, highlighted note | An assigned, prioritized, owned action with success criteria |
| **Metaphor** | Editor highlighting a book | Commander directing an operation |
| **AI role** | None | AI can be the one receiving the direction |

**Distill is passive.** You're making notes easier to re-read.
**Direct is active.** You're making decisions and deploying resources.

### The Direction Hierarchy

Direct works at three levels:

```
GOAL    "Run a marathon by December"           ← Long-term outcome
  └── PROJECT  "Q2 Marathon Training Block"    ← Bounded effort toward the goal
        ├── TASK  "Run 5 miles Tuesday"        ← Single action
        ├── TASK  "Book sports massage"        ← Single action
        ├── SOP   "Weekly long run protocol"   ← Repeatable human process
        └── AOP   "Auto-generate weekly plan"  ← Agent-executed procedure
```

Each level can have a different operator:
- The **Goal** is human-directed (you set the vision)
- The **Project** might be co-piloted (agent tracks progress, human does the work)
- Individual **Tasks** can be routed to agents (research, scheduling, analysis)
- **SOPs** define exactly how repeatable work gets done by humans
- **AOPs** define exactly how repeatable work gets done by agents

### Routing Table

| Operator | Route To When... | Examples |
|----------|-----------------|----------|
| **Human** | Requires judgment, creativity, physical presence, or high-stakes decisions | Exercise, parenting, client calls, creative writing |
| **Agent** | Research, analysis, drafting, monitoring, data processing | Market research, email drafts, metric tracking, inbox triage |
| **Robot** | Physical automation, sensor monitoring | Smart home, security cameras, manufacturing |
| **Drone** | Autonomous physical tasks, remote operations | Property survey, delivery, agricultural monitoring |
| **Automated** | Recurring tasks, scheduled events, system maintenance | Backups, report generation, scheduled reminders |

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

Agents execute against **AOPs** (Agent Operations Procedures) documented in the vault. An AOP defines structured inputs, deterministic steps, tools, outputs, error handling, and guardrails — everything an agent needs to run a procedure autonomously.

Humans execute against **SOPs** (Standard Operating Procedures). SOPs are human-readable step-by-step guides. An SOP can be delegated to an agent in a pinch, but AOPs are purpose-built for agent execution.

### SOP vs. AOP

| | SOP (Standard Operating Procedure) | AOP (Agent Operations Procedure) |
|---|---|---|
| **Written for** | Humans (with agent delegation possible) | Agents (machine-parseable by design) |
| **Structure** | Natural language steps, context, judgment calls | Structured inputs, deterministic steps, defined outputs |
| **Includes** | Purpose, steps, expected outcome, troubleshooting | Trigger, inputs table, tools per step, outputs table, error handling, guardrails |
| **Autonomy** | Human runs it, may ask agent for help | Agent runs it, escalates to human on exceptions |
| **Example** | "Weekly grocery shopping" — check fridge, make list, go to store | "Weekly inbox triage" — scan inbox, categorize by type, route to domains, flag unknowns |

### The Three Execution Modes

| Mode | What Happens | Human Involvement |
|------|-------------|-------------------|
| **Human-only** | You do the work. Log the result. | 100% — physical tasks, creative work, relationships |
| **Agent-assisted** | Agent does the work, you review the output | 20% — review and approve |
| **Fully automated** | System runs on schedule or trigger, results logged | 0% — until the next review cycle |

Most beginners start with 100% human execution. As you write SOPs and configure agents, the ratio shifts. An established system might run 40-60% through agents.

### Skills & Tools

**Skills** are portable capability definitions in `_codex/skills/`. Each skill describes what it does, what inputs it needs, and what it outputs. Skills are agent-agnostic — any AI can learn them.

**Tools** are specific software or hardware bound to an environment (Obsidian, Claude, a 3D printer). Tools enable skills. Skills are the "what," tools are the "with what."

```
SKILL: "Research a market competitor"
  TOOLS USED: web search, Claude, spreadsheet
  INPUT: competitor name, industry
  OUTPUT: competitive analysis document

SKILL: "Monitor soil moisture"
  TOOLS USED: IoT sensors, dashboard
  INPUT: field zone ID
  OUTPUT: moisture readings + irrigation alert
```

### How Execute Connects to ×

Every execution produces OUTPUT — a completed task, a generated report, a metric reading, a decision outcome. That output feeds into the × step, where you evaluate: did it work? What can we learn? What should we change? Execute without × is just busywork. Execute WITH × is a learning machine.

---

## × — Multiply

**The compounding engine. Every cycle through CODEX multiplies the system's intelligence.**

The × step is what separates a living system from a digital junk drawer. Without it, you capture and execute but never improve. With it, each cycle makes the entire system smarter:

- **SOPs get refined** — what didn't work gets fixed
- **Metrics get tracked** — you see trends, not just events
- **Agents get smarter** — their context improves with every review
- **Knowledge compounds** — lessons feed back into Capture as new inputs

### Weekly Review (~30 min)

Every week:

1. **Process inboxes** — route or archive every captured item
2. **Update active projects** — status check on in-progress work
3. **Review agent output** — what did agents produce? Is it meeting standards?
4. **Adjust priorities** — what's changed? What's more urgent now?
5. **Capture reflections** — what worked, what didn't, what to change

### Monthly Review (~60 min)

Every month:

1. **Domain health check** — are all three life domains getting attention or is one starving?
2. **Metric review** — track key metrics for each domain
3. **System maintenance** — archive stale documents, update templates, refine conventions
4. **Goal alignment** — are daily actions serving quarterly/annual goals?

### Quarterly Review (~2-3 hours)

Every quarter:

1. **Read all monthly reviews** — identify patterns and themes
2. **Review major decisions** — are they holding up?
3. **Review long-term projects** — on track or need recalibration?
4. **Set next quarter priorities** — update `_codex/system/active-goals.md`

### Review Profiles

`_codex/profiles/` contains structured review profiles — checklists and prompts for weekly, monthly, and quarterly reviews. These can be run by humans alone or co-piloted with an AI agent.

### How × Connects Back to Capture

Every review surfaces new inputs: gaps you didn't notice, priorities that shifted, SOPs that need updating, ideas triggered by reflection. These go back into Capture — completing the loop. The system is a flywheel:

```
CYCLE 1:  Messy. You're learning the system. Everything feels manual.
CYCLE 4:  Smoother. Templates and SOPs are working. Inboxes are smaller.
CYCLE 12: Compounding. Agents handle 30-40% of execution. Reviews are faster.
CYCLE 52: Multiplied. The system practically runs itself.
          You direct. It executes. × tracks. The loop never stops.
```

---

## Entity Taxonomy

One Mind knows WHAT something is, WHO owns it, and WHERE it lives. PARA treats everything as "a note in a folder." Your system has 17 entity types across 5 categories.

### The Full Entity System

```
CODEX ENTITY SYSTEM
│
├── 🎯 INTENT (what you want)
│   ├── goal        — Long-term outcome ("Run a marathon by December")
│   ├── project     — Bounded effort toward a goal ("Marathon training plan")
│   └── task        — Single action ("Run 5 miles Tuesday")
│
├── 🧠 KNOWLEDGE (what you know)
│   ├── note        — Captured thought, observation, idea
│   ├── decision    — Recorded choice with context + rationale
│   ├── doctrine    — Core philosophy, non-negotiable truth
│   ├── reference   — External resource, spec, guide
│   ├── sop         — Standard Operating Procedure (human-readable repeatable process)
│   └── aop         — Agent Operations Procedure (agent-native execution contract)
│
├── 📊 MEASUREMENT (how you track)
│   ├── metric      — Tracked number (weight, revenue, sprint pace)
│   └── review      — Periodic assessment (weekly, monthly, quarterly)
│
├── 🤖 OPERATOR (who/what does the work)
│   ├── human       — You, family member, team member, contractor
│   ├── agent       — AI agent (Legacy, Spartan, Oracle, etc.)
│   ├── robot       — Physical automation (smart home, CNC, etc.)
│   └── drone       — Autonomous physical agent
│
└── 🔧 CAPABILITY (what you can do)
    ├── skill       — Portable ability definition (research, draft, analyze)
    └── tool        — Specific software/hardware (Obsidian, Claude, 3D printer)
```

### How Entities Map to CODEX Steps

| CODEX Step | Primary Entities |
|-----------|------------------|
| **C — Capture** | `note`, `reference` — raw inputs enter the system |
| **O — Organize** | All types — route to domain, assign type, add frontmatter |
| **D — Direct** | `goal` → `project` → `task` (break down intent), assign `operator`, set priority/deadline |
| **E — Execute** | `task` + `sop`/`aop` + `skill` + `tool` — operators run the work |
| **× — Multiply** | `metric` + `review` — track results, refine SOPs/AOPs, compound value |

### Entity Coordinates

Every entity has **three coordinates** that tell you exactly where it lives and what it is:

```
DOMAIN GROUP → DOMAIN → ENTITY TYPE

HP / 27-Body     / goal-run-marathon.md
HP / 27-Body     / metric-weight.md
HP / 27-Body     / sop-morning-workout.md
HP / 27-Body     / aop-generate-weekly-plan.md
GE / 84-Ventures / project-launch-academy.md
GE / 84-Ventures / task-setup-stripe.md
SO / 02-Agents   / agent-legacy.md
SO / 02-Agents   / skill-research.md
SO / 09-Automation / aop-inbox-triage.md
LE / 50-Home     / task-fix-fence.md
LE / 50-Home     / robot-irrigation-system.md
LE / 56-Wealth   / note-estate-plan-options.md
```

### Entity Properties

Every entity can carry two key properties in its frontmatter:

| Property | Values | Purpose |
|----------|--------|---------|
| `operator` | `human`, `agent`, `robot`, `drone`, `automated` | Who/what is responsible for this entity |
| `realm` | `digital`, `physical`, `hybrid` | Is this entity in the digital world, physical world, or both |

Examples:
- A `task` to write a blog post → `operator: agent`, `realm: digital`
- A `task` to fix the fence → `operator: human`, `realm: physical`
- A `project` to launch a product → `operator: human`, `realm: hybrid`
- A `metric` for soil moisture → `operator: robot`, `realm: physical`

---

## The CODEX Loop

**This is the most important concept in the entire framework.** CODEX is not a line. It's a loop. And every cycle through the loop multiplies the system's intelligence.

```
              ┌───────────────────────────────────┐
              │                                     │
              ▼                                     │
         ┌─────────┐                                │
         │    C     │  Capture                      │
         │ (input)  │  "Get it in"                  │
         └────┬─────┘                                │
              │                                     │
              ▼                                     │
         ┌─────────┐                                │
         │    O     │  Organize                     │
         │ (route)  │  "Give it an address"         │
         └────┬─────┘                                │
              │                                     │
              ▼                                     │
         ┌─────────┐                                │
         │    D     │  Direct                       │
         │(command) │  "Decide what happens"        │
         └────┬─────┘                                │
              │                                     │
              ▼                                     │
         ┌─────────┐                                │
         │    E     │  Execute                      │
         │ (action) │  "Do the work"                │
         └────┬─────┘                                │
              │                                     │
              ▼                                     │
         ┌─────────┐                                │
         │    ×     │  Multiply                     │
         │(compound)│  "Review, learn, improve"     │
         └────┬─────┘                                │
              │                                     │
              │   New insights, updated priorities,  │
              │   refined SOPs/AOPs, fresh metrics   │
              │                                     │
              └─────────── feed back into C ────────┘
```

### How the Loop Works in Practice

**Weekly cycle (the core rhythm):**

```
MONDAY-SATURDAY: The Working Week
─────────────────────────────────
C — Capture thoughts, notes, ideas all week (fast, messy, into inboxes)
O — Quick-route obvious items as you capture them
D — Daily 5-min priority check: what matters today? Who's doing it?
E — Humans work, agents run AOPs, tasks get completed

SUNDAY: The × Day (30 minutes)
────────────────────────────────
× — Process inboxes (route or archive everything)
× — Review what got done vs. what was planned
× — Check metrics (are numbers moving right?)
× — Extract lessons (what worked? what broke?)
× — Set next week's priorities (feeds back into D)
× — Capture new insights from the review (feeds back into C)
    ↕
    The loop restarts. But now the system knows more.
```

**Monthly cycle (zoom out):**

```
× — Read the last 4 weekly reviews → see patterns
× — Domain health check → is any area of life starving?
× — SOP/AOP audit → are procedures working or need refinement?
× — Goal alignment → are daily actions serving quarterly goals?
× — Capture: new goals, updated priorities, refined procedures
    ↕
    The loop restarts at a higher level.
```

**Quarterly cycle (zoom way out):**

```
× — Read all monthly reviews → see the big picture
× — Major decision audit → are past decisions holding up?
× — Long-term project check → on track or need recalibration?
× — Set OKRs / themes for next quarter
× — Capture: strategic insights, updated identity, new doctrines
    ↕
    The loop restarts with fresh strategic clarity.
```

### The Multiplication Effect

Here's what compounding looks like over time:

```
WEEK 1:   You capture 20 items. Organize 15. Direct 10. Execute 5.
          × Review: "I'm over-capturing and under-executing."
          LESSON → Be more selective at Capture. Write clearer tasks at Direct.

WEEK 4:   Capture 12 (more selective). Organize 12. Direct 10. Execute 8.
          × Review: "Inbox triage takes 30 min. Agent could do this."
          LESSON → Write an AOP for inbox triage.

WEEK 8:   Agent handles inbox triage (AOP). You save 30 min/week.
          × Review: "Agent triage is 85% accurate. Needs better type detection."
          LESSON → Refine AOP with clearer type rules.

WEEK 12:  Agent triage is 95% accurate. You barely touch inboxes.
          × Review: "System handles 40% of Organize step automatically."
          LESSON → What ELSE can I delegate?

WEEK 52:  70% of Organize and 50% of Execute run through agents/automation.
          You spend most of your time on Direct (strategy) and × (review).
          The system multiplied its own intelligence 52 times.
```

**That's the loop. That's why × matters. That's why CODEX compounds.**

---

## Mobile Access

**Your codex lives on your Mac as files and folders, synced to GitHub and your VPS. Here's how to add iPhone access without creating conflicts.**

### Understanding the Sync Architecture

Your codex has multiple sync layers. Before adding mobile, you need to understand what's already running:

```
┌───────────────┐         ┌──────────┐         ┌──────────────────┐
│   YOUR MAC    │ ──git──▶│  GITHUB  │◀──pull──│    VPS           │
│  (Obsidian)   │◀──git── │  (main)  │──push──▶│  (codex-watch)   │
│               │         │          │         │  auto-commit ~3s  │
│               │         │          │         │  auto-pull ~1min  │
└───────────────┘         └──────────┘         └──────────────────┘
       ↕                        │
  Obsidian Sync                 ├──▶ Cloudflare Pages (website)
       ↕                        └──▶ Student Template (auto-sync)
┌───────────────┐
│   iPHONE      │
│  (Obsidian    │
│   Mobile)     │
└───────────────┘
```

**What's already happening:**
- **Mac → GitHub**: You manually commit and push
- **VPS → GitHub**: `codex-watch.service` auto-commits within ~3 seconds of any file change, auto-pushes
- **GitHub → VPS**: `codex-pull.timer` pulls every 1 minute
- **Legacy AI**: Writes to the vault on the VPS, changes auto-commit to GitHub

**What Obsidian Sync adds:**
- **Mac ↔ iPhone**: Obsidian Sync syncs vault files between your two devices
- Obsidian Sync has **zero awareness of Git** — it just syncs files
- When Sync delivers a file change from iPhone → Mac, Git sees it as a local file modification (same as if you edited it yourself)

### Will This Create Conflicts?

**Short answer: No — if you follow one rule.**

Here's why it's safe:

| Scenario | What Happens | Risk |
|----------|-------------|------|
| You create a NEW file on iPhone | Sync delivers it to Mac → you commit → GitHub → VPS pulls it | ✅ **Zero risk** — new files can't conflict |
| You edit a file on iPhone that nobody else touched | Sync delivers edit to Mac → you commit → normal flow | ✅ **Zero risk** — no competing edits |
| You edit a file on iPhone while Legacy AI edits the SAME file on VPS | Sync delivers your version to Mac. VPS pushes Legacy's version to GitHub. When you `git pull`, **merge conflict**. | ⚠️ **This is the only real risk** |

**The one rule that prevents all conflicts:**

> **On mobile, only CREATE new files (captures to inbox). Never EDIT existing files that agents might also touch.**

This is safe because:
1. New files created on iPhone don't exist anywhere else → no conflict possible
2. Obsidian Sync delivers the new file to your Mac
3. Next time you sit at your Mac, commit and push → GitHub → VPS gets it in 1 min
4. Your auto-commit on VPS only touches files that agents write to — never your inbox

### What About the Auto-Commit on VPS?

The VPS `codex-watch.service` auto-commits agent changes within ~3 seconds and pushes to GitHub. This means GitHub may have new commits that your Mac doesn't have yet.

**The flow when you edit on iPhone:**

```
1. You create a note on iPhone (10am, on the go)
2. Obsidian Sync delivers it to Mac (~seconds)
3. Meanwhile, Legacy AI writes a report on VPS (10:15am)
4. VPS auto-commits and pushes to GitHub (10:15am)
5. You sit at Mac (6pm), open terminal:
   a. git pull → gets Legacy's changes from GitHub ✅
   b. git add → stages your new iPhone capture ✅
   c. git commit && git push → sends both to GitHub ✅
   d. VPS picks up your capture within 1 min ✅
```

**No conflict** because your iPhone capture is a NEW file and Legacy's edit is a DIFFERENT file.

### What Does NOT Sync to Git from iPhone

**Obsidian Sync ≠ Git.** Editing on your iPhone does NOT automatically commit to Git or push to GitHub. The flow is:

```
iPhone edit → Obsidian Sync → Mac filesystem (local change only)
                                    ↓
                        You must manually: git add → commit → push
                                    ↓
                              Then GitHub and VPS get it
```

If you want iPhone captures to reach the VPS faster, you could add an auto-commit script on your Mac (like the VPS has). But for now, manual commit when you sit down at your Mac is fine.

### Obsidian Sync Setup

**Recommended plan: Obsidian Sync Standard — $4/month (annual) or $5/month (monthly)**

| | **Standard** | **Plus** |
|---|---|---|
| **Price** | $4/mo annual · $5/mo monthly | $8/mo annual |
| **Vaults** | 1 | 10 |
| **Storage** | 1 GB | 10 GB (expandable to 100 GB) |
| **Max file size** | 5 MB | 200 MB |
| **Version history** | 1 month | 12 months |
| **Devices** | Unlimited | Unlimited |
| **Encryption** | AES-256 E2E | AES-256 E2E |

**Standard is enough for a codex vault.** Your vault is pure markdown — even with hundreds of files, you'll use well under 1 GB. The 5 MB file limit only affects attachments (images, PDFs), not markdown files. Upgrade to Plus only if you start embedding large media or want 12 months of version history inside Obsidian.

#### Step 1 — Set Up Desktop (Mac) First

1. **Obsidian Desktop** → Settings → Core Plugins → enable **Sync**
2. **Settings → Sync** → sign in to your Obsidian account
3. Click **"Create remote vault"** → name it (e.g. `OneMind-Codex`) → pick a region → set an encryption password (this is your E2E key — don't lose it)
4. Wait for the initial upload to finish — watch the Sync log (Settings → Sync → "View sync log") for file counts ticking up
5. **Exclude device-specific files** — in Sync settings, exclude:
   - `node_modules/` (if present)
   - `.obsidian/workspace.json` (device-specific layout)

> **Note on `.git/`:** Obsidian Sync **automatically excludes all dot-folders** (`.git/`, `.vscode/`, etc.) except `.obsidian/`. You do NOT need to manually exclude `.git/` — it's built-in behavior. Your Git repository is safe by default.

#### Step 2 — Connect iPhone

This is where most people get stuck. **You must open a remote vault, not create a new local one.**

1. Open Obsidian on iPhone
2. Tap the vault switcher (bottom-left) → **"Open remote vault"** ← this is the key step
   - ❌ NOT "Create vault"
   - ❌ NOT "Open folder as vault"
   - ✅ **"Open remote vault"**
3. Sign in with the **same Obsidian account** you used on Mac
4. Your remote vault (e.g. `OneMind-Codex`) will appear in the list → tap it
5. Choose a local name → storage location = **"On My iPhone"** (NOT iCloud Drive) → tap Create
6. Wait for initial download — may take a few minutes depending on vault size

#### Step 3 — Verify It's Working

| Check | Where | What You See |
|-------|-------|-------------|
| **Sync status icon** | Bottom status bar on iPhone | Cloud icon — spinning = syncing, checkmark ✅ = synced |
| **Sync log** | Settings → Sync → "View sync log" | Timestamps of recent uploads/downloads with file names |
| **Manual test (iPhone → Mac)** | Create a test note on iPhone | Should appear on Mac within seconds |
| **Reverse test (Mac → iPhone)** | Edit a note on Mac | Open iPhone — change appears after brief sync |

**If you see "Synced" in the sync log with recent timestamps and the cloud icon shows a checkmark, you're connected.** ✅

#### Troubleshooting — Common Issues

| Problem | Fix |
|---------|-----|
| No remote vault showing on iPhone | Make sure you created the remote vault on Desktop first (Step 1, #3) |
| Signed in but nothing syncs | Check you're on the **same Obsidian account** on both devices |
| Vault exists but shows 0 files | Wait — initial sync can take a few minutes for larger vaults |
| "Vault not found" error | Sign out of Sync on iPhone, force-quit the app, reopen, sign back in |
| Changes not appearing | Check Wi-Fi/cellular connection, then check Sync log for errors |
| Duplicate files appearing | Check conflict resolution in Settings → Sync — Obsidian saves both versions for you to merge |

### Why NOT Add Sync or CLI to the VPS

Your VPS is a **headless server**. Both Obsidian CLI and Obsidian Sync require a running Obsidian GUI application — they are "remote controls" for the desktop app, not standalone tools. They cannot run on a headless VPS.

More importantly, adding Sync to VPS would create a **double-sync nightmare**:

| | **Obsidian CLI** | **Obsidian Sync** | **Git (current VPS setup)** |
|---|---|---|---|
| **Requires GUI Obsidian?** | ✅ Yes | ✅ Yes | ❌ No — fully headless |
| **Works on headless VPS?** | ❌ No | ❌ No | ✅ Yes |
| **Conflict risk if added?** | N/A (can't run) | ⚠️ Double-sync: Git AND Sync both pushing changes = guaranteed conflicts | Already working cleanly |

**The architecture stays cleanly separated — each layer does one job:**

```
Obsidian Sync  = Mac ↔ iPhone (file sync only, no Git awareness)
Git            = Mac ↔ GitHub ↔ VPS (source of truth, version control)
Obsidian CLI   = Mac only (safe vault operations where Obsidian Desktop runs)
```

No overlap. No double-sync. No conflicts.

### Why Obsidian Sync Over iCloud (Long-Term)

iCloud sync with Obsidian improved with iOS 18's "Keep Downloaded" feature, but problems persist — especially with larger vaults (2000+ files report slow syncs, stuck uploads, startup lag). More critically for a codex vault:

| | **Obsidian Sync** | **iCloud** |
|---|---|---|
| **Git coexistence** | Safe — auto-excludes `.git/` and all dot-folders by default | **Can corrupt `.git/` metadata** — iCloud doesn't understand Git internals |
| **Conflict handling** | Shows both versions, lets you merge | Silently overwrites (last write wins — you lose the other edit) |
| **Large vault reliability** | Purpose-built for Obsidian vaults of any size | Gets flaky as vaults grow past hundreds of files |
| **Encryption** | Zero-knowledge E2E (even Obsidian can't read your files) | Apple holds the keys |
| **Selective sync** | Exclude folders and file types | All or nothing |
| **Cost** | $4-5/month | Free |

**The `.git/` risk is the dealbreaker.** Your codex is a Git repository synced to GitHub and your VPS. iCloud may try to sync `.git/` internals (index files, pack files, refs), which corrupts the repository. Obsidian Sync auto-excludes `.git/` by design — making it the only safe choice for a Git-tracked vault.

**For a system you're building your entire framework and product around, $5/month is the cost of one coffee to guarantee it doesn't break.**

### Mobile Capture Rules (Safety Rules)

These aren't just convenience — they prevent conflicts with your VPS auto-sync:

1. **CREATE new files only** — write new notes, tasks, ideas in the inbox
2. **Never EDIT existing files on iPhone** — agents on VPS may be editing them too
3. **Always capture to the inbox** (`06 Inbox (Queue)/`) — inboxes are human-only zones, agents don't touch them
4. **Commit from Mac** — when you sit down, `git pull` first, then `git add/commit/push`

### Quick-Capture Workflow (iPhone)

```
Idea hits while you're out →
  Open Obsidian on iPhone →
    New note in 06 Inbox (use note or task template) →
      Write 2-3 sentences →
        Close app →
          Obsidian Sync delivers to Mac (seconds) →
            Next time at Mac: git pull, commit, push →
              VPS gets it within 1 min
```

This keeps mobile friction near zero, Git conflicts at zero, and your VPS auto-sync pipeline unbroken.

---

## Obsidian CLI

**Obsidian 1.12+ ships with an official command-line interface.** This changes everything for CODEX — agents, automations, and you can now operate the vault safely from the terminal instead of editing raw files.

### What It Is

The Obsidian CLI is a **remote control for a running Obsidian app** — not a standalone headless tool. Every command passes through Obsidian's internal API, which means:

- **File moves update wikilinks automatically** — no more broken links from `mv`
- **Property changes update the index instantly** — frontmatter is always consistent
- **Safe to operate while Obsidian is open** — no file-locking conflicts
- **Link graph stays intact** — Obsidian manages all link resolution

If Obsidian isn't running when you execute a CLI command, it launches automatically.

### Setup (macOS)

```bash
# 1. Update Obsidian to v1.12.7+ (download latest installer from obsidian.md)
# 2. In Obsidian: Settings → General → Command line interface → Enable → Register CLI
# 3. Add to PATH in ~/.zshrc:
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
# 4. Reload shell and verify:
source ~/.zshrc
obsidian version
```

> **v1.12.7 update** (March 23, 2026): The installer now bundles a new dedicated binary for CLI use, replacing the old Electron binary method. This makes terminal interactions significantly faster. Autocompletion for commands is now available when using the `id=` parameter.

### 100+ Commands in 8 Categories

| Category | Key Commands | Purpose |
|----------|-------------|---------|
| **File Operations** | `files`, `read`, `create`, `append`, `prepend`, `move`, `delete` | Note CRUD — create, read, update, delete notes safely |
| **Properties** | `properties`, `property:set`, `property:remove` | Frontmatter/YAML manipulation |
| **Search** | `search`, `search:context` | Full-text vault search with context |
| **Tags** | `tags`, `tag`, `tags:rename` | List, filter, and bulk rename tags |
| **Links** | `links`, `backlinks`, `unresolved`, `orphans` | Link graph health and analysis |
| **Daily Notes** | `daily`, `daily:append`, `daily:read` | Daily note operations |
| **Plugins** | `plugins`, `plugin:enable`, `plugin:disable` | Plugin lifecycle management |
| **Developer** | `eval`, `devtools`, `dev:screenshot` | JS execution, debugging, internal API access |

### Command Syntax

```bash
obsidian <command> [param=value] [flag]

# If multiple vaults exist, specify which one:
obsidian vault="OneMind-Codex" search query="TODO"
```

**Output formats** — most commands support `format=` for scripting:

| Format | Use Case |
|--------|----------|
| `json` | Pipe through `jq` for programmatic use |
| `csv` / `tsv` | Spreadsheet export |
| `md` | Markdown output |
| `paths` | File paths only (for piping to other commands) |
| `text` | Human-readable (default) |
| `tree` | Folder hierarchy |
| `yaml` | YAML format (default for properties) |

### Essential CODEX Operations

**File operations — the safe way to manage your vault:**

```bash
# List all notes in vault
obsidian files

# Read a note
obsidian read file="06 Inbox (Queue)/quick-idea"

# Create a new note (with template)
obsidian create name="06 Inbox (Queue)/new-task" template="task"

# Create with inline content
obsidian create name="06 Inbox (Queue)/capture" content="# Quick Thought\nSomething I need to process later"

# Append to a note (add content to end)
obsidian append file="daily/2026-03-25" content="\n- [ ] Review framework docs"

# Move a note (wikilinks update automatically!)
obsidian move file="06 Inbox (Queue)/new-task" to="01 Projects (Active)/"

# Delete (to trash)
obsidian delete file="old-note"
```

**Properties — frontmatter without manual YAML editing:**

```bash
# View all properties on a note
obsidian properties file="goals/q2-revenue"

# Set entity type, status, operator
obsidian property:set file="goals/q2-revenue" name="type" value="goal"
obsidian property:set file="goals/q2-revenue" name="status" value="active"
obsidian property:set file="goals/q2-revenue" name="operator" value="human"

# Remove a property
obsidian property:remove file="goals/q2-revenue" name="deprecated-field"

# Bulk-set a property across all notes with a tag
obsidian tag tag="#inbox" format=paths | while read -r f; do
  obsidian property:set file="$f" name="status" value="unprocessed"
done
```

**Search — find anything in the vault:**

```bash
# Full-text search
obsidian search query="revenue target"

# Search with surrounding context (like grep -C)
obsidian search:context query="Legacy AI" limit=10

# Search and output as JSON for scripting
obsidian search query="type: goal" format=json | jq '.[].file'
```

**Tags — vault-wide tag management:**

```bash
# List all tags with counts
obsidian tags counts

# Find all notes with a specific tag
obsidian tag tag="#active"

# Bulk rename a tag across entire vault
obsidian tags:rename old=wip new=in-progress
```

**Links — vault health checks:**

```bash
# Find all outgoing links from a note
obsidian links file="ONEMIND-CODEX"

# Find all backlinks to a note
obsidian backlinks file="goals/q2-revenue"

# Find broken links (targets that don't exist)
obsidian unresolved

# Find orphan notes (nothing links to them)
obsidian orphans
```

**Daily notes — terminal-native daily capture:**

```bash
# Open (or create) today's daily note
obsidian daily

# Append a task to today's daily note
obsidian daily:append content="- [ ] Review CODEX framework updates"

# Read today's content
obsidian daily:read
```

### TUI Mode (Interactive Terminal)

Running `obsidian` with no arguments launches a **full-screen Terminal User Interface**:

| Key | Action |
|-----|--------|
| Arrow keys | Navigate files |
| `/` | Filter by filename |
| `Enter` | Open in Obsidian |
| `n` | Create new note |
| `d` | Delete file |
| `r` | Rename |
| `Ctrl+R` | Search command history |
| `q` | Quit |

Supports tab completion and command history — browse your entire codex without leaving the terminal.

### How CLI Fits the CODEX Sync Architecture

```
┌───────────────────┐         ┌──────────┐         ┌──────────────────┐
│     YOUR MAC      │ ──git──▶│  GITHUB  │◀──pull──│      VPS         │
│                   │◀──git── │  (main)  │──push──▶│  (codex-watch)   │
│  Obsidian Desktop │         │          │         │  auto-commit ~3s │
│  Obsidian CLI ◀───┼── YOU   │          │         │  auto-pull ~1min │
│  Obsidian CLI ◀───┼── Mac   │          │         │                  │
│                   │  Agents │          │         │  Legacy AI       │
└───────────────────┘         └──────────┘         │  (writes files   │
       ↕                           │               │   directly)      │
  Obsidian Sync                    ├──▶ CF Pages   └──────────────────┘
       ↕                           └──▶ Student
┌───────────────────┐
│     iPHONE        │
│  (Obsidian Mobile │
│   + Sync)         │
└───────────────────┘
```

**Before CLI:** Agents on your Mac (or scripts) had to edit vault files directly — the "back door." This bypassed Obsidian's link resolver, property indexer, and cache. Moving files with `mv` broke wikilinks. Editing frontmatter with `sed` left the index stale.

**After CLI:** Any process on your Mac can use `obsidian create`, `obsidian move`, `obsidian property:set` — and Obsidian handles link updates, index refreshes, and conflict resolution internally.

**What this means for your setup:**

| Layer | How It Works Now | CLI Changes |
|-------|-----------------|-------------|
| **You on Mac** | Edit in Obsidian GUI, commit via Git | Can also create/move/search from terminal — useful for batch operations |
| **Mac-side agents** | Would edit files directly | **Should use CLI instead** — safe link updates, instant indexing |
| **VPS agents (Legacy AI)** | Write files directly, `codex-watch` auto-commits | **No change** — VPS runs headless, CLI requires GUI Obsidian running (Mac only for now) |
| **iPhone** | Capture via Obsidian Mobile + Sync | No change — mobile stays capture-only |

### Why This Matters for CODEX

**1. Safe Organize step from terminal.** Move notes between domains without breaking links:
```bash
# Move a processed inbox item to the right domain — links update automatically
obsidian move file="06 Inbox (Queue)/startup-idea" to="75-99 GE (Galactic Empire)/84 Ventures/"
```

**2. Agent-safe property management.** Set entity types, statuses, operators without touching YAML by hand:
```bash
obsidian property:set file="84 Ventures/new-venture" name="type" value="project"
obsidian property:set file="84 Ventures/new-venture" name="operator" value="human"
obsidian property:set file="84 Ventures/new-venture" name="realm" value="digital"
obsidian property:set file="84 Ventures/new-venture" name="status" value="active"
```

**3. Vault health in the × Multiply loop.** Add to your weekly review:
```bash
# Weekly vault health check
obsidian orphans          # Notes nobody links to — need connecting or archiving
obsidian unresolved       # Broken links — need fixing
obsidian tags counts      # Tag sprawl check — need consolidating?
```

**4. Scripted bulk operations.** Reclassify, retag, or restructure at scale:
```bash
# Reclassify all notes tagged #someday to status=backlog
obsidian tag tag="#someday" format=paths | while read -r f; do
  obsidian property:set file="$f" name="status" value="backlog"
done

# Find all orphan notes and move them to inbox for review
obsidian orphans format=paths | while read -r f; do
  obsidian move file="$f" to="06 Inbox (Queue)/"
done
```

**5. AI agent skill.** The CLI can serve as an AOP (Agent Operations Procedure) tool — give agents a structured, safe interface to the vault rather than raw file access. An agent that uses `obsidian create` and `obsidian property:set` will never break a wikilink or leave stale metadata.

### VPS Consideration

The CLI currently requires a running Obsidian GUI instance — it's a "remote control," not headless. This means:

- **Mac**: ✅ Full CLI access (Obsidian Desktop runs here)
- **VPS**: ❌ CLI not available (headless server, no GUI) — agents continue writing files directly via filesystem, and `codex-watch` handles Git sync
- **iPhone**: ❌ No terminal access — use Obsidian Mobile + Sync for captures

If Obsidian ever ships a headless CLI mode, VPS agents could migrate from direct file writes to CLI operations — eliminating the last "back door" in the pipeline. For now, the VPS `codex-watch` auto-commit flow remains the correct approach for server-side agents.

---

**Start with 3 + 1. Grow to 100. Never feel overwhelmed.**

The 100-domain system is the architecture — the full map of your life. But you don't start with the full map. You start with 3 life domains and 1 operating layer, then activate domains as your life demands them.

### The Structure: 3 Domains + 1 Operating Layer

One Mind OS is NOT four equal boxes. It's **three life domains running on one operating layer**:

```
┌──────────────────────────────────────────────────────────────────┐
│              SO — Sovereign Operations (00–24)                    │
│              The operating layer that runs everything             │
├─────────────────────┬─────────────────────┬──────────────────────┤
│  HP (25–49)         │  LE (50–74)         │  GE (75–99)          │
│  Your Self          │  Your Foundation     │  Your Endeavor        │
│  (health, mind, $)  │  (relationships,     │  (career, ventures,  │
│                     │   community, home)   │   brand, impact)     │
└─────────────────────┴─────────────────────┴──────────────────────┘
```

**SO is the platform. HP, LE, GE are the applications.** Just like macOS isn't "another app" — it's the operating system that runs all the apps — SO isn't another life domain. It's the layer that runs your life domains.

- SO holds your agents, tools, protocols, automations, and the framework itself
- HP, LE, GE hold your actual life — your self, your foundation, your endeavor
- Every capture flows THROUGH SO's inbox before routing to a domain
- Every agent LIVES in SO and SERVES HP, LE, and GE

### Day 1 — Just Drop Things In

```
"Is this about me? → HP. My relationships or home? → LE. My career or income? → GE. My system? → SO."
```

On your first day, you don't think about domains at all. You see 3 life folders and 1 system folder. Captured something about your health? Drop it in HP. Career move? GE. Server configuration? SO. Community event? LE.

This is **simpler than PARA** — PARA asks you to decide between Projects, Areas, Resources, and Archives (confusing boundaries). Life domains are obvious.

### Week 1 — Activate Your Starter Domains (8–12)

After a few days of capturing, patterns emerge. Activate only the domains you're actually using:

```
STARTER KIT (suggested — customize to your life):

SO:  00 Framework, 02 Agents, 06 Inbox       ← the operating layer
HP:  25 Identity, 27 Body, 29 Life Systems, 30 Finance
LE:  50 Home, 52 Children
GE:  75 Brand, 81 Strategy

That's 10-12 domains. Most people start here.
```

### Month 1+ — Domains Unlock As Life Expands

As your system grows, you activate new domains:
- Started investing? Activate `LE/56 Wealth`
- Learning a new skill? Activate `HP/28 Mastery`
- New business venture? Activate `GE/84 Ventures`

### The Scale

| Stage | Structure | Who |
|-------|-----------|-----|
| **Beginner** | 3 domains + SO (no sub-domains) | Day 1 users |
| **Starter** | 8–12 domains activated | Week 1 users |
| **Established** | 15–30 domains | Regular users |
| **Power** | 30–50 domains | Serious builders |
| **Dynasty** | 50–100 domains | Multi-generational estates |

**Most people will use 15–30 domains.** The 100-slot system means you'll never outgrow it — but you don't need to fill it.

### PARA vs. One Mind Onboarding

| | PARA | One Mind |
|---|---|---|
| **Day 1** | 4 folders. Use all 4. | 3 life domains + 1 operating layer. |
| **Month 1** | Still 4 folders. | Activate 10-12 domains. |
| **Year 1** | Still 4 folders. You've outgrown them. | 20-40 domains. Still growing. |
| **The ceiling** | 4 folders forever. | 100 domains. You never outgrow it. |

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

## Build Your CODEX

The framework is the skeleton. Your content is the muscle.

1. **Capture** — get things into the system
2. **Organize** — route to the right domain, tag with the right entity type
3. **Direct** — command: decide what matters, who does it, what done looks like
4. **Execute** — operators (human + AI) do the work
5. **× Multiply** — review, measure, extract lessons, feed back into Capture

The loop compounds. Every cycle makes the system smarter, the agent context richer, your SOPs sharper, and your decisions better-informed. That's the multiplication effect.

That's the CODEX.

---

## Supercharging the Codex — Plugin Stack

The private codex runs on a near-stock Obsidian installation. These plugins transform it from a file system into a queryable, automated life operating system — mapped directly to the CODEX method.

### Tier 1 — Install Now (Transforms the Vault)

#### Dataview — The Database Layer

**CODEX step:** All steps, especially × Multiply

Dataview turns your 100 domains into a **queryable database**. Every note with frontmatter becomes a row you can filter, sort, and display. This is the single biggest upgrade to the codex.

**What it unlocks:**
- Query all 17 entity types by `type`, `status`, `operator`, `realm`
- Build live dashboards that update automatically
- Surface orphan notes, stale goals, overdue tasks across all domains
- Power the × Multiply loop with data instead of guesswork

**Install:** Settings → Community Plugins → Browse → search "Dataview" → Install → Enable

#### Templater — Dynamic Templates

**CODEX step:** Capture

You already have 19 templates. Templater makes them **dynamic** — auto-fill dates, auto-set frontmatter based on the folder you're in, run JavaScript for custom logic.

**What it unlocks:**
- `{{date}}` and `{{time}}` auto-fill in templates
- `tp.file.title` auto-inserts the file name into frontmatter
- Folder-based template triggers — create a file in `01 Projects/` and the project template auto-applies
- JavaScript hooks for custom automation

**Install:** Settings → Community Plugins → Browse → search "Templater" → Install → Enable

#### QuickAdd — One-Key Capture

**CODEX step:** Capture

One hotkey = new entity with the right template and frontmatter. Eliminates all friction from the Capture step.

**Recommended hotkeys:**
- `Cmd+Shift+G` → New Goal (auto-fills `type: goal`, `status: draft`, `operator: human`)
- `Cmd+Shift+T` → New Task (auto-fills `type: task`, places in inbox)
- `Cmd+Shift+N` → Quick Note (timestamp + inbox placement)
- `Cmd+Shift+A` → New AOP (agent operations procedure template)

**Install:** Settings → Community Plugins → Browse → search "QuickAdd" → Install → Enable

#### Tasks + Todoist Sync — Hybrid Task Management

**CODEX step:** Capture + Execute

You already use Todoist — don't abandon it. Todoist has mobile push notifications, natural language input, and cross-platform reminders that Obsidian Tasks can't match. The right move is a **hybrid: Todoist for capture and reminders, Obsidian for dashboard and context.**

**The stack:**
- **Todoist** — quick mobile capture, reminders, due date notifications, recurring tasks
- **Todoist Sync plugin** — two-way sync that materializes Todoist tasks inside Obsidian notes. Changes in either app sync to the other.
- **Dataview** — query synced Todoist tasks alongside native vault data in your Mission Control dashboard

**What this unlocks:**
- Capture a task on your phone via Todoist → it appears in Obsidian automatically
- Complete a task in Obsidian → Todoist marks it done
- Dataview queries can pull both Todoist tasks AND vault-native tasks into one view
- You keep Todoist's reminders and notifications (Obsidian has none)
- Tasks live in context — next to the goals, projects, and notes they relate to

**Install:** Settings → Community Plugins → Browse → search "Todoist Sync" → Install → Enable → enter your Todoist API token

> **Why not Obsidian Tasks alone?** Obsidian Tasks has no mobile notifications, no push reminders, and no natural language input. Since you already use Todoist and it handles the Execute step's "when" (due dates, reminders), keep it. Todoist Sync bridges it into the codex so Dataview can query everything in one place.

### Tier 2 — Install Week 2 (Powers the Loop)

#### Periodic Notes — Automated Review Cycles

**CODEX step:** × Multiply

Auto-creates weekly, monthly, and quarterly review notes from templates. This IS your CODEX loop — automated. Set it up once and every Sunday a fresh review template appears with the right structure.

**Configuration:**
- Weekly template → triggers every Sunday (the × Multiply weekly cycle)
- Monthly template → triggers on the 1st (monthly multiplication)
- Quarterly template → triggers on quarter boundaries (strategic review)

#### Calendar — Visual Timeline

**CODEX step:** × Multiply

Sidebar calendar widget. Click any date → see that day's daily note. Visual timeline of your entire codex history. Pairs with Periodic Notes for navigating your review cycles.

#### Kanban — Visual Project Boards

**CODEX step:** Direct

Markdown-backed Kanban boards (Trello-style). Drag cards between columns: backlog → active → done. See all active projects across domains in one visual board.

**Use cases:**
- Project status board per domain
- Goal tracking board (draft → active → achieved)
- Inbox triage board (unprocessed → organized → directed)

#### Smart Connections — AI Semantic Search

**CODEX step:** × Multiply

Local AI embeddings — finds related notes by **meaning**, not just keywords. "What in my codex connects to this idea?" All processing happens locally on your Mac. Zero cloud, fully private.

**What it unlocks:**
- Discover hidden connections between domains you never manually linked
- Surface related notes while you're writing — automatic context
- Semantic search: "find everything about revenue strategy" returns meaning-matched results
- Pairs with MCP (Model Context Protocol) to let your AI agents query the vault semantically

### Tier 3 — Install Month 2 (Automation Layer)

#### MetaFlow — Auto-Populate Frontmatter

**CODEX step:** Organize

Automatically sets frontmatter based on folder location. Drop a file in `01 Projects/` → auto-sets `type: project`. Drop in `03 Agents/` → auto-sets `type: agent`, `operator: agent`. Automates the Organize step classification.

#### Metadata Auto Classifier — AI-Powered Tagging

**CODEX step:** Organize

Uses AI to analyze note content and suggest entity type + tags. Drop a raw capture in the inbox → it suggests the right type, status, and tags based on what you wrote.

#### Omnisearch — Next-Gen Search

**CODEX step:** Capture / × Multiply

Advanced search that includes OCR on images and PDFs. Find anything in the vault instantly, even content inside screenshots or scanned documents.

#### Obsidian Git — Auto-Commit from Mac

**CODEX step:** All steps (infrastructure)

Eliminates the manual `git add → commit → push` friction on your Mac. Auto-commits your changes on a schedule and auto-pulls VPS agent changes — keeping your Mac always in sync with GitHub.

**Why this is safe with your VPS pipeline:**
- VPS `codex-watch` auto-commits agent changes (~3s) and pushes to GitHub
- Obsidian Git on Mac auto-pulls (every 5 min) → you always see agent changes
- Obsidian Git on Mac auto-commits your edits (every 10 min) and pushes → VPS gets them within 1 min
- Smaller, more frequent commits = smaller diffs = easier to merge if conflicts ever arise
- The conflict risk is the SAME whether you commit manually or automatically — auto just makes the window smaller

**Recommended settings:**
- Auto-pull interval: **5 minutes**
- Auto-commit interval: **10 minutes**
- Auto-push after commit: **enabled**
- Pull on startup: **enabled**
- Commit message format: `vault backup: {{date}}`

**What this changes for iPhone captures:**
```
Before: iPhone → Sync → Mac → YOU manually git commit → GitHub → VPS (hours later)
After:  iPhone → Sync → Mac → Obsidian Git auto-commits (≤10 min) → GitHub → VPS (~1 min)
```

Your iPhone captures reach the VPS in ~11 minutes instead of waiting until you sit down and remember to commit.

**Mobile note:** Obsidian Git's mobile support is unstable (uses IsomorphicGit, not native Git). Don't enable it on iPhone — you have Obsidian Sync for that. Obsidian Git runs on Mac only.

**Install:** Settings → Community Plugins → Browse → search "Git" → Install → Enable

### Install Priority

```
Week 1:  Dataview + Templater + QuickAdd + Todoist Sync + Obsidian Git
Week 2:  Periodic Notes + Calendar + Kanban
Week 3:  Smart Connections
Month 2: MetaFlow + Metadata Auto Classifier
```

---

## Mission Control Dashboard

Once Dataview is installed, create this note as your command center. Every query updates live — open this note and you see the real-time state of your entire codex.

### The Dashboard (Create as `_codex/mission-control.md`)

```markdown
---
title: "Mission Control"
type: reference
status: active
tags: [type/reference, status/active, dashboard]
---

# 🎛️ Mission Control

## 🎯 Active Goals

\```dataview
TABLE status, operator, realm
FROM ""
WHERE type = "goal" AND status = "active"
SORT file.mtime DESC
\```

## 📋 Tasks Due This Week

\```dataview
TASK FROM ""
WHERE due <= date(today) + dur(7 days) AND !completed
SORT due ASC
\```

> **Note:** With Todoist Sync installed, your Todoist tasks also appear in the vault and can be queried by Dataview alongside native vault tasks.

## 📥 Inbox (Unprocessed)

\```dataview
TABLE file.ctime as "Captured"
FROM "06 Inbox (Queue)"
SORT file.ctime DESC
\```

## 🤖 Agent Activity (Last 7 Days)

\```dataview
TABLE operator, type, file.mtime as "Last Modified"
FROM ""
WHERE operator = "agent" AND file.mtime >= date(today) - dur(7 days)
SORT file.mtime DESC
LIMIT 20
\```

## 🔄 Active Projects

\```dataview
TABLE status, operator, realm
FROM ""
WHERE type = "project" AND status = "active"
SORT file.mtime DESC
\```

## ⚠️ Blocked Items

\```dataview
TABLE type, status
FROM ""
WHERE status = "blocked"
SORT file.mtime DESC
\```

## 🔗 Orphan Notes (Need Connecting)

\```dataview
LIST
FROM ""
WHERE length(file.inlinks) = 0 AND length(file.outlinks) = 0
LIMIT 15
\```

## 📊 Entity Counts

\```dataview
TABLE length(rows) as "Count"
FROM ""
WHERE type
GROUP BY type
SORT length(rows) DESC
\```
```

### Weekly Review Template (For Periodic Notes)

```markdown
---
title: "Weekly Review — {{date:YYYY-[W]ww}}"
type: review
status: active
tags: [type/review, cadence/weekly]
---

# × Multiply — Week {{date:ww}}, {{date:YYYY}}

## What moved forward this week?

\```dataview
TASK FROM ""
WHERE completed AND completion >= date(today) - dur(7 days)
\```

## What's stuck?

\```dataview
TABLE status, type
FROM ""
WHERE status = "blocked"
SORT file.mtime DESC
\```

## Inbox Health
- [ ] Process all items in 06 Inbox (Queue)
- [ ] Run `obsidian orphans` — connect or archive lonely notes
- [ ] Run `obsidian unresolved` — fix broken links
- [ ] Check `obsidian tags counts` — consolidate tag sprawl

## Key Decisions Made

-

## Lessons Learned (Feed Back to Capture)

-

## Next Week's Focus

-
```

---

*Part of the One Mind framework. See [ONEMIND-CODEX.md](ONEMIND-CODEX.md) for the master document.*
