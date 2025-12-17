# Aurora Plugin Collection

> A 7-mode color system for organizing knowledge by energy and intent, not task status.

Aurora is a Claude Code plugin marketplace that transforms any git repository into a powerful knowledge management system. It beats Notion, Obsidian, and similar tools by leveraging Claude's intelligence for document understanding, synthesis, and proactive assistance.

## The Aurora Philosophy

**Color = Energy, not Status.**

Red isn't "urgent" - it's *committed*. Green isn't "active" - it's *focused*. Aurora organizes your work by how you engage with it, not by arbitrary priority levels.

## The Seven Modes

| Color | Mode | Folder | Energy |
|-------|------|--------|--------|
| 🟣 | Explore | `Curiosity-Queue/` | Curiosity without agenda |
| 🟢 | Focus | `Deep-Field/` | Deep creative work |
| 🔴 | Commitments | `Waves-Pumping/` | Deadlines and promises |
| 🟡 | Ops | `Quick-Ops/` | Admin and systems |
| 🟠 | Collab | `Jam-Sync/` | Co-creation |
| 🔵 | Life | `Recharge/` | Rest and balance |
| ⚫️ | Archive | `Done-Dusted/` | Completed work |

## Installation

```
/plugin marketplace add wave-artisans/aurora
/plugin install aurora-core@aurora
/aurora-init
```

**Optional plugins:**
```
/plugin install aurora-intelligence@aurora   # AI-powered features
/plugin install aurora-workflow@aurora       # Automation
```

## Quick Start

1. **Initialize** - Run `/aurora-init` in any git repository
2. **Intake** - Drop files into `Inbox/`, run `/intake`
3. **Flow** - Use `/surf-report` to check your energy balance

## Available Plugins

### aurora-core (Essential)
16 commands for system initialization, mode management, and document operations.

**Mode Commands:**
- `/surf-report` - What mode should you be in right now?
- `/aurora-status` - Visualize your color balance
- `/paddle` - Enter focus mode (🟢 Deep Field)
- `/float` - Enter rest mode (🔵 Recharge)
- `/catch-wave` - Check your commitments (🔴)
- `/rhythm` - See your patterns over time

**Document Commands:**
- `/aurora-init` - Initialize Aurora in any repository
- `/intake` - Process documents from Inbox
- `/retrieve` - Search your knowledge base
- `/validate` - Check system health
- `/task` - Manage tasks
- `/move`, `/archive` - Move documents between modes

### aurora-intelligence (Recommended)
9 AI-powered commands for document understanding and synthesis.

- `/ask <question>` - Get answers from your knowledge base
- `/summarize` - Multi-level summarization
- `/brief <topic>` - Executive summary on any topic
- `/report <topic>` - Comprehensive reports from multiple sources
- `/compare`, `/expand`, `/simplify`, `/translate` - Content transformation
- `/relate` - Discover document relationships

### aurora-workflow (Optional)
5 automation commands for proactive assistance.

- `/digest daily|weekly` - Periodic activity summaries
- `/extract-actions` - Pull tasks from meeting notes
- `/gaps` - Find missing documentation
- `/stale` - Identify outdated content
- `/trends` - Analyze topic evolution

## Why Aurora Beats Notion

| Feature | Notion | Aurora + Claude |
|---------|--------|-----------------|
| Search | Keyword only | Natural language + context |
| Summarization | None | Multi-level (1-line to full report) |
| Cross-doc Q&A | None | Synthesized answers with citations |
| Relationship Discovery | Manual | AI auto-detects connections |
| Action Extraction | Manual | Auto-extracts from meeting notes |
| Report Generation | Templates only | AI synthesizes from sources |
| Ownership | Cloud-locked | Git-based, you own everything |
| Editor | Notion only | Any editor (iA Writer, VS Code, etc.) |
| Offline | Limited | Full offline with git |
| Cost | $$/user/month | Free (just Claude usage) |

## Example Daily Flow

```
Morning:   /surf-report      → "Heavy 🔴 week. Consider 🔵 time today."
Focus:     /paddle           → Shows Deep Field priorities
Midday:    /catch-wave       → Check commitments before meeting
Evening:   /float            → Surface Recharge items
Weekly:    /rhythm weekly    → "40% 🔴, 30% 🟢, 10% 🔵 - add blue"
```

## MAGI Front Matter

All documents use MAGI (Markdown for Agent Guidance & Instruction) YAML front matter:

```yaml
---
doc-id: unique-identifier
title: Document Title
description: Brief summary
aurora-mode: focus
tags: [tag1, tag2]
created: 2025-12-17
updated: 2025-12-17
---
```

## Documentation

After installing, find detailed documentation in:
- Plugin assets: `.claude-plugin/plugins/aurora-core/assets/docs/`
  - `philosophy.md` - The Aurora philosophy in depth
  - `conventions.md` - MAGI and naming standards
  - `quick-start.md` - Getting started guide

## Core Principles

1. **Color = Energy, not Status** - Modes represent how you engage, not priority
2. **Fluid Movement** - Projects naturally flow 🟣→🟢→🔴→⚫️
3. **Weekly Rhythm** - Balance colors like a waveform
4. **System That Breathes** - Change modes when energy shifts

## Repository Structure

This repository is a **plugin marketplace**. After installation, `/aurora-init` creates the actual Aurora folder structure in your target repository:

```
your-repo/
├── Inbox/                   # Intake zone
├── Tasks/                   # Task tracking
├── Curiosity-Queue/         # 🟣 Explore
├── Deep-Field/              # 🟢 Focus
├── Waves-Pumping/           # 🔴 Commitments
├── Quick-Ops/               # 🟡 Ops
├── Jam-Sync/                # 🟠 Collab
├── Recharge/                # 🔵 Life
├── Done-Dusted/             # ⚫️ Archive
├── Library/                 # Evergreen content
│   └── _templates/          # MAGI templates
└── .magi/                   # Metadata index
```

## Contributing

To contribute to Aurora:
1. Fork this repository
2. Add or modify plugins in `.claude-plugin/plugins/`
3. Update `marketplace.json` if adding new plugins
4. Submit a pull request

## License

MIT

---

*Like surfing: know when to paddle hard, when to ride, and when to float.*
