---
id: ui-10-readme
title: "10 Development — Code & Testing"
type: index
status: active
created: 2026-01-13
owner: zeus
tags: [domain/ui, type/index, domain/development]
ai_summary: "Code projects, development notes, testing strategies, and technical decisions"
---

# 10 Development — Code & Testing

> *Build things that last. Document decisions, not just code.*

## Purpose

This domain captures all software development work — project notes, architecture decisions, testing strategies, debugging logs, and technical references. Not where the code lives (GitHub), but where the thinking lives.

---

## What Lives Here

```text
10 Development (Code & Testing)/
├── Projects/            # Per-project notes and decisions
├── Patterns/            # Reusable patterns and architectures
├── Testing/             # Testing strategies and results
├── Debugging/           # Debug logs and resolved issues
└── References/          # Tech references and API notes
```

## Active Projects

| Project | Stack | Status | Repo |
|---------|-------|--------|------|
| OneMind UI | Next.js, TypeScript | Active | onemind-ui |
| OneMind Office | Vite, R3F, Zustand | Active | onemind-office |
| OpenClaw Skills | Node.js | Active | onemind-os |
| Chowder iOS | Swift, Xcode | Active | onemind-ios |

## Standards

- TypeScript strict mode — no `any`
- Conventional Commits: `feat:`, `fix:`, `chore:`, `docs:`
- Tests before merge for logic-critical code
- Architecture decisions recorded as ADRs in `Projects/{name}/`
