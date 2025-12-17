---
name: aurora-rhythm
description: Mode intelligence and energy pattern management. Use when analyzing color balance, detecting burnout patterns, generating surf reports, or managing mode transitions.
---

# Aurora Rhythm Skill

Mode intelligence and energy pattern management for the Aurora system.

## Purpose

This skill enables Claude to understand and manage Aurora mode patterns, detect energy imbalances, and provide rhythm-based recommendations.

## Capabilities

### 1. Color Balance Analysis

Analyze distribution of documents and activity across all 7 Aurora modes.

**Implementation:**
```
1. Query .magi/index.json for all documents
2. Count by aurora-mode field
3. Calculate percentages
4. Compare against healthy targets
5. Identify imbalances
```

**Healthy Targets (flexible):**
- 🟣 Explore: 5-15%
- 🟢 Focus: 25-35%
- 🔴 Commitments: 15-25%
- 🟡 Ops: 10-15%
- 🟠 Collab: 10-20%
- 🔵 Life: 15-25%
- ⚫️ Archive: Growing

### 2. Mode Transition Tracking

Track how documents flow between modes over time.

**Data Structure:**
```yaml
mode-history:
  - from: explore
    to: focus
    date: 2025-12-17
    reason: "Moving to implementation"
```

**Pattern Detection:**
- Normal flow: 🟣→🟢→🔴→⚫️
- Regression: 🔴→🟢 (back to focus)
- Stall: Document stuck in one mode too long
- Skip: Jumping from 🟣 directly to 🔴

### 3. Energy Pattern Recognition

Detect patterns that indicate burnout or imbalance.

**Warning Signs:**
- High 🔴 sustained (>40% for 2+ weeks)
- No 🔵 activity (0% for 1+ week)
- No 🟣 activity (0% for 2+ weeks)
- Declining ⚫️ (not shipping/completing)
- Increasing 🔴 without completion

**Healthy Signs:**
- Regular 🔵 entries
- Steady ⚫️ growth (completing work)
- Balanced 🟢 and 🔴
- Active 🟣 exploration

### 4. Surf Report Generation

Generate daily energy recommendations.

**Algorithm:**
```
1. Analyze last 7 days of mode activity
2. Check today's calendar/deadline data if available
3. Identify dominant modes
4. Detect neglected modes
5. Consider time of day/week
6. Generate natural language recommendation
```

**Output Format:**
```
Your week shows [dominant] energy.
Today consider [suggested mode].
[Specific reasoning].
```

### 5. Rebalance Suggestions

Provide actionable recommendations for improving balance.

**Analysis Steps:**
```
1. Calculate current distribution
2. Identify modes above/below target
3. Check for warning patterns
4. Generate specific actions
5. Prioritize by urgency
```

**Recommendation Types:**
- Add mode: "Consider adding 🔵 Recharge time"
- Reduce mode: "Heavy 🔴 - can any deadlines shift?"
- Archive prompt: "5 items ready to archive"
- Explore prompt: "Feed your curiosity with new input"

### 6. Natural Flow Tracking

Monitor the lifecycle of documents through modes.

**Lifecycle States:**
```
INCEPTION: Created in any mode
EXPLORATION: In 🟣 Curiosity Queue
DEVELOPMENT: In 🟢 Deep Field
COMMITMENT: In 🔴 Waves Pumping
COLLABORATION: In 🟠 Jam & Sync
OPERATIONAL: In 🟡 Quick Ops
COMPLETION: Moved to ⚫️ Done & Dusted
```

**Metrics:**
- Average time in each mode
- Completion rate (% reaching ⚫️)
- Abandonment rate (deleted or stale)
- Flow velocity (how fast things move)

## Integration Points

### Commands Using This Skill
- `/surf-report` - Daily energy check
- `/aurora-status` - Current balance
- `/rhythm` - Pattern visualization
- `/rebalance` - Balance recommendations
- `/flow` - Mode transitions
- `/paddle`, `/float`, `/catch-wave` - Mode-specific views

### Data Sources
- `.magi/index.json` - Document metadata
- `Tasks/tasks.json` - Task integration
- Document `updated` timestamps
- Document `mode-history` arrays

## Best Practices

### For Mode Assignment
1. Ask "What energy does this require?" not "How urgent is it?"
2. Consider the natural flow
3. Don't force documents into modes
4. Allow regression when needed

### For Balance
1. Check weekly, not daily (rhythm, not rigidity)
2. Some weeks are naturally heavy in one mode
3. Recovery follows intensity
4. Exploration prevents stagnation

### For Recommendations
1. Suggest, don't mandate
2. Explain the reasoning
3. Offer specific actions
4. Respect user autonomy

## Example Usage

```
// Analyze current balance
const balance = analyzeColorBalance(index.documents);
if (balance.commitments > 0.4 && balance.life < 0.1) {
  warn("Burnout risk: High commitments, low recharge");
  suggest("Add 🔵 time or defer a deadline");
}

// Generate surf report
const activity = getRecentActivity(7); // days
const dominant = findDominantMode(activity);
const neglected = findNeglectedModes(activity);
return generateSurfReport(dominant, neglected, today);
```
