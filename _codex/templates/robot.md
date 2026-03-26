---
id: "robot-{slug}"
title: "Robot: {Device Name}"
type: robot
status: active
created: "{YYYY-MM-DD}"
owner: "{your-name}"
realm: physical
tags: [type/robot, "domain/{domain}"]
related: []
ai_summary: "Robot: {name} — {what it does in ≤10 words}"
---

# Robot: {Device Name}

<!-- Robots are physical automation devices — smart home, CNC machines, IoT sensors,
     security systems, irrigation controllers, etc.
     Save in the domain where this device operates.
     e.g. irrigation system → LE/50 Home/, security camera → SO/11 Security/ -->

## Device Info

- **Type**: {smart home | sensor | manufacturing | security | agricultural | other}
- **Location**: {where is this device physically?}
- **Manufacturer/Model**: {brand and model}
- **Connection**: {WiFi, Bluetooth, Zigbee, wired, etc.}

## What It Does

{What role does this device play in your system?}

## AOPs Assigned

{Which Agent Operations Procedures involve this device?}

- [[aop-name]]

## Monitoring

- **Dashboard**: {where to check status}
- **Alerts**: {what triggers an alert}
- **Maintenance schedule**: {how often does it need attention}

## Notes

{Setup details, quirks, troubleshooting tips}

---
<!-- AI AGENT NOTE: Robot profiles track physical automation in the system.
     If a robot's status is flagged, alert the human owner.
     Robots cannot be controlled directly through the vault — they require their own interfaces. -->
