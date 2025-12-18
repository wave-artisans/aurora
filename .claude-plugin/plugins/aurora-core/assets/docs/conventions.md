---
doc-id: aurora-conventions
title: Aurora Conventions
description: Document naming, MAGI front matter, and link pattern standards
aurora-mode: null
tags: [conventions, meta, reference]
created: 2025-12-17
updated: 2025-12-17
---

# Aurora Conventions

This document defines the standards for naming, MAGI front matter, and link patterns in the Aurora knowledge management system.

## Document Naming

### General Rules

1. **All lowercase with hyphens** (kebab-case)
2. **No spaces or special characters** (except hyphens and underscores)
3. **Date prefix for temporal documents**: `YYYY-MM-DD_`
4. **Descriptive, searchable names**

### Patterns by Type

| Type | Pattern | Example |
|------|---------|---------|
| Standard | `{descriptive-name}.md` | `api-design-patterns.md` |
| Dated | `{YYYY-MM-DD}_{name}.md` | `2025-12-17_quarterly-review.md` |
| Meeting | `{YYYY-MM-DD}_{type}-{topic}.md` | `2025-12-17_sync-project-alpha.md` |
| Project root | `TOC.md` | `TOC.md` |
| Asset metadata | `{filename}.meta.md` | `diagram.png.meta.md` |
| Templates | `_template_{type}.md` | `_template_meeting.md` |

### Folder Naming

| Type | Pattern | Example |
|------|---------|---------|
| Aurora modes | `{Mode-Name}` | `Deep-Field/` |
| Projects | `{project-name}` (kebab) | `project-alpha/` |
| Year archives | `{YYYY}/` | `2025/` |
| Assets | `assets/` | `assets/` |

---

## MAGI Front Matter

All documents use MAGI (Markdown for Agent Guidance & Instruction) YAML front matter.

### Required Fields

```yaml
---
doc-id: unique-uuid-v4-here       # Globally unique, immutable
title: Document Title             # Human-readable
description: Brief 1-2 sentences  # Searchable summary
aurora-mode: focus                # explore|focus|commitments|ops|collab|life|archive
tags: [tag1, tag2]               # Categorization
created: 2025-12-17              # ISO date, immutable
updated: 2025-12-17              # Updated on each edit
---
```

### Optional Fields

```yaml
author: Athena                   # Creator name
version: 1.0.0                   # Semantic version
status: draft                    # draft|review|final|archived
source: https://...              # Original source URL
```

### Aurora Mode Values

| Value | Meaning |
|-------|---------|
| `explore` | 🟣 Curiosity Queue |
| `focus` | 🟢 Deep Field |
| `commitments` | 🔴 Waves Pumping |
| `ops` | 🟡 Quick Ops |
| `collab` | 🟠 Jam & Sync |
| `life` | 🔵 Recharge |
| `archive` | ⚫️ Done and Dusted |
| `null` | System/meta documents |

### doc-id Convention

The `doc-id` should be:
- **Globally unique** across the entire knowledge base
- **Kebab-case, lowercase**
- **Include context for disambiguation**

Examples:
- `deep-field-project-alpha-spec`
- `jam-sync-2025-12-17-alpha-sync`
- `library-api-design-patterns`

---

## Relationships via Footnotes

Document relationships use MAGI footnote syntax with JSON payloads.

### Syntax

```markdown
See the design document[^1] for details.

[^1]: {"rel-type": "references", "doc-id": "target-uuid", "rel-desc": "Context"}
```

### Relationship Types

| Type | Description | Example Use |
|------|-------------|-------------|
| `references` | Cites another doc | Meeting notes reference a project |
| `extends` | Builds upon another | Spec extends a design doc |
| `contains` | Parent-child | Project contains task list |
| `supports` | Supports goals | Meeting supports a project |
| `follows` | Temporal sequence | Meeting follows previous |
| `precedes` | Reverse temporal | Draft precedes final |
| `illustrates` | Visual supports text | Diagram illustrates concept |
| `implements` | Concrete from abstract | Code implements spec |
| `supersedes` | Replaces older doc | v2 supersedes v1 |
| `companion` | Binary + markdown pair | PDF + its metadata |

---

## iA Writer Link Patterns

Aurora is optimized for iA Writer. Use these patterns:

### External URLs

```markdown
[Display Text](https://example.com/page)
```

### Images in Assets (Same Folder)

```markdown
![Alt text](image-name.png)
```
Just the filename, no path. iA Writer resolves from current folder's `assets/`.

### Non-Image Binaries in Assets

```markdown
[PDF Report](./assets/report.pdf)
```
Relative path with `./assets/` prefix.

### Inline Content Includes

```markdown
content-to-include.md
```
Just the filename on its own line. iA Writer transcludes the content.

### Wiki-Style Reference Links

```markdown
[[Folder/Document|Display Title]]
[[Deep-Field/project-alpha/spec|Alpha Spec]]
[[/TOC|Table of Contents]]
```

---

## Binary Files & Companions

All binary files (PDFs, images, audio, video) in `assets/` folders should have a companion markdown file for discoverability.

### Companion Template

```yaml
---
doc-id: asset-name-meta
title: Asset Name
description: Description of the binary file
aurora-mode: focus
tags: [asset-type, topic]
created: 2025-12-17
updated: 2025-12-17
asset:
  filename: original-file.pdf
  type: document
  path: ./assets/original-file.pdf
---

# Asset Name

![Preview](original-file.pdf) or [Download](./assets/original-file.pdf)

## Notes

Description and context for this asset.
```

---

## Tags

### Hierarchical Tags

Use `/` for hierarchy:
- `technology/ai`
- `project/alpha`
- `client/acme`

### Reserved Tags

| Tag | Usage |
|-----|-------|
| `meta` | System documents |
| `template` | Template files |
| `archived` | Deprecated content |

---

*Parent: [[/README|Home]]*
