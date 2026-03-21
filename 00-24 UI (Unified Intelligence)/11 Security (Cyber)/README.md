---
id: ui-11-readme
title: "11 Security — Cyber & Access Control"
type: index
status: active
created: 2026-01-13
owner: zeus
tags: [domain/ui, type/index, domain/security]
ai_summary: "Cybersecurity practices, access control, credentials management, and threat monitoring"
---

# 11 Security — Cyber & Access Control

> *Security is not a feature. It's the foundation.*

## Purpose

This domain manages all security-related knowledge — access control policies, credential management practices, threat monitoring, incident response, and security decisions.

---

## What Lives Here

```text
11 Security (Cyber)/
├── Access/              # Who has access to what
├── Credentials/         # Credential management (no actual creds here)
├── Incidents/           # Security incident logs
├── Policies/            # Security rules and decisions
└── Monitoring/          # Alert configs and monitoring setup
```

## Core Principles

1. **Secrets never in code** — 1Password for all credentials, `op://` references only
2. **Least privilege** — agents get minimum tools needed for their scope
3. **Audit trails** — all sensitive ops logged
4. **Defense in depth** — Tailscale + systemd sandboxing + firewall

## Tools

- **1Password** — credential vault (vault: `00-24 UI`)
- **Tailscale** — zero-trust network access
- **UFW** — VPS firewall
- **Fail2ban** — brute-force protection
