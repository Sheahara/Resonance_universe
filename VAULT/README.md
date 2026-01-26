# SHEPHERD Vault
## Interactive Investigation Archive

---

## What Is This?

This is an **Obsidian-compatible vault** containing the SHEPHERD investigation database for Project Black Phoenix. Documents are cross-linked using `[[wikilinks]]` and feature collapsible sections for progressive disclosure.

---

## How to Use

### Option 1: Obsidian (Recommended)

1. Download [Obsidian](https://obsidian.md/) (free)
2. Open this `VAULT` folder as an Obsidian vault
3. Click `[[links]]` to navigate between documents
4. Use the graph view to see document relationships
5. Expand `<details>` sections by clicking them

### Option 2: GitHub

Documents render on GitHub with:
- Clickable links between files
- Collapsible sections (click the arrows)
- Markdown formatting

Note: `[[wikilinks]]` won't be clickable on GitHub, but filenames are visible.

### Option 3: Any Markdown Viewer

The documents are standard markdown with some HTML (`<details>` tags). Most markdown viewers will render them correctly.

---

## Vault Structure

```
VAULT/
├── SHEPHERD_INDEX.md      ← Start here (hub document)
├── Evidence/              ← Primary source documents
│   └── EVD-*.md
├── Personnel/             ← Character/subject files
│   └── PERSONNEL-*.md
├── Technical/             ← System documentation
│   └── TECH-*.md
├── Investigation/         ← Case files and threads
│   └── CASE-*.md
│   └── THREAD-*.md
└── Reference/             ← Background materials
    └── REF-*.md
```

---

## Document Conventions

### Link Types
- `[[DOCUMENT-NAME]]` - Link to another document
- `[[DOCUMENT-NAME|Display Text]]` - Link with custom text
- `[[DOCUMENT-NAME#Section]]` - Link to specific section

### Classification Markers
| Marker | Meaning |
|--------|---------|
| `[REDACTED]` | Information withheld |
| `[DATA EXPUNGED]` | Information destroyed |
| `[CLASSIFIED]` | Requires higher clearance |
| `████████` | Blacked-out text |

### Status Indicators
| Icon | Meaning |
|------|---------|
| 🔴 | Critical / Active |
| 🟡 | Developing |
| 🟠 | Preliminary |
| 🔵 | Monitoring |
| ⚠️ | Warning / Caution |

### Collapsible Sections

Click to expand:

<details>
<summary><b>Example Collapsible</b></summary>

Hidden content goes here. This is how classified addenda, detailed analysis, and supplementary materials are presented.

You can nest these:

<details>
<summary>Nested content</summary>

Even more hidden content.

</details>

</details>

---

## For Content Creators

### Adding New Documents

1. Use the appropriate folder (Evidence, Personnel, Technical, etc.)
2. Follow naming convention: `TYPE-IDENTIFIER.md`
3. Include front matter with classification and metadata
4. Add links to related documents
5. Update `SHEPHERD_INDEX.md` if it's a major addition

### Cross-Reference Guidelines

- Link to related documents liberally
- Use `| Related | [[DOCUMENT]] |` tables for "See Also" sections
- When adding evidence, link it from the relevant case file
- When adding personnel, link them from relevant evidence

### Collapsible Content

Use for:
- Detailed analysis that might overwhelm casual readers
- Classified information revealed progressively
- Addenda and supplementary materials
- Long technical specifications

---

## Quick Links

- [[SHEPHERD_INDEX]] - Main navigation hub
- [[CASE-2025-07-BLK]] - Primary case file
- [[EVD-ICR-TEL-2025-07-06]] - Critical evidence (collar telemetry)
- [[PERSONNEL-SEVRON]] - Primary POI

---

*SHEPHERD System v2.0*
