---
title: Letta Context Repository Integration
type: example
domain: agent
tags: [letta, context-repository, memory, integration]
ai_summary: Shows how a Letta agent uses a codex as its Context Repository — mapping core memory, archival memory, and tools to codex structure.
---

# Letta Context Repository Integration

How a [Letta](https://github.com/letta-ai/letta) agent uses a codex vault as its Context Repository, with memory tiers mapped to the codex structure.

## Overview

Letta agents have a tiered memory architecture: **core memory** (always in context), **recall memory** (conversation history), and **archival memory** (long-term searchable storage). A codex vault maps cleanly to this model.

## Memory Tier Mapping

### Core Memory → `_codex/system/`

Letta's core memory is always loaded into the agent's context window. The codex equivalent is `_codex/system/`:

| Letta Core Block | Codex File |
|-----------------|------------|
| `persona` | `_codex/system/IDENTITY.md` |
| `human` | `_codex/system/OWNER.md` (the human's preferences) |
| `instructions` | `_codex/CONVENTIONS.md` |
| `system` | `_codex/INTERFACE.md` |

These files are small, high-signal, and always relevant — exactly what core memory should be.

### Tool Definitions → `_codex/skills/`

Letta's tools map to codex skills:

| Letta Tool | Codex Skill |
|-----------|-------------|
| `archival_memory_insert` | `_codex/skills/capture.md` |
| `archival_memory_search` | `_codex/skills/search.md` |
| Custom: `organize_note` | `_codex/skills/organize.md` |
| Custom: `weekly_review` | `_codex/skills/reflect.md` |

### Archival Memory → Domain Folders

Letta's archival memory is searchable but not always loaded. Domain folders serve this role:

```
00-24 UI/   →  archival passages about tech, infrastructure, AI
25-49 HP/   →  archival passages about health, skills, personal growth
50-74 LE/   →  archival passages about family, home, legacy
75-99 GE/   →  archival passages about business, ventures, wealth
```

Each markdown file in these folders becomes searchable archival content. The `ai_summary` frontmatter field serves as a compressed passage for search result ranking.

## Progressive Disclosure

Codex structure supports progressive disclosure — loading more context only when needed:

### L0 — Core Memory (Always Loaded)

```
_codex/system/IDENTITY.md     →  Who the agent is
_codex/system/OWNER.md        →  Who the human is
_codex/CONVENTIONS.md          →  How to behave
```

**Token cost**: ~500-1000 tokens. Always in context.

### L1 — Summary Scan (Search Results)

When the agent searches archival memory, it first gets `ai_summary` fields:

```yaml
# Search: "quarterly revenue targets"
# Returns:
- title: Q2 Planning Notes
  ai_summary: Revenue targets set at $50K MRR. Hiring 2 engineers in April.
  path: 75-99 GE/business/q2-planning.md
```

**Token cost**: ~50-100 tokens per result. Cheap to scan multiple results.

### L2 — Full File (On Demand)

If the summary is relevant, the agent loads the full file:

```
archival_memory_search("quarterly revenue") → summaries
  → relevant hit: q2-planning.md
    → load full file (500-2000 tokens)
```

### L3 — Linked Files (Follow References)

The full file may contain wiki-links to related notes:

```markdown
See also: [[hiring-plan]], [[budget-2026]], [[product-roadmap]]
```

The agent can follow these links to load additional context as needed.

## Implementation

### Setting Up Letta with a Codex

```python
from letta import create_client

client = create_client()

# Create agent with codex-backed core memory
agent = client.create_agent(
    name="codex-agent",
    memory=client.create_block_memory(
        persona=open("_codex/system/IDENTITY.md").read(),
        human=open("_codex/system/OWNER.md").read(),
    ),
    system=open("_codex/INTERFACE.md").read(),
)
```

### Indexing Domain Folders as Archival

```python
import os

# Walk codex domain folders and insert as archival memory
for domain_dir in ["00-24 UI", "25-49 HP", "50-74 LE", "75-99 GE"]:
    for root, dirs, files in os.walk(domain_dir):
        for file in files:
            if file.endswith(".md"):
                path = os.path.join(root, file)
                content = open(path).read()
                client.insert_archival_memory(
                    agent_id=agent.id,
                    memory=content,
                    metadata={"source_path": path},
                )
```

### Custom Tool: Capture to Codex

```python
def capture_to_codex(self, text: str, domain: str, tags: list[str]) -> str:
    """Capture a new note to the codex inbox for later routing."""
    import datetime
    date = datetime.date.today().isoformat()
    filename = f"06 Inbox/{date}-capture.md"

    frontmatter = f"""---
title: Agent Capture — {date}
type: capture
domain: {domain}
tags: {tags}
created: {date}
ai_summary: {text[:200]}
---
"""
    with open(filename, "w") as f:
        f.write(frontmatter + "\n" + text)

    return f"Captured to {filename}"
```

## Key Differences from Raw Letta

| Standard Letta | Codex-Backed Letta |
|---------------|-------------------|
| Core memory is free-form text blocks | Core memory is structured markdown with frontmatter |
| Archival memory is flat passages | Archival memory is organized into domain folders |
| No file structure | Files on disk, version-controlled, editable by humans |
| Search returns raw text | Search returns with `ai_summary` for fast scanning |
| Single agent's memory | Shared across agents and human (via git) |

## When To Use This Pattern

- You want your Letta agent to share knowledge with other agents or humans
- You want version-controlled, auditable agent memory
- You need progressive disclosure (not everything loaded at once)
- You're building a personal knowledge system that an agent helps maintain
