# Aurora System Skill

Core skill for managing the Aurora Knowledge Management System.

## Overview

The Aurora System is a git-based document and knowledge management system using a 7-mode color system to organize work by **energy and intent**, not task status.

## The Seven Modes

| Mode | Color | Folder | Energy |
|------|-------|--------|--------|
| Explore | 🟣 | `Curiosity-Queue/` | Curiosity without agenda |
| Focus | 🟢 | `Deep-Field/` | Deep creative work |
| Commitments | 🔴 | `Waves-Pumping/` | Deadlines and promises |
| Ops | 🟡 | `Quick-Ops/` | Admin and systems |
| Collab | 🟠 | `Jam-Sync/` | Co-creation |
| Life | 🔵 | `Recharge/` | Rest and balance |
| Archive | ⚫️ | `Done-Dusted/` | Completed work |

## Core Principles

1. **Color = Energy, not Status**: Modes represent how you engage, not priority
2. **Fluid Movement**: Projects naturally flow 🟣→🟢→🔴→⚫️
3. **Weekly Rhythm**: Balance colors like a waveform
4. **System That Breathes**: Change modes when energy shifts

## MAGI Front Matter

All documents use MAGI (Markdown for Agent Guidance & Instruction) YAML front matter:

```yaml
---
doc-id: unique-uuid-v4
title: Document Title
description: Brief summary
aurora-mode: focus
tags: [tag1, tag2]
created: 2025-12-17
updated: 2025-12-17
---
```

### Required Fields
- `doc-id`: Unique UUID v4, immutable after creation
- `title`: Human-readable title
- `description`: 1-2 sentence summary
- `aurora-mode`: One of: explore, focus, commitments, ops, collab, life, archive
- `tags`: Array of categorization tags
- `created`: ISO date, immutable
- `updated`: ISO date, updated on each edit

## Document Relationships

Use MAGI footnote syntax:

```markdown
See the spec[^1] for details.

[^1]: {"rel-type": "references", "doc-id": "target-uuid", "rel-desc": "Description"}
```

### Relationship Types
- `references`: Cites another document
- `extends`: Builds upon another
- `contains`: Parent-child containment
- `supports`: Supports goals
- `follows` / `precedes`: Temporal sequence
- `illustrates`: Visual supports textual
- `implements`: Concrete from abstract
- `supersedes`: Replaces older doc
- `companion`: Binary + markdown pair

## File Organization

### Metadata
- `.magi/index.json`: Document index (doc-id → path, title, mode, tags)
- `.magi/relationships.json`: Document graph edges
- `.magi/tags.json`: Tag taxonomy

### Tasks
- `Tasks/tasks.json`: Task tracker with aurora-mode integration

### Naming Conventions
- Kebab-case for files: `project-alpha-spec.md`
- Date prefix for temporal: `2025-12-17_meeting-notes.md`
- Assets in `assets/` subfolders

## iA Writer Compatibility

This system is optimized for iA Writer:

| Type | Format |
|------|--------|
| External URL | `[title](https://...)` |
| Image in assets | `image.png` |
| Binary in assets | `[title](./assets/file.pdf)` |
| Inline include | `content.md` |
| Wiki reference | `[[Path/Doc|Title]]` |

## Mode Classification Guidelines

When classifying documents:

1. **Is it exploratory/learning?** → 🟣 Curiosity Queue
2. **Is it deep creative work?** → 🟢 Deep Field
3. **Has external commitment/deadline?** → 🔴 Waves Pumping
4. **Is it administrative/operational?** → 🟡 Quick Ops
5. **Is it collaborative/shared?** → 🟠 Jam & Sync
6. **Is it personal/lifestyle?** → 🔵 Recharge
7. **Is it completed/archived?** → ⚫️ Done and Dusted

## Available Commands

### Core Management
- `/aurora-init` - Initialize system
- `/intake` - Process Inbox documents
- `/validate` - Check system health
- `/retrieve` - Search documents
- `/task` - Manage tasks
- `/toc-update` - Update ToCs
- `/move` - Move between modes
- `/archive` - Archive documents

### Aurora Mode Management
- `/surf-report` - Energy check
- `/aurora-status` - Color balance
- `/rhythm` - Pattern analysis
- `/paddle` - Focus mode
- `/float` - Rest mode
- `/catch-wave` - Commitment check
- `/flow` - Mode transition
- `/rebalance` - Balance suggestions

### Intelligence
- `/ask` - Knowledge Q&A
- `/summarize` - Summarization
- `/digest` - Periodic digests
- `/report` - Report generation
- `/brief` - Executive briefs
- `/extract-actions` - Action extraction
- `/gaps` - Gap analysis
- `/stale` - Freshness check
- `/trends` - Trend analysis
- `/compare` - Document comparison
- `/expand` - Content expansion
- `/simplify` - Simplification
- `/translate` - Style transfer
