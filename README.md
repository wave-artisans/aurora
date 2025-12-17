# Aurora

> The world's first AI-native knowledge ecosystem.
> A gift from Wave Artisans to humanity.

Aurora transforms how humans organize knowledge by putting AI at the center—not as a feature, but as the foundation. It's free, open, and yours forever.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blueviolet)](https://claude.com/claude-code)

---

## The Aurora Philosophy

**Color = Energy, not Status.**

Traditional productivity tools organize by urgency, priority, or status. Aurora organizes by *energy*—how you engage with your work, not how important someone else thinks it is.

Red isn't "urgent"—it's *committed*. Green isn't "active"—it's *focused*. Blue isn't "low priority"—it's *life*.

Like surfing, productivity has rhythm. Sometimes you paddle hard. Sometimes you ride the wave. Sometimes you float. Aurora helps you recognize which mode you're in and honor it.

### The Seven Modes

| Color | Mode | Folder | Energy |
|-------|------|--------|--------|
| 🟣 | Explore | `Curiosity-Queue/` | Curiosity without agenda |
| 🟢 | Focus | `Deep-Field/` | Deep creative work |
| 🔴 | Commitments | `Waves-Pumping/` | Deadlines and promises |
| 🟡 | Ops | `Quick-Ops/` | Admin and systems |
| 🟠 | Collab | `Jam-Sync/` | Co-creation with others |
| 🔵 | Life | `Recharge/` | Rest, health, balance |
| ⚫️ | Archive | `Done-Dusted/` | Completed work worth keeping |

Projects naturally flow: 🟣 → 🟢 → 🔴 → ⚫️

But life isn't linear. Sometimes you go back. Sometimes you skip. Aurora tracks the flow without judgment.

---

## Why Aurora Exists

### The Problem with Existing Tools

**Notion**: Your data lives on their servers. No end-to-end encryption. AI is an add-on, not native. $10+/month per person. Try exporting—you'll lose formatting, links, and structure.

**Obsidian**: Powerful but complex. Steep learning curve. AI requires third-party plugins with varying quality. Sync costs extra. You're assembling a system, not using one.

**Craft**: Beautiful but limited. $8/month. Cloud-dependent. Basic AI. Less flexible for power users.

### Aurora's Answer

- **AI-native from day one** — Claude understands your documents, finds connections, answers questions
- **Plain markdown** — A format that will outlive every app. Human-readable forever.
- **Git-based** — Infinite history. Multiple copies. Real version control.
- **Free and open source** — MIT licensed. No subscriptions. No lock-in.
- **Your favorite editor** — iA Writer, VS Code, Typora, or any markdown editor

---

## How It Works

```
1. Install Aurora plugins in Claude Code
2. Run /aurora-init in any git repo
3. Drop files in Inbox/, run /intake
4. Claude understands, organizes, and assists
```

**The Magic:**

- **Natural language search** — Ask "What did we decide about authentication?" and get synthesized answers with citations
- **Cross-document intelligence** — Claude finds connections you'd never spot manually
- **Proactive assistance** — Get burnout warnings, stale content alerts, and balance suggestions
- **Energy tracking** — See your weekly color distribution like a waveform

---

## Work from Anywhere

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   iPhone    │────▶│  VPS/Server │────▶│   Aurora    │
│   iPad      │ SSH │ Claude Code │     │  Knowledge  │
│   Mac       │     │             │     │    Base     │
└─────────────┘     └─────────────┘     └─────────────┘
```

### VPS Options

Host Claude Code on a server and access Aurora from any device:

- **[Hostinger](https://hostinger.com)** — Pre-built Claude Code VPS template
- **[DigitalOcean](https://digitalocean.com)** — Simple droplet setup ($5/month)
- **Any Linux VPS** — Just needs Node.js and SSH access

### Apple Shortcuts Integration

Control Aurora from your iPhone or iPad:

- Built-in **"Run Script Over SSH"** action in Apple Shortcuts
- Trigger `/surf-report`, `/intake`, or any Aurora command remotely
- Create location-based automations ("When I arrive at office, show my commitments")
- Voice commands via Siri

### iA Writer: The Perfect Companion

Aurora was designed with [iA Writer](https://ia.net/writer) in mind—the most beautiful, focused markdown editor:

| Feature | Aurora + iA Writer |
|---------|-------------------|
| **Wiki Links** | `[[document]]` works perfectly with Aurora's structure |
| **YAML Frontmatter** | Full MAGI metadata support (hidden in editor, visible when needed) |
| **Content Blocks** | Transclude documents seamlessly |
| **Cross-Platform** | macOS, iOS, iPadOS, Windows, Android |
| **Focus** | You write, Aurora organizes, Claude understands |

Your files stay as plain markdown. Edit in iA Writer on your iPad. Sync with git. Claude processes everything on your VPS. It just works.

*Other editors (VS Code, Obsidian as editor, Typora) work too—Aurora uses standard markdown.*

---

## Your Data, Your Rules

| Aspect | Notion / Cloud Apps | Aurora |
|--------|---------------------|--------|
| **Storage** | Their servers | Your machine / your VPS |
| **Format** | Proprietary database | Plain Markdown |
| **Encryption** | They hold the keys | You control everything |
| **Backup** | Trust them | Git = copies everywhere |
| **Export** | Limited, lossy | Already portable |
| **Longevity** | Until they shut down | Forever |

### Multiple Copies by Default

- Your local machine
- Git remote (GitHub, GitLab, your own server)
- VPS if using remote access
- iCloud/Dropbox sync for the folder (your choice)

Your knowledge base isn't trapped. It's yours.

---

## Aurora vs The Rest

| Feature | Notion | Obsidian | Craft | Aurora |
|---------|--------|----------|-------|--------|
| **AI Integration** | Add-on | Plugins | Basic | **Native** |
| **Data Ownership** | Cloud | Local | Cloud | **Local + Git** |
| **Format** | Proprietary | Markdown | Proprietary | **Markdown** |
| **Cost** | $10+/mo | $5/mo sync | $8/mo | **Free** |
| **Search** | Keywords | Local | Keywords | **AI Semantic** |
| **Cross-doc Q&A** | No | Plugins | No | **Native** |
| **Summarization** | Basic | Plugins | No | **Multi-level** |
| **Open Source** | No | No | No | **Yes (MIT)** |
| **Mobile Access** | App | App | App | **SSH + Any editor** |
| **Offline** | Limited | Yes | Limited | **Full** |

---

## Installation

```bash
# Add the Aurora marketplace
/plugin marketplace add wave-artisans/aurora

# Install core plugin (required)
/plugin install aurora-core@aurora

# Initialize in any repository
/aurora-init
```

**Optional plugins:**
```bash
/plugin install aurora-intelligence@aurora   # AI-powered Q&A, summaries, reports
/plugin install aurora-workflow@aurora       # Digests, action extraction, automation
```

---

## Quick Start

1. **Initialize** — Run `/aurora-init` in any git repository
2. **Intake** — Drop files into `Inbox/`, run `/intake`
3. **Flow** — Use `/surf-report` to check your energy balance

---

## Available Plugins

### aurora-core (Essential)

16 commands for system initialization, mode management, and document operations.

**Mode Commands:**
- `/surf-report` — What mode should you be in right now?
- `/aurora-status` — Visualize your color balance
- `/paddle` — Enter focus mode (🟢 Deep Field)
- `/float` — Enter rest mode (🔵 Recharge)
- `/catch-wave` — Check your commitments (🔴)
- `/rhythm` — See your patterns over time

**Document Commands:**
- `/aurora-init` — Initialize Aurora in any repository
- `/intake` — Process documents from Inbox
- `/retrieve` — Search your knowledge base
- `/validate` — Check system health
- `/task` — Manage tasks
- `/move`, `/archive` — Move documents between modes

### aurora-intelligence (Recommended)

AI-powered commands for document understanding and synthesis.

- `/ask <question>` — Get answers from your knowledge base
- `/summarize` — Multi-level summarization
- `/brief <topic>` — Executive summary on any topic
- `/report <topic>` — Comprehensive reports from multiple sources
- `/compare`, `/expand`, `/simplify`, `/translate` — Content transformation
- `/relate` — Discover document relationships

### aurora-workflow (Optional)

Automation commands for proactive assistance.

- `/digest daily|weekly` — Periodic activity summaries
- `/extract-actions` — Pull tasks from meeting notes
- `/gaps` — Find missing documentation
- `/stale` — Identify outdated content
- `/trends` — Analyze topic evolution

---

## Example Daily Flow

```
Morning:   /surf-report      → "Heavy 🔴 week. Consider 🔵 time today."
Focus:     /paddle           → Shows Deep Field priorities
Midday:    /catch-wave       → Check commitments before meeting
Evening:   /float            → Surface Recharge items
Weekly:    /rhythm weekly    → "40% 🔴, 30% 🟢, 10% 🔵 - add blue"
```

---

## Technical Details

### MAGI Front Matter

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

### Repository Structure

After `/aurora-init`, your repository contains:

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

### Documentation

After installing, find detailed documentation in:
- Plugin assets: `.claude-plugin/plugins/aurora-core/assets/docs/`
  - `philosophy.md` — The Aurora philosophy in depth
  - `conventions.md` — MAGI and naming standards
  - `quick-start.md` — Getting started guide

---

## Contributing

To contribute to Aurora:

1. Fork this repository
2. Add or modify plugins in `.claude-plugin/plugins/`
3. Update `marketplace.json` if adding new plugins
4. Submit a pull request

---

## From Wave Artisans

Aurora is our gift to the world—a belief that AI should help humans live better, not lock them into subscriptions and walled gardens.

We built Aurora because we needed it ourselves. Now it's yours.

**Free. Open. Forever.**

---

## License

[MIT](LICENSE)

---

*Like surfing: know when to paddle hard, when to ride, and when to float.*
