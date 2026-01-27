# SIMULATION: SIM_001_BLAKE_CASE
## Master State Tracking

---

> **Simulation ID:** SIM_001
> **Case Reference:** CASE-2025-07-BLK
> **Created:** 2025-01-27
> **Last Updated:** 2025-01-27

---

## Current Timeline Position

| Perspective | Date | Notes |
|-------------|------|-------|
| **Investigation Date** | 2025-08-15 | When the investigator is working |
| **Days Since Crisis** | 40 | Since July 6 collapse |
| **Session Count** | 0 | Playthrough sessions |

---

## Arc Status Overview

| Arc | Status | Last Event | Day | Pending Actions |
|-----|--------|------------|-----|-----------------|
| [[_ARC_STATE_SCIARA\|SCIARA_RECOVERY]] | 🟡 Active | Crisis transfer | 0 | Initial recovery docs |
| [[_ARC_STATE_SEVRON\|SEVRON_MACHINATIONS]] | 🟡 Active | Transfer denial | 0 | Counter-response |
| [[_ARC_STATE_LEGAL\|LEGAL_PROCEEDINGS]] | 🟡 Active | Case opened | 0 | Initial filings |
| [[_ARC_STATE_KESSLER\|KESSLER_EXTRACTION]] | 🔵 Pending | Emergency extraction | 0 | Debrief documents |
| [[_ARC_STATE_MIRA\|MIRA_AWAKENING]] | ⚪ Dormant | Witnessed collapse | 0 | Trigger event needed |

**Status Key:**
- 🔴 Critical - Immediate attention required
- 🟡 Active - In progress, updates expected
- 🔵 Pending - Awaiting trigger/development
- ⚪ Dormant - Not yet activated
- ✅ Resolved - Arc concluded

---

## Cross-Arc Dependencies

```
DEPENDENCIES GRAPH:

LEGAL_PROCEEDINGS
    ├── awaits → SCIARA witness capacity (medical assessment)
    ├── awaits → KESSLER formal statement
    └── blocked_by → ICR jurisdictional challenge

SEVRON_MACHINATIONS
    ├── reacts_to → LEGAL subpoenas
    ├── reacts_to → KESSLER movements
    └── may_target → MIRA (if Kessler compromised)

KESSLER_EXTRACTION
    ├── depends_on → Family safety status
    └── feeds → LEGAL evidence chain

MIRA_AWAKENING
    ├── triggered_by → Sciara's absence noticed
    └── endangered_by → SEVRON awareness

SCIARA_RECOVERY
    ├── independent (medical timeline)
    └── milestone_unlocks → LEGAL witness testimony
```

---

## World State Flags

### Characters

| Character | Location | Status | Available |
|-----------|----------|--------|-----------|
| Sciara Blake | FRMC Neuro-ICU | Recovering | Limited |
| Collin Blake | FRMC | Present | Yes |
| Ava Kessler | [Unknown] | Under scrutiny | Covert only |
| Talia Sevron | ICR Site-17 | Active | Non-cooperative |
| Aria Shahrazai | FRMC | Treating | Yes |
| Alexander Shahrazai | TPC/Mobile | Coordinating | Yes |
| Mira Fallon | ICR Site-17 | Collared | Inaccessible |

### Evidence State

| Item | Status | Location |
|------|--------|----------|
| Collar (physical) | Preserved | FRMC secure storage |
| Collar telemetry | Extracted | Investigation files |
| Pharmacy records | Subpoenaed | Pending |
| Kessler personal notes | Exists | Not yet obtained |
| Sevron communications | Subpoenaed | ICR blocking |

### Institutional Posture

| Institution | Stance | Recent Action |
|-------------|--------|---------------|
| ICR | Obstructing | Filed jurisdiction challenge |
| FRMC | Cooperative | Providing records |
| Prometheus | Deflecting | "Refer to ICR" |
| Summit Council | Investigating | Subpoenas issued |
| TPC | Supporting (covert) | Intel sharing |

---

## Burned Bridges (Permanent)

*Actions that cannot be undone in this simulation:*

| Action | Consequence | Date |
|--------|-------------|------|
| *None yet* | — | — |

---

## Session Log

| Session | Date | Focus | Major Events |
|---------|------|-------|--------------|
| 0 | 2025-01-27 | Setup | Simulation initialized |

---

## Pending Queue

*Items awaiting generation or QA review:*

| Item | Type | Arc | Priority | Status |
|------|------|-----|----------|--------|
| Initial arc documents | Setup | ALL | High | Pending |

---

## Notes for Next Session

- All arcs initialized but need starting documents
- Player has not yet accessed any arc folders
- Timeline begins ~40 days post-crisis

---

*Auto-updated by SHEPHERD system. Manual edits preserved.*
