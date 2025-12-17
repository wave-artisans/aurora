---
description: Extract tasks and actions from document
argument-hint: <document> [--add-tasks]
---

# Extract Actions Command

Pull tasks and action items from documents.

## Usage

```
/extract-actions <document> [--add-tasks]
```

## Description

The extract-actions command analyzes a document (typically meeting notes) and extracts:
- Action items
- Decisions made
- Deadlines mentioned
- Owners/assignees

## How It Works

1. **Parse Document**: Read the content
2. **Identify Actions**: Find TODO markers, assignments, action language
3. **Extract Details**: Owner, due date, context
4. **Format Output**: Structured list of actions
5. **Optionally Add**: Create tasks in tasks.json

## Signals Detected

- "Action:", "TODO:", "ACTION ITEM:"
- "@Name will..." or "Name to..."
- "by [date]", "due [date]", "deadline:"
- "Let's...", "We need to...", "Should..."
- Checkbox items: "- [ ]"

## Output

```
📋 Actions Extracted from: 2025-12-17_sync-alpha.md

Action Items:
  1. [ ] Review API design
     Owner: Alice
     Due: Dec 19
     Context: "Alice to review API design by Friday"

  2. [ ] Update documentation
     Owner: Bob
     Due: Dec 20
     Context: "Bob needs to update docs before release"

  3. [ ] Schedule client demo
     Owner: Unassigned
     Due: Next week
     Context: "We should schedule a demo"

Decisions:
  ✓ Use v2 API for new features
  ✓ Postpone mobile app to Q1

Add to tasks? Use: /extract-actions doc.md --add-tasks
```

## With --add-tasks

Automatically creates tasks in `Tasks/tasks.json`:
- Sets aurora-mode based on context
- Links to source document
- Adds extracted due dates

## Best For

- Meeting notes from Jam & Sync
- Email captures
- Project kickoff docs
- Any document with action items

## Related Commands

- `/task new` - Create individual tasks
- `/intake` - Full document processing
- `/ask` - Query for decisions/actions
