---
doc-id: aurora-readme
title: Aurora Knowledge Management System
description: A 7-mode color system for organizing knowledge, tasks, and creative work
aurora-mode: null
tags: [system, documentation, meta]
created: 2025-12-17
updated: 2025-12-17
author: Athena
version: 1.0.0
---

# Aurora Knowledge Management System

> *A system for people who build, play, surf, and create. Color = Energy, not Status.*

Aurora is a git-based document and knowledge management system powered by Claude. It uses a 7-mode color system to organize your work by **energy and intent**, not just task status.

## Installation (Claude Code Plugin Marketplace)

Aurora is distributed as a Claude Code plugin marketplace. Install the plugins to add Aurora capabilities to any project.

### Add the Aurora Marketplace

```
/plugin marketplace add owner/aurora
```

### Install Aurora Plugins

**All-in-one (recommended):**
```
/plugin install aurora-core@aurora
/plugin install aurora-intelligence@aurora
/plugin install aurora-workflow@aurora
```

**Or install individually:**

| Plugin | Description |
|--------|-------------|
| `aurora-core` | Essential: modes, intake, retrieval, validation |
| `aurora-intelligence` | AI-powered: Q&A, reports, briefs, summarization |
| `aurora-workflow` | Automation: digests, actions, trends |

### Initialize Aurora in Your Repository

After installing plugins:
```
/aurora-init
```

This creates the complete Aurora folder structure in your current repository.

## The Seven Modes

| Color | Mode | Folder | Vibe |
|-------|------|--------|------|
| 🟣 | Explore | [[Curiosity-Queue/TOC\|Curiosity Queue]] | The horizon. Curiosity without agenda. |
| 🟢 | Focus | [[Deep-Field/TOC\|Deep Field]] | The zone. Headphones on, flow state. |
| 🔴 | Commitments | [[Waves-Pumping/TOC\|Waves Pumping]] | The pulse. Deadlines and promises. |
| 🟡 | Ops | [[Quick-Ops/TOC\|Quick Ops]] | The backbone. Admin and systems. |
| 🟠 | Collab | [[Jam-Sync/TOC\|Jam & Sync]] | The vibe-share. Co-creating together. |
| 🔵 | Life | [[Recharge/TOC\|Recharge]] | The ride. Surf, play, rest. |
| ⚫️ | Archive | [[Done-Dusted/TOC\|Done & Dusted]] | The echo. Completed work. |

## Quick Links

- [[TOC\|Global Table of Contents]]
- [[Tasks/tasks.json\|Task Tracker]]
- [[Library/TOC\|Library (Evergreen)]]
- [[Inbox/\|Inbox (Intake)]]
- [[CONVENTIONS\|Document Conventions]]

## Core Commands

### Aurora Mode Management
```
/surf-report          # What mode should you be in right now?
/aurora-status        # Visualize your color balance
/rhythm weekly        # See your patterns over time
/paddle               # Enter deep work mode (Deep Field)
/float                # Shift to rest mode (Recharge)
/catch-wave           # Check deadlines (Waves Pumping)
```

### Document Operations
```
/intake               # Process documents from Inbox
/retrieve <query>     # Search your knowledge base
/ask <question>       # Get answers from your docs
/validate             # Check system health
```

### Intelligence
```
/digest daily         # Daily activity summary
/brief <topic>        # Executive summary on any topic
/report <topic>       # Full report from multiple sources
/extract-actions      # Pull tasks from meeting notes
```

## Getting Started

1. Drop new content into `Inbox/`
2. Run `/intake` to process with MAGI metadata
3. Documents flow to appropriate Aurora mode folders
4. Use `/surf-report` to check your energy balance
5. Surf between modes: `/paddle` for focus, `/float` for rest

## The Aurora Philosophy

- **Color = Energy, not Status**: Red isn't "urgent" - it's *committed*
- **Fluid Movement**: Projects naturally evolve 🟣→🟢→🔴→⚫️
- **Weekly Rhythm**: Look at your color balance as a waveform
- **System That Breathes**: When feeling off, change colors, not tasks

---

*Like surfing: know when to paddle hard, when to ride, and when to float.*

## Plugin Details

### aurora-core (16 commands)
Essential operations for managing your Aurora knowledge base.

**Mode Management:** `/surf-report`, `/aurora-status`, `/paddle`, `/float`, `/catch-wave`, `/rhythm`, `/flow`, `/rebalance`

**Document Operations:** `/aurora-init`, `/intake`, `/validate`, `/retrieve`, `/task`, `/toc-update`, `/move`, `/archive`

### aurora-intelligence (9 commands)
AI-powered document understanding and generation.

**Q&A & Synthesis:** `/ask`, `/summarize`, `/relate`

**Document Generation:** `/brief`, `/report`

**Content Transformation:** `/compare`, `/expand`, `/simplify`, `/translate`

### aurora-workflow (5 commands)
Automation and analysis tools.

**Periodic:** `/digest`

**Analysis:** `/gaps`, `/stale`, `/trends`

**Extraction:** `/extract-actions`

## Reference

- [[docs/aurora\|Aurora System Philosophy]]
- [[CONVENTIONS\|MAGI & Naming Conventions]]
- [[Library/_templates/\|Document Templates]]

## Marketplace Structure

```
.claude-plugin/
├── marketplace.json           # Marketplace definition
└── plugins/
    ├── aurora-core/          # Essential operations
    │   ├── plugin.json
    │   ├── commands/         # 16 commands
    │   └── agents/           # Aurora system agent
    ├── aurora-intelligence/  # AI-powered features
    │   ├── plugin.json
    │   └── commands/         # 9 commands
    └── aurora-workflow/      # Automation
        ├── plugin.json
        └── commands/         # 5 commands
```

## Contributing

To contribute plugins to Aurora:
1. Fork this repository
2. Add your plugin to `.claude-plugin/plugins/`
3. Update `marketplace.json` with your plugin entry
4. Submit a pull request
