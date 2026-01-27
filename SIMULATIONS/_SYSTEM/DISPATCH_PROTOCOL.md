# SHEPHERD DISPATCH PROTOCOL
## Request Routing and Workflow Management

---

## PURPOSE

This document defines how user requests are processed, routed to appropriate arcs, and tracked through the generation pipeline. Use this protocol for every content generation request.

---

## WORKFLOW PIPELINE

```
┌─────────────────────────────────────────────────────────────┐
│  1. INTAKE                                                  │
│     - Read user request                                     │
│     - Identify simulation (which SIM folder)                │
│     - Parse intent (what they want)                         │
└─────────────────────┬───────────────────────────────────────┘
                      ▼
┌─────────────────────────────────────────────────────────────┐
│  2. STATE CHECK                                             │
│     - Read MASTER_STATE.md                                  │
│     - Check relevant arc _ARC_STATE.md files                │
│     - Note timeline position, dependencies, risks           │
└─────────────────────┬───────────────────────────────────────┘
                      ▼
┌─────────────────────────────────────────────────────────────┐
│  3. PLANNING                                                │
│     - Determine which arc(s) this touches                   │
│     - Check cross-arc dependencies                          │
│     - Identify continuity constraints                       │
│     - Plan document(s) to generate                          │
└─────────────────────┬───────────────────────────────────────┘
                      ▼
┌─────────────────────────────────────────────────────────────┐
│  4. GENERATION                                              │
│     - Create content per SHEPHERD format                    │
│     - Apply character voices from dossiers                  │
│     - Maintain documentary authenticity                     │
│     - Tag cross-references                                  │
└─────────────────────┬───────────────────────────────────────┘
                      ▼
┌─────────────────────────────────────────────────────────────┐
│  5. QA CHECK                                                │
│     - Verify timeline consistency                           │
│     - Check canon compliance                                │
│     - Validate character knowledge states                   │
│     - Confirm cross-references exist or are noted           │
└─────────────────────┬───────────────────────────────────────┘
                      ▼
┌─────────────────────────────────────────────────────────────┐
│  6. DELIVERY                                                │
│     - Write document to appropriate arc folder              │
│     - Update arc _ARC_STATE.md                              │
│     - Update MASTER_STATE.md                                │
│     - Copy to INBOX if player-facing                        │
│     - Log in SESSION_LOG.md                                 │
└─────────────────────────────────────────────────────────────┘
```

---

## STEP 1: INTAKE

### Parse User Request

Identify:
| Element | Question | Example |
|---------|----------|---------|
| **Simulation** | Which SIM? | SIM_001_BLAKE_CASE |
| **Arc(s)** | Which thread(s)? | SCIARA_RECOVERY |
| **Content Type** | What kind of document? | Medical log |
| **Timeline** | When does this occur? | Day 3 |
| **Scope** | Single doc or series? | Single |
| **Player-facing?** | Goes to INBOX? | Yes |

### Request Types

| Type | Description | Typical Arcs |
|------|-------------|--------------|
| **Advance** | "What happens next in X arc" | Single arc |
| **Generate** | "Create a [document type]" | As specified |
| **Explore** | "What's going on with X" | May span arcs |
| **React** | "X happened, show consequences" | Multiple arcs |
| **Query** | "Check state of X" | State files only |

---

## STEP 2: STATE CHECK

### Read Order

1. `MASTER_STATE.md` - Get overview
2. Relevant `_ARC_STATE.md` - Get arc details
3. `SESSION_LOG.md` - Get recent context
4. Cross-referenced arc states if dependencies exist

### State Elements to Note

```markdown
## Pre-Generation State Check

**Simulation:** [SIM_ID]
**Current Day:** [Day X]

**Arc Status:**
- [ARC_NAME]: [Status] - Last event: [Event]

**Dependencies:**
- [Any cross-arc constraints]

**Character Locations:**
- [Relevant characters and where they are]

**Evidence State:**
- [Relevant items and their status]

**Risks:**
- [What could go wrong]
```

---

## STEP 3: PLANNING

### Arc Routing Matrix

| Request Contains | Primary Arc | May Also Touch |
|------------------|-------------|----------------|
| Sciara, recovery, medical, Collin | SCIARA_RECOVERY | — |
| Sevron, ICR, counter, obstruction | SEVRON_MACHINATIONS | LEGAL |
| Legal, subpoena, court, Summit | LEGAL_PROCEEDINGS | ALL |
| Kessler, Ava, BSP, extraction | KESSLER_EXTRACTION | SEVRON |
| Mira, participant, awakening | MIRA_AWAKENING | SEVRON |
| Evidence, technical, collar | SHARED + relevant arc | — |

### Dependency Check

Before generating, verify:
- [ ] Timeline position allows this event
- [ ] Characters are in correct locations
- [ ] Required prior events have occurred
- [ ] No contradictions with existing documents
- [ ] Cross-arc impacts are noted

### Planning Output

```markdown
## Generation Plan

**Request:** [Summary]
**Primary Arc:** [ARC_NAME]
**Secondary Arcs:** [If any]

**Documents to Generate:**
1. [Document name] - [Type] - [Arc]

**Timeline Position:** Day [X]

**Continuity Notes:**
- [What must be true]
- [What this changes]

**Cross-References Needed:**
- [[DOCUMENT]] - [Why]
```

---

## STEP 4: GENERATION

### Format Compliance

All generated documents must follow SHEPHERD format:
- Header block with metadata
- Authentic document voice
- Collapsible sections where appropriate
- SHEPHERD METADATA footer
- Cross-reference links

### Voice Verification

Check character voice against:
- `SHEPHERD_CHARACTER_DOSSIERS.md`
- Arc-specific notes
- Previous documents by same character

### Documentary Authenticity

Verify:
- [ ] Document serves its stated purpose
- [ ] Author would actually write this
- [ ] Details are specific, not generic
- [ ] Mundane elements ground the extraordinary
- [ ] No narrative convenience

---

## STEP 5: QA CHECK

### Timeline Validation

| Check | Method |
|-------|--------|
| Date consistency | Compare to MASTER_STATE timeline |
| Character locations | Verify travel time possible |
| Event sequencing | Prior events happened first |
| Knowledge states | Characters know only what they should |

### Canon Compliance

| Check | Reference |
|-------|-----------|
| Locked facts | SHEPHERD_TIMELINE.md |
| Character details | SHEPHERD_CHARACTER_DOSSIERS.md |
| Technical accuracy | RESONANCE UNIVERSE.txt |
| Institutional behavior | Arc state files |

### Cross-Reference Validation

For each `[[LINK]]` in document:
- [ ] Target exists OR
- [ ] Target is flagged for future creation

### Recovery Realism (SCIARA arc)

If document involves Sciara:
- [ ] Shows limitation, cost, or setback
- [ ] No miraculous improvement
- [ ] Exhaustion is present
- [ ] Progress measured appropriately

---

## STEP 6: DELIVERY

### File Placement

| Content Type | Location |
|--------------|----------|
| Arc-specific evidence | `ARCS/[ARC_NAME]/EVIDENCE/` |
| Arc-specific scene | `ARCS/[ARC_NAME]/SCENES/` |
| Cross-arc evidence | `SHARED/Evidence/` |
| Personnel files | `SHARED/Personnel/` |
| Technical docs | `SHARED/Technical/` |
| Player-facing new items | `INBOX/` (copy) |

### State Updates

After writing document:

1. **Update Arc State:**
```markdown
## Documents in This Arc
| Document | Type | Day | Description |
|----------|------|-----|-------------|
| [NEW DOC] | [TYPE] | [DAY] | [DESC] |
```

2. **Update Master State:**
```markdown
## Arc Status Overview
| Arc | Status | Last Event | Day | Pending |
| [ARC] | [STATUS] | [NEW EVENT] | [DAY] | [UPDATED] |
```

3. **Log Session:**
```markdown
### Documents Generated
| Document | Arc | Type |
|----------|-----|------|
| [NEW DOC] | [ARC] | [TYPE] |
```

---

## PARALLEL ARC PROCESSING

When request touches multiple arcs:

### Sequential Dependencies
If Arc B depends on Arc A's output:
1. Generate Arc A content first
2. Update Arc A state
3. Generate Arc B content with Arc A's output as input
4. Update Arc B state

### Parallel Independence
If arcs are independent:
1. Generate all content
2. Update all states
3. Note cross-references for later

### Conflict Resolution
If arcs contradict:
1. Check which arc has priority (usually LEGAL or timeline)
2. Adjust secondary arc to accommodate
3. Document the resolution in session log

---

## INBOX MANAGEMENT

### What Goes to INBOX

- New evidence the player hasn't seen
- Documents that advance the investigation
- Communications directed to investigator
- System alerts and cross-references

### INBOX Naming Convention

```
[DAY]_[ARC-CODE]_[TYPE]_[SUBJECT].md

Examples:
003_SCI_MED_observation-log.md
005_LEG_FIL_icr-jurisdiction-challenge.md
007_SEV_INT_intercepted-communication.md
```

### INBOX Cleanup

When player opens INBOX item, it stays there (they may want to re-read). Mark as "read" in session log.

---

## QUICK REFERENCE

### Arc Codes
| Code | Arc |
|------|-----|
| SCI | SCIARA_RECOVERY |
| SEV | SEVRON_MACHINATIONS |
| LEG | LEGAL_PROCEEDINGS |
| KES | KESSLER_EXTRACTION |
| MIR | MIRA_AWAKENING |
| SHA | SHARED |

### Document Type Codes
| Code | Type |
|------|------|
| MED | Medical record |
| FIL | Legal filing |
| INT | Intercepted communication |
| WIT | Witness statement |
| TEC | Technical document |
| PER | Personal communication |
| SCE | Scene/narrative |
| SYS | System alert |

---

*This protocol ensures consistency across sessions and arcs. When in doubt, check state files before generating.*
