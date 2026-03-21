---
title: "Financial Independence Tracker"
type: note
status: active
created: 2026-02-01
owner: zeus
tags: [type/note, domain/hp, topic/finance]
ai_summary: "Financial independence targets — income streams, savings rate, investment allocation, runway metrics"
---

# Financial Independence Tracker

## The Number

Financial independence = annual expenses × 25 (4% rule). Track progress toward this quarterly.

## Income Streams

| Stream | Type | Status |
|--------|------|--------|
| Day job / consulting | Active | Running |
| SaaS / digital products | Active | Building |
| Content / education | Active | Planning |
| Real estate | Passive | Research phase |
| Investments | Passive | Dollar-cost averaging |

## Monthly Tracking Template

```
[Month]:
  Income: $____
  Expenses: $____
  Savings rate: ____%
  Net worth delta: $____
  Runway (months): ____
```

## Rules

- Pay yourself first — automate savings before spending
- Track net worth monthly, not daily (prevents anxiety)
- Oracle agent monitors and flags anomalies

## How the Oracle Agent Uses This

The Oracle agent (domain 30) reads this note for financial context. During heartbeat, it can pull data from connected accounts and flag if savings rate drops below target.
