---
title: "Home Network & Smart Home Setup"
type: note
status: active
created: 2026-02-10
owner: zeus
tags: [type/note, domain/le, topic/smart-home]
ai_summary: "Home Assistant setup with Haven agent integration — lights, climate, security, routines"
---

# Home Network & Smart Home Setup

## Overview

The home runs on Home Assistant, integrated with the Haven agent for AI-powered automation. The goal: the house should anticipate needs, not wait for commands.

## Current Devices

| Category | Devices | Protocol |
|----------|---------|----------|
| Lighting | Hue bulbs (all rooms) | Zigbee via Hue Bridge |
| Climate | Ecobee thermostat | Wi-Fi |
| Security | Ring doorbell, cameras | Wi-Fi |
| Voice | HomePod minis (3) | AirPlay |
| Sensors | Motion, door/window | Zigbee |

## Automations

- **Morning routine** — Lights warm up gradually at 6am, coffee maker on, briefing read aloud
- **Away mode** — Lights simulate occupancy, cameras active, thermostat eco mode
- **Bedtime** — All lights off except hallway night light, doors locked confirmation
- **Guest mode** — Override automations, keep lights manual, disable sleep routines

## How Haven Agent Uses This

The Haven agent (domain 50-58) can control Home Assistant via API. It reads this note for device context and automation rules. When someone says "I'm cold," Haven knows to adjust the Ecobee, not just say "try a blanket."

## Network

- Router: Ubiquiti Dream Machine Pro
- Mesh: 3 UniFi access points
- Separate IoT VLAN for smart devices (isolated from main network)
