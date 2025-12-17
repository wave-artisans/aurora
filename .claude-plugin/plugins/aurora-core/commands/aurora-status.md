# Aurora Status Command

Visualize your color balance across all documents and activity.

## Usage

```
/aurora-status [--period <period>]
```

## Description

Shows the distribution of your documents and activity across all 7 Aurora modes as a visual "waveform."

## Output

```
🌌 Aurora Status

Document Distribution:
  🟣 Curiosity Queue:    ████████░░░░░░░░░░░░  23 docs (18%)
  🟢 Deep Field:         ██████████████░░░░░░  42 docs (33%)
  🔴 Waves Pumping:      ██████████░░░░░░░░░░  28 docs (22%)
  🟡 Quick Ops:          ████░░░░░░░░░░░░░░░░  12 docs (9%)
  🟠 Jam & Sync:         ██████░░░░░░░░░░░░░░  18 docs (14%)
  🔵 Recharge:           ██░░░░░░░░░░░░░░░░░░   5 docs (4%)
  ⚫️ Done & Dusted:      ░░░░░░░░░░░░░░░░░░░░   0 docs (0%)

Recent Activity (7 days):
  🟢🟢🔴🔴🔴🟡🟠

Color Balance: 🔴 Heavy • Consider adding 🔵🟣

Mode Breakdown:
  - Most active: 🟢 Deep Field (42 docs)
  - Least active: 🔵 Recharge (5 docs)
  - Growing: 🔴 Waves Pumping (+8 this week)
```

## Options

- `--period <period>`: Activity window (7d, 30d, 90d, all)

## Interpretation

- **Too much 🔴**: You're over-committed. Add 🔵 or 🟣.
- **Too much 🟢**: Great focus, but check 🔴 for deadlines.
- **Low 🔵**: Burnout risk. Schedule recharge.
- **Low 🟣**: Not exploring. Feed curiosity.
- **Growing ⚫️**: Good! You're shipping work.

## Related Commands

- `/surf-report` - Today's recommendation
- `/rhythm weekly` - Patterns over time
- `/rebalance` - Specific suggestions
