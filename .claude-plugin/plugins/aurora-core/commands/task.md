---
description: Manage tasks in Aurora task system
argument-hint: <action> [options]
---

# Task Command

Manage tasks in the Aurora task system.

## Usage

```
/task <action> [options]
```

## Actions

### Create Task
```
/task new "Task title" [--mode <mode>] [--due <date>] [--priority <p1-p4>]
```

### List Tasks
```
/task list [--mode <mode>] [--status <status>] [--due <filter>]
```

### Complete Task
```
/task complete <task-id>
```

### Update Task
```
/task update <task-id> [--title] [--mode] [--due] [--priority]
```

### Link Document
```
/task link <task-id> <doc-id>
```

## Examples

```
/task new "Review client proposal" --mode commitments --due tomorrow
/task list --mode focus
/task list --due today
/task complete T-000001
/task link T-000001 proposal-doc-id
```

## Task Structure

```json
{
  "id": "T-000001",
  "title": "Task title",
  "aurora-mode": "commitments",
  "status": "pending",
  "priority": "p2",
  "due": "2025-12-20",
  "created": "2025-12-17",
  "tags": ["client"],
  "related-docs": ["doc-id-1"]
}
```

## Status Values
- `pending` - Not started
- `active` - In progress
- `done` - Completed
- `cancelled` - Cancelled

## Priority Levels
- `p1` - Critical
- `p2` - High
- `p3` - Medium
- `p4` - Low

## Integration

Tasks integrate with Aurora modes:
- Mode changes can trigger task suggestions
- `/extract-actions` creates tasks from meeting notes
- Completed tasks can trigger document archival
