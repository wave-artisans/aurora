# Aurora System Initialization

Initialize or verify the complete Aurora Knowledge Management System structure.

## Usage

```
/aurora-init [--verify] [--fix]
```

## Description

This command initializes the complete Aurora file structure in the current repository. It creates all folders, metadata files, templates, and documentation needed for a fully functional Aurora knowledge base.

**Safe to run multiple times** - existing files are never overwritten.

## What Gets Created

### 1. Aurora Mode Folders (with assets/)

Create these folders, each with an `assets/` subfolder and `.gitkeep` files:

```
Inbox/
  assets/.gitkeep
Tasks/
  assets/.gitkeep
Curiosity-Queue/     # 🟣 Explore
  assets/.gitkeep
Deep-Field/          # 🟢 Focus
  assets/.gitkeep
Waves-Pumping/       # 🔴 Commitments
  assets/.gitkeep
Quick-Ops/           # 🟡 Ops
  assets/.gitkeep
Jam-Sync/            # 🟠 Collab
  assets/.gitkeep
Recharge/            # 🔵 Life
  assets/.gitkeep
Done-Dusted/         # ⚫️ Archive
  assets/.gitkeep
Library/
  assets/.gitkeep
  _templates/.gitkeep
```

### 2. MAGI Metadata Folder

```
.magi/
  .gitkeep
  index.json
  relationships.json
  tags.json
```

**index.json:**
```json
{
  "version": "1.0.0",
  "created": "{TODAY}",
  "updated": "{TODAY}",
  "documents": {}
}
```

**relationships.json:**
```json
{
  "version": "1.0.0",
  "created": "{TODAY}",
  "updated": "{TODAY}",
  "edges": [],
  "adjacency": {}
}
```

**tags.json:**
```json
{
  "version": "1.0.0",
  "created": "{TODAY}",
  "updated": "{TODAY}",
  "taxonomy": {
    "aurora": {
      "explore": [],
      "focus": [],
      "commitments": [],
      "ops": [],
      "collab": [],
      "life": [],
      "archive": []
    }
  },
  "flat": {}
}
```

### 3. Tasks/tasks.json

```json
{
  "version": "1.0.0",
  "created": "{TODAY}",
  "updated": "{TODAY}",
  "tasks": []
}
```

### 4. Root Documentation

**README.md** (with MAGI front matter):
```markdown
---
doc-id: aurora-readme
title: {REPO_NAME} Knowledge Base
description: Aurora-powered knowledge management system
aurora-mode: null
tags: [index, home]
created: {TODAY}
updated: {TODAY}
---

# {REPO_NAME} Knowledge Base

> Powered by Aurora - The 7-mode color system for organizing knowledge.

## Quick Start

1. Drop documents into `Inbox/`
2. Run `/intake` to process them
3. Use `/surf-report` to check your energy balance

## Navigation

- [[TOC|Table of Contents]]
- [[CONVENTIONS|Conventions]]

## The Seven Modes

| Color | Mode | Folder |
|-------|------|--------|
| 🟣 | Explore | [[Curiosity-Queue/TOC\|Curiosity Queue]] |
| 🟢 | Focus | [[Deep-Field/TOC\|Deep Field]] |
| 🔴 | Commitments | [[Waves-Pumping/TOC\|Waves Pumping]] |
| 🟡 | Ops | [[Quick-Ops/TOC\|Quick Ops]] |
| 🟠 | Collab | [[Jam-Sync/TOC\|Jam & Sync]] |
| 🔵 | Life | [[Recharge/TOC\|Recharge]] |
| ⚫️ | Archive | [[Done-Dusted/TOC\|Done & Dusted]] |

## Resources

- [[Library/TOC\|Library (Evergreen)]]
- [[Tasks/tasks.json\|Task Tracker]]
```

**TOC.md:**
```markdown
---
doc-id: aurora-toc
title: Table of Contents
description: Global navigation for the Aurora knowledge base
aurora-mode: null
tags: [index, navigation, meta]
created: {TODAY}
updated: {TODAY}
---

# Table of Contents

## Aurora Modes

### 🟣 Curiosity Queue (Explore)
[[Curiosity-Queue/TOC|Browse Exploration →]]

### 🟢 Deep Field (Focus)
[[Deep-Field/TOC|Browse Focus Work →]]

### 🔴 Waves Pumping (Commitments)
[[Waves-Pumping/TOC|Browse Commitments →]]

### 🟡 Quick Ops (Operations)
[[Quick-Ops/TOC|Browse Operations →]]

### 🟠 Jam & Sync (Collaboration)
[[Jam-Sync/TOC|Browse Collaborations →]]

### 🔵 Recharge (Life)
[[Recharge/TOC|Browse Life →]]

### ⚫️ Done & Dusted (Archive)
[[Done-Dusted/TOC|Browse Archive →]]

## Resources

### 📚 Library
[[Library/TOC|Browse Evergreen Content →]]

### 📥 Inbox
[[Inbox/|View Inbox →]]

### ✅ Tasks
[[Tasks/tasks.json|View Tasks →]]

---

*[[README|← Back to Home]]*
```

**CONVENTIONS.md:**
```markdown
---
doc-id: aurora-conventions
title: Aurora Conventions
description: Document naming, MAGI front matter, and link pattern standards
aurora-mode: null
tags: [conventions, meta, reference]
created: {TODAY}
updated: {TODAY}
---

# Aurora Conventions

## Document Naming

### General Rules
1. **Kebab-case** (lowercase with hyphens)
2. **No spaces or special characters**
3. **Date prefix for temporal**: `YYYY-MM-DD_name.md`

### Patterns
| Type | Pattern | Example |
|------|---------|---------|
| Standard | `{name}.md` | `api-design.md` |
| Dated | `{YYYY-MM-DD}_{name}.md` | `2025-12-17_meeting.md` |
| Template | `_template_{type}.md` | `_template_meeting.md` |

## MAGI Front Matter

All documents use YAML front matter:

```yaml
---
doc-id: unique-identifier
title: Document Title
description: Brief summary
aurora-mode: focus
tags: [tag1, tag2]
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### Aurora Mode Values
| Value | Mode |
|-------|------|
| `explore` | 🟣 Curiosity Queue |
| `focus` | 🟢 Deep Field |
| `commitments` | 🔴 Waves Pumping |
| `ops` | 🟡 Quick Ops |
| `collab` | 🟠 Jam & Sync |
| `life` | 🔵 Recharge |
| `archive` | ⚫️ Done & Dusted |

## Relationship Footnotes

```markdown
See the spec[^1] for details.

[^1]: {"rel-type": "references", "doc-id": "target-id", "rel-desc": "Description"}
```

## iA Writer Links

| Type | Format |
|------|--------|
| External | `[title](https://...)` |
| Image | `image.png` |
| Binary | `[title](./assets/file.pdf)` |
| Wiki | `[[Path/Doc\|Title]]` |

---

*[[README|← Back to Home]]*
```

**.gitignore:**
```
# OS files
.DS_Store
Thumbs.db

# Editor files
*.swp
*.swo
*~
.idea/
.vscode/

# Temporary
*.tmp
*.temp

# Local config
.local/
*.local.md
```

### 5. Folder TOC Files

Create a TOC.md in each Aurora mode folder with appropriate MAGI front matter:

**Template for mode TOC (e.g., Curiosity-Queue/TOC.md):**
```markdown
---
doc-id: {mode}-toc
title: {Mode Name}
description: Table of contents for {Mode Name}
aurora-mode: {mode-value}
tags: [index, {mode}]
created: {TODAY}
updated: {TODAY}
---

# {Mode Emoji} {Mode Name}

> {Mode Description}

## Documents

*No documents yet. Use `/intake` to add content.*

---

*[[TOC|← Global TOC]] | [[README|Home]]*
```

Create for each mode:
- `Curiosity-Queue/TOC.md` - 🟣 Curiosity Queue (Explore)
- `Deep-Field/TOC.md` - 🟢 Deep Field (Focus)
- `Waves-Pumping/TOC.md` - 🔴 Waves Pumping (Commitments)
- `Quick-Ops/TOC.md` - 🟡 Quick Ops (Operations)
- `Jam-Sync/TOC.md` - 🟠 Jam & Sync (Collaboration)
- `Recharge/TOC.md` - 🔵 Recharge (Life)
- `Done-Dusted/TOC.md` - ⚫️ Done & Dusted (Archive)
- `Library/TOC.md` - 📚 Library (Evergreen)

### 6. Templates in Library/_templates/

Create four template files:

**_template_standard.md** - Basic document
**_template_project.md** - Project documentation
**_template_meeting.md** - Meeting notes
**_template_asset-meta.md** - Binary file companion

See the plugin assets for complete template content.

## Flags

### --verify
Check existing structure without making changes. Reports:
- Missing folders
- Missing .gitkeep files
- Missing TOC files
- Missing metadata files
- Missing templates

### --fix
Verify and automatically create any missing components.

## Initialization Output

After successful initialization, display:

```
✅ Aurora initialized successfully!

Created:
  📁 11 folders (with assets/)
  📄 12 .gitkeep files
  📄 4 metadata files (.magi/)
  📄 3 root docs (README, TOC, CONVENTIONS)
  📄 8 folder TOCs
  📄 4 templates

Next steps:
  1. Drop documents into Inbox/
  2. Run /intake to process them
  3. Use /surf-report to check your energy
```

## Notes

- All dates should use ISO format: YYYY-MM-DD
- Replace {TODAY} with current date
- Replace {REPO_NAME} with the repository name
- Generate unique doc-ids using descriptive kebab-case identifiers
- Safe to run multiple times - never overwrites existing files
