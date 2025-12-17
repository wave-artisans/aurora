---
name: workflow-automation
description: Proactive workflow assistance and automation. Use when generating digests, extracting follow-up reminders, synthesizing project status, or detecting stale content.
---

# Workflow Automation Skill

Proactive assistance and workflow automation for the Aurora system.

## Purpose

This skill enables Claude to proactively assist with recurring workflows, generate reports, and automate routine knowledge management tasks.

## Capabilities

### 1. Daily Standup Generation

Generate morning activity summaries.

**Data Sources:**
- Documents modified yesterday
- Tasks completed/added
- Mode distribution of activity
- Upcoming deadlines (next 48h)

**Output Structure:**
```markdown
## Daily Standup - 2025-12-17

### Yesterday's Activity
- 🟢 Deep Field: 3 documents updated
- 🔴 Commitments: 2 tasks completed
- 🟠 Collab: 1 meeting captured

### Key Updates
- Project Alpha spec finalized
- Client proposal submitted

### Today's Focus
- 🔴 Review deadline: Client feedback by 3pm
- 🟢 Continue: Auth module implementation

### Blockers
- None identified
```

**Trigger:**
- Manual: `/digest daily`
- Scheduled: Could run automatically at 9am

### 2. Weekly Review Preparation

Prepare materials for weekly review sessions.

**Analysis Includes:**
- Color balance over the week
- Documents created/updated by mode
- Tasks completed vs added
- Meetings held
- Items archived
- Trends and patterns

**Output Structure:**
```markdown
## Weekly Review - Dec 11-17, 2025

### Color Balance
🔴🔴🟢🟢🟢🟡🟠

### Accomplishments
- ✅ Project Alpha: Milestone 2 complete
- ✅ Submitted 3 client deliverables
- ✅ Archived Q3 materials

### In Progress
- 🔄 API documentation (70%)
- 🔄 Test automation setup

### Challenges
- Timeline pressure on Alpha
- Waiting on external dependency

### Next Week Priority
1. Complete API docs
2. Begin integration testing
3. Client demo preparation
```

### 3. Stale Content Alerts

Proactively identify content needing attention.

**Alert Types:**
- Documents not updated in threshold period
- Referenced docs that no longer exist
- Tasks with passed due dates
- Mode imbalances sustained too long

**Alert Delivery:**
- Include in daily/weekly digests
- Flag during relevant commands
- Suggest actions

**Alert Format:**
```
⚠️ Stale Content Alert

3 documents need attention:
1. security-policy.md - 120 days old
2. team-directory.md - 90 days old
3. api-v1-spec.md - still referenced, may be outdated

Quick fix: /stale --fix
```

### 4. Follow-up Reminder Extraction

Extract and track follow-ups from content.

**Sources:**
- Meeting notes with action items
- Emails with commitments
- Documents with TODO markers

**Reminder Data:**
```yaml
reminders:
  - source: "2025-12-17_sync.md"
    action: "Follow up with client on feedback"
    owner: "self"
    due: "2025-12-20"
    created: "2025-12-17"
    status: "pending"
```

**Integration:**
- Add to Tasks/tasks.json
- Surface in daily digest
- Alert on due date

### 5. Project Status Synthesis

Aggregate status from scattered documents.

**Data Collection:**
```
1. Find all docs in project folder
2. Extract from meeting notes
3. Check task status
4. Find recent commits/changes
5. Identify blockers mentioned
```

**Synthesis Process:**
```
1. Determine overall status (on-track/at-risk/blocked)
2. Calculate completion percentage
3. List recent accomplishments
4. Identify current focus
5. Flag risks and blockers
```

**Output:**
```markdown
## Project Alpha Status

**Overall**: 🟢 On Track (70% complete)

### Recent Progress
- API design finalized
- Core implementation complete
- Auth module started

### Current Focus
- Authentication implementation
- Unit test coverage

### Risks
- ⚠️ Timeline tight for testing phase

### Next Milestone
- Dec 20: Begin integration testing
```

## Automation Patterns

### Scheduled Tasks

| Task | Frequency | Trigger |
|------|-----------|---------|
| Daily digest | Daily 9am | Automatic |
| Stale check | Weekly | Sunday |
| Balance check | Weekly | Friday |
| ToC update | On intake | After /intake |

### Event-Triggered

| Event | Action |
|-------|--------|
| Document archived | Update related ToCs |
| Task completed | Check for related tasks |
| Meeting notes added | Extract actions |
| Mode transition | Log in history |

### Proactive Suggestions

| Condition | Suggestion |
|-----------|------------|
| High 🔴, low 🔵 | Suggest recharge |
| No ⚫️ in 2 weeks | Suggest archiving |
| Stale reference docs | Suggest review |
| Empty inbox | Celebrate! |

## Integration Points

### Commands Using This Skill
- `/digest` - Periodic summaries
- `/stale` - Content freshness
- `/rebalance` - Balance suggestions
- `/extract-actions` - Action extraction

### Data Sources
- All MAGI index files
- Tasks/tasks.json
- Git commit history (optional)
- Document content

## Best Practices

### For Automation
1. Don't over-automate
2. Allow user control
3. Explain what happened
4. Provide undo options

### For Proactive Assistance
1. Suggest, don't mandate
2. Explain reasoning
3. Respect user preferences
4. Learn from feedback

### For Reminders
1. Avoid notification fatigue
2. Consolidate where possible
3. Prioritize by importance
4. Allow snoozing
