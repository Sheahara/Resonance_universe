# SHEPHERD SIMULATION SYSTEM
## Multi-Arc Investigation Framework

---

## What Is This?

This system allows you to run **parallel narrative threads** that can be explored independently while maintaining continuity across the whole simulation. Instead of one long conversation, each arc lives in its own folder with its own documents and state tracking.

---

## Quick Start

### 1. Open Your Simulation Folder
```
SIMULATIONS/SIM_001_BLAKE_CASE/
```

### 2. Check Your INBOX
```
SIMULATIONS/SIM_001_BLAKE_CASE/INBOX/
```
New documents appear here. Start by reading `_WELCOME.md`.

### 3. Explore Arcs
Each arc is a parallel story thread:
```
ARCS/
├── SCIARA_RECOVERY/     ← Her healing journey
├── SEVRON_MACHINATIONS/ ← Antagonist's response
├── LEGAL_PROCEEDINGS/   ← Summit Council case
├── KESSLER_EXTRACTION/  ← Whistleblower protection
└── MIRA_AWAKENING/      ← Potential new witness
```

### 4. Check State Files
Each arc has an `_ARC_STATE.md` showing:
- Current status
- Timeline position
- Active threads
- Pending developments

---

## Folder Structure

```
SIMULATIONS/
├── _SYSTEM/                     ← System prompts and protocols
│   ├── DISPATCH_PROTOCOL.md     ← How requests are routed
│   └── ASK_USER_TOOL.md         ← Clarification and confirmation protocol
│
└── SIM_001_BLAKE_CASE/          ← Your active simulation
    ├── _STATE/                  ← Tracking files
    │   ├── MASTER_STATE.md      ← Overall status
    │   └── SESSION_LOG.md       ← What happened each session
    │
    ├── ARCS/                    ← Parallel narrative threads
    │   ├── SCIARA_RECOVERY/
    │   │   ├── _ARC_STATE.md    ← Arc-specific tracking
    │   │   ├── EVIDENCE/        ← Documents for this arc
    │   │   └── SCENES/          ← Narrative moments
    │   ├── SEVRON_MACHINATIONS/
    │   ├── LEGAL_PROCEEDINGS/
    │   ├── KESSLER_EXTRACTION/
    │   └── MIRA_AWAKENING/
    │
    ├── SHARED/                  ← Cross-arc resources
    │   ├── Evidence/
    │   ├── Personnel/
    │   └── Technical/
    │
    └── INBOX/                   ← Your document queue
```

---

## How Arcs Work

### Independent Timelines
Each arc tracks its own progress. Sciara's recovery continues whether or not you're watching. Sevron's machinations proceed in the background. You choose what to focus on.

### Cross-Arc Dependencies
Some arcs affect each other:
- LEGAL needs SCIARA's witness capacity
- SEVRON reacts to KESSLER's movements
- MIRA may be triggered by SCIARA's absence

These dependencies are tracked in `MASTER_STATE.md`.

### Arc Statuses
| Status | Meaning |
|--------|---------|
| 🔴 Critical | Needs immediate attention |
| 🟡 Active | In progress, updates expected |
| 🔵 Pending | Awaiting trigger |
| ⚪ Dormant | Not yet activated |
| ✅ Resolved | Arc concluded |

---

## Interacting With the System

### Request Types

**Advance an arc:**
> "What happens next in Sciara's recovery?"

**Generate specific content:**
> "Create observation logs for Day 3-5"

**Check status:**
> "What's the current state of the legal proceedings?"

**React to events:**
> "Sevron finds out about Kessler's TPC connection - show her response"

**Cross-arc events:**
> "Show how the subpoena affects both Sevron's arc and the legal arc"

### What Happens Behind the Scenes

1. **Intake** - Your request is parsed
2. **Ask User** - If your request is ambiguous or risky, SHEPHERD asks a clarifying question before proceeding
3. **State Check** - Current arc states are read
4. **Research** - Optional web search for authentic details
5. **Planning** - Documents to generate are identified
6. **Confirm Action** - If consequences are irreversible, SHEPHERD asks for explicit confirmation
7. **Generation** - Content is created in SHEPHERD format
8. **QA** - Timeline and continuity verified
9. **Delivery** - Documents placed in arc folders + INBOX

---

## State Tracking

### MASTER_STATE.md
The hub. Shows:
- Overall timeline position
- All arc statuses at a glance
- Cross-arc dependencies
- Character locations
- Evidence inventory
- Burned bridges (permanent consequences)

### _ARC_STATE.md (per arc)
Arc-specific details:
- Current timeline position for this arc
- Active threads within the arc
- Key NPCs for this arc
- Documents generated
- Pending actions

### SESSION_LOG.md
History of what happened:
- Events per session
- Documents generated
- State changes
- Player actions

---

## Creating New Simulations

To start a fresh playthrough:

1. Copy `SIM_001_BLAKE_CASE` to `SIM_002_[NAME]`
2. Reset all state files to Day 0
3. Clear INBOX except `_WELCOME.md`
4. Clear arc EVIDENCE and SCENES folders

Each simulation is independent. You can run multiple in parallel.

---

## Tips

### For Focused Play
- Pick one arc to follow closely
- Let others develop in background
- Check INBOX for cross-arc impacts

### For Comprehensive Play
- Rotate between arcs
- Check MASTER_STATE regularly
- Follow dependency chains

### For Maximum Immersion
- Only read documents in INBOX order
- Don't peek at arc states
- Let developments surprise you

---

## The Philosophy

This system exists because:

1. **Long conversations lose context** - Files persist, conversations fade
2. **Parallel stories need parallel tracking** - Each arc has its own state
3. **You should explore, not scroll** - Click into what interests you
4. **Continuity matters** - State files prevent contradictions
5. **Modifications are easy** - It's all markdown files

---

## Reference Materials

The `VAULT/` folder (sibling to SIMULATIONS) contains:
- SCP-style evidence templates
- Character dossiers
- Timeline reference
- Technical documentation

The root folder contains:
- `SHEPHERD_MASTER_PROMPT.md` - Core system identity
- `SHEPHERD_SCENARIO_TEMPLATES.md` - Entry points and structures
- `RESONANCE UNIVERSE.txt` - Pharmacology and lore reference

---

*Welcome to the investigation. The documents are waiting.*
