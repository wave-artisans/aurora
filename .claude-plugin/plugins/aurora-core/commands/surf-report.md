# Surf Report Command

Get your energy check and mode recommendation.

## Usage

```
/surf-report
```

## Description

The surf report analyzes your recent activity, document distribution, and patterns to suggest what mode you should be in right now.

Like checking the surf conditions before paddling out.

## Analysis Factors

1. **Recent Activity**: What modes have you been working in?
2. **Color Balance**: Distribution across all 7 modes
3. **Deadline Pressure**: Upcoming commitments (🔴 Waves Pumping)
4. **Energy Patterns**: Time of day, day of week
5. **Neglected Modes**: Areas that haven't seen activity
6. **Task Queue**: Pending items by mode

## Output

```
🏄 Surf Report - 2025-12-17

Current Conditions:
  🔴 Heavy commitment week (45% of activity)
  🟢 Some deep work scheduled
  🔵 Low recharge time

Energy Read:
  You've been paddling hard. Consider floating.

Recommendation:
  After your 3pm deadline, shift to 🔵 Recharge
  or 🟣 Curiosity Queue for balance.

Upcoming Waves:
  🔴 3 deadlines in next 48h
  🟠 2 collaboration sessions tomorrow

Quick Actions:
  /paddle     → Enter focus mode
  /float      → Shift to rest
  /catch-wave → Check deadlines
```

## Philosophy

The surf report embodies Aurora's core principle:

> Know when to paddle hard, when to ride, and when to float.

It doesn't tell you what to DO - it tells you what ENERGY to bring.

## Related Commands

- `/aurora-status` - Color balance visualization
- `/rhythm weekly` - Pattern over time
- `/rebalance` - Detailed recommendations
