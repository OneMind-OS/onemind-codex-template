---
id: ui-08-readme
title: "08 — Infrastructure (Grid & APIs)"
type: index
status: active
created: 2026-01-01
owner: zeus
tags: [domain/ui-08, type/index, status/active]
ai_summary: "Infrastructure domain — servers, APIs, NATS, databases, cloud services, and the technical grid"
---

# 08 — Infrastructure (Grid & APIs)

> *Infrastructure is the part of your system you only think about when it breaks.*

---

## What Lives Here

The technical foundation everything runs on — servers, cloud services, APIs, databases, message queues, and the configuration that keeps it all alive.

- **Service registry** — every running service, its URL, purpose, and health status
- **Architecture diagrams** — how the pieces connect
- **API catalog** — all external APIs in use with auth method and usage notes
- **Database inventory** — all databases, schemas, access patterns
- **Operations runbooks** — how to restart, maintain, and recover services
- **Cost tracking** — infrastructure spend by service

---

## Suggested Folder Structure

```text
08 Infrastructure (Grid & APIs)/
├── service-registry.md           ← All services: name, URL, purpose, owner, health endpoint
├── architecture.md               ← System architecture overview with diagrams or links
├── api-catalog.md                ← External APIs in use: purpose, auth, rate limits, docs URL
├── databases.md                  ← All databases: type, host, schema notes, access
├── runbooks/
│   ├── restart-services.md       ← How to restart each service safely
│   └── disaster-recovery.md      ← What to do when something major breaks
└── infra-costs.md                ← Monthly infrastructure spend by service
```

---

## Zeus's Note

The service registry is the file I open when anything breaks. When Legacy (my AI) needs to call an API, it checks the API catalog first. When infrastructure costs spike, `infra-costs.md` tells me what changed.

Runbooks were a forcing function for me. Writing "how to restart X" forced me to realize I didn't actually know how to restart X gracefully. Now I do — and so does anyone else on the team.

Architecture diagrams don't need to be fancy. A Markdown file with an ASCII block diagram and a few paragraphs of explanation is enough. The goal is that any reasonably technical person can understand the system in 10 minutes without asking you.
