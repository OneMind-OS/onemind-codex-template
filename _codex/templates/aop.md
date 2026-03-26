---
id: "{domain-code}-{YYYYMMDD}-{slug}"
title: "AOP: {Procedure Name}"
type: aop
status: active
created: "{YYYY-MM-DD}"
owner: "{agent-name}"
agent: "{which agent runs this}"
tags: [type/aop, "domain/{domain}", "operator/{agent-name}"]
related: []
ai_summary: "AOP: {what this agent procedure does in ≤10 words}"
---

# AOP: {Procedure Name}

<!-- AOPs are procedures designed FOR agents, written in a format agents can execute directly.
     Unlike SOPs (which are human-readable and may be delegated to agents), AOPs are
     agent-native: structured inputs, deterministic steps, machine-parseable outputs.
     Save in the domain where this operation lives.
     e.g. inbox triage → SO/09 Automation/, market research → GE/81 Strategy/ -->

## Purpose

{What does this agent procedure accomplish?
What would require human effort without this AOP?}

## Trigger

- **When**: {What triggers this AOP? Schedule, event, human command, or another AOP}
- **Frequency**: {one-time | on-demand | daily | weekly | on-event}
- **Autonomy**: {L0: human runs it | L1: agent suggests, human approves | L2: agent runs, human reviews | L3: fully autonomous}

## Agent Assignment

- **Primary agent**: {agent name — e.g., Legacy, Spartan, Oracle}
- **Fallback agent**: {backup agent if primary unavailable}
- **Human escalation**: {when should the agent stop and ask a human?}

## Inputs

| Input | Source | Required |
|-------|--------|----------|
| {input 1} | {where the agent gets it — file path, API, user prompt} | yes/no |
| {input 2} | {source} | yes/no |

## Steps

1. **{Step 1}** — {clear instruction an agent can follow without interpretation}
   - Tool: {specific tool or API to use}
   - Expected output: {what this step produces}

2. **{Step 2}**
   - Tool: {tool}
   - Expected output: {output}

3. **{Step 3}**
   - Tool: {tool}
   - Expected output: {output}

## Outputs

| Output | Format | Destination |
|--------|--------|-------------|
| {output 1} | {markdown file, JSON, notification, etc.} | {where it goes — file path, inbox, dashboard} |
| {output 2} | {format} | {destination} |

## Success Criteria

- {How does the agent (or reviewer) know this completed correctly?}
- {What quality checks should be run on the output?}

## Error Handling

| Error Condition | Action |
|----------------|--------|
| {input missing or invalid} | {what to do — retry, skip, escalate to human} |
| {API/tool failure} | {fallback behavior} |
| {output doesn't meet quality criteria} | {retry with different approach or escalate} |

## Guardrails

- {What is the agent NOT allowed to do during this procedure?}
- {What files/domains are off-limits?}
- {Maximum resources (API calls, tokens, time) this AOP can consume}

## Last Verified

{YYYY-MM-DD} — {who confirmed this AOP still works correctly}

---
<!-- AI AGENT NOTE: AOPs are your execution contracts.
     Follow steps exactly as written. If a step is ambiguous, escalate to human.
     Log your execution in the output destination.
     Update 'Last Verified' after successful completion. -->
