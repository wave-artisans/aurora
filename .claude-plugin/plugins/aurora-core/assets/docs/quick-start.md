# Aurora Quick Start Guide

Get up and running with Aurora in 5 minutes.

## Step 1: Install Aurora Plugins

```
/plugin marketplace add wave-artisans/aurora
/plugin install aurora-core@aurora
```

Optional (recommended):
```
/plugin install aurora-intelligence@aurora
/plugin install aurora-workflow@aurora
```

## Step 2: Initialize Your Knowledge Base

Navigate to your repository and run:

```
/aurora-init
```

This creates the complete Aurora folder structure with all necessary files.

## Step 3: Add Your First Document

1. Drop a file into `Inbox/`
2. Run `/intake` to process it
3. Aurora classifies and places it in the appropriate mode folder

## Step 4: Check Your Energy Balance

```
/surf-report
```

This tells you which mode you should focus on based on your current patterns.

## Step 5: Work Your Flow

- `/paddle` - Enter focus mode (Deep Field)
- `/float` - Enter rest mode (Recharge)
- `/catch-wave` - Check your commitments

## Daily Workflow

**Morning:**
```
/surf-report          # What mode should I be in?
/digest daily         # What happened yesterday?
```

**During work:**
```
/intake               # Process new documents
/retrieve <query>     # Find information
/ask <question>       # Get answers from your KB
```

**End of week:**
```
/rhythm weekly        # See your color balance
/rebalance           # Get suggestions for improvement
```

## The Seven Modes

| Color | Mode | Folder | Use When... |
|-------|------|--------|-------------|
| 🟣 | Explore | Curiosity-Queue/ | Learning, researching, curious |
| 🟢 | Focus | Deep-Field/ | Creating, coding, writing |
| 🔴 | Commitments | Waves-Pumping/ | Deadlines, deliverables |
| 🟡 | Ops | Quick-Ops/ | Admin, maintenance |
| 🟠 | Collab | Jam-Sync/ | Meetings, teamwork |
| 🔵 | Life | Recharge/ | Rest, personal, fun |
| ⚫️ | Archive | Done-Dusted/ | Completed work |

## Tips

1. **Don't overthink modes** - Pick the main energy, not the perfect category
2. **Check weekly, not daily** - Aurora is about rhythm, not rigidity
3. **Change colors often** - Projects naturally flow 🟣→🟢→🔴→⚫️
4. **Trust the surf report** - It knows your patterns

## Next Steps

- Read the [Philosophy](philosophy.md) to understand Aurora deeply
- Check [Conventions](conventions.md) for MAGI and naming standards
- Explore all commands with `/help aurora`
