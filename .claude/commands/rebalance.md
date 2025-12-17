# Rebalance Command

Get AI recommendations for mode balance.

## Usage

```
/rebalance
```

## Description

Analyzes your current Aurora mode distribution and provides specific, actionable recommendations to improve balance and prevent burnout.

## Analysis Factors

1. **Color Distribution**: How documents are spread across modes
2. **Recent Activity**: Where you've been spending energy
3. **Neglected Modes**: Areas that haven't seen attention
4. **Deadline Density**: Commitment concentration
5. **Recovery Ratio**: Life mode vs work modes
6. **Exploration Health**: Curiosity queue activity

## Output

```
⚖️ Aurora Rebalance Analysis

Current State:
  🔴 Commitments: 45% ████████████████░░░░ HIGH
  🟢 Focus:       25% ██████████░░░░░░░░░░ GOOD
  🟡 Ops:         15% ██████░░░░░░░░░░░░░░ NORMAL
  🟠 Collab:      10% ████░░░░░░░░░░░░░░░░ NORMAL
  🔵 Life:         3% █░░░░░░░░░░░░░░░░░░░ LOW ⚠️
  🟣 Explore:      2% █░░░░░░░░░░░░░░░░░░░ LOW ⚠️
  ⚫️ Archive:      0% ░░░░░░░░░░░░░░░░░░░░ STALE

Diagnosis:
  🚨 Burnout Risk: HIGH
  - Heavy commitment load (45%)
  - Minimal life/recharge (3%)
  - No recent archiving (shipping)

Recommendations:

1. URGENT: Add 🔵 Recharge
   You haven't logged life items in 2 weeks.
   → Schedule non-work time this week
   → Use /float to surface recharge items

2. Archive Completed Work
   5 items in Waves-Pumping are past deadline.
   → Use /archive to move completed items
   → Celebrate what you've shipped

3. Feed Your Curiosity
   Explore mode is starving (2%).
   → Spend 30 min on something interesting
   → Add to Curiosity-Queue without agenda

4. Spread Commitments
   3 deadlines cluster on Friday.
   → Consider renegotiating one deadline
   → Front-load work earlier in week

Suggested Actions:
  /float              # Surface life items
  /archive            # Clear completed work
  /catch-wave         # Review commitment spread
  /paddle             # Focus on deep work
```

## Balance Targets

Healthy distribution (flexible, not rigid):
- 🔴 Commitments: 15-25%
- 🟢 Focus: 25-35%
- 🟡 Ops: 10-15%
- 🟠 Collab: 10-20%
- 🔵 Life: 15-25%
- 🟣 Explore: 5-15%
- ⚫️ Archive: Growing (you're shipping!)

## Philosophy

Aurora is about resonance, not productivity metrics. The rebalance command helps you:
- Recognize patterns before burnout
- Remember that life is part of work
- Keep curiosity alive
- Celebrate completion

## Related Commands

- `/surf-report` - Today's quick check
- `/aurora-status` - Current distribution
- `/rhythm weekly` - Pattern over time
