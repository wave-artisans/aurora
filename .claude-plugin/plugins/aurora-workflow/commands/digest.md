---
description: Generate periodic activity summary
argument-hint: [daily|weekly|monthly]
---

# Digest Command

Generate periodic activity summaries.

## Usage

```
/digest [daily|weekly|monthly]
```

## Description

The digest command generates a summary of activity across your Aurora knowledge base for the specified period.

## Daily Digest

```
/digest daily
```

Shows:
- Documents modified today
- Tasks completed
- New items added
- Aurora mode distribution of activity
- Key decisions or actions noted

## Weekly Digest

```
/digest weekly
```

Shows:
- Activity by Aurora mode
- Color balance over the week
- Major documents created/updated
- Task completion rate
- Meeting summaries (from Jam & Sync)
- Items archived (Done & Dusted)

## Monthly Digest

```
/digest monthly
```

Shows:
- High-level trends
- Projects started/completed
- Mode distribution analysis
- Notable achievements
- Recommendations for next month

## Output Example

```
📊 Weekly Digest - Dec 11-17, 2025

Activity by Mode:
  🟢 Deep Field:     12 edits (focus week!)
  🔴 Waves Pumping:   8 items completed
  🟠 Jam & Sync:      3 meetings captured
  🟣 Curiosity:       5 new explorations
  🔵 Recharge:        2 entries (consider more!)

Highlights:
  ✅ Project Alpha milestone reached
  ✅ Client proposal submitted
  📝 3 new research notes added

Tasks:
  Completed: 12
  Added: 8
  Overdue: 1

Archived:
  - Invoice batch Dec 2025 → Done & Dusted

Color Balance: 🟢🟢🔴🔴🟠🟣🟣
  Good focus week. Add some 🔵 next week.
```

## Related Commands

- `/aurora-status` - Current color balance
- `/rhythm weekly` - Pattern visualization
- `/surf-report` - Today's energy check
