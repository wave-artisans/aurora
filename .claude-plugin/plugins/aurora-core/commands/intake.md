---
description: Process documents from Inbox folder
argument-hint: [filename] [--dry-run] [--force]
---

# Intake Command

Process documents from the Inbox folder into the Aurora system.

## Usage

```
/intake [filename] [--dry-run] [--force]
```

## Description

The intake command processes documents in the `Inbox/` folder:

1. **Document Recognition**: Detect file type and format
2. **Content Analysis**: Extract key topics, entities, and context
3. **MAGI Generation**: Create YAML front matter with:
   - Unique doc-id (UUID v4)
   - Title (from content or filename)
   - Description (AI-generated summary)
   - Tags (based on content analysis)
   - Timestamps
4. **Aurora Mode Classification**: Determine appropriate mode folder
5. **Relationship Detection**: Find connections to existing documents
6. **Placement**: Move to target folder and update indexes

## Workflow

### For Markdown Files

1. Parse existing content
2. Check for existing MAGI front matter
3. If no MAGI: Generate complete front matter
4. If has MAGI: Validate and update if needed
5. Classify into Aurora mode
6. Move to appropriate folder
7. Update `.magi/index.json`
8. Update folder TOC

### For Binary Files (PDF, images, etc.)

1. Extract metadata and content where possible
2. Generate companion markdown file with:
   - MAGI front matter
   - AI-generated description
   - Asset reference
3. Move binary to `{mode-folder}/assets/`
4. Place companion .md in mode folder
5. Update indexes

## Classification Logic

1. **Explore (🟣)**: Research, learning, experiments, "what if"
2. **Focus (🟢)**: Deep work, creative projects, coding, writing
3. **Commitments (🔴)**: Deadlines, client work, obligations
4. **Ops (🟡)**: Admin, finance, maintenance, systems
5. **Collab (🟠)**: Meeting notes, shared docs, reviews
6. **Life (🔵)**: Personal, health, leisure, non-work
7. **Archive (⚫️)**: Completed items

## Options

- `filename`: Process specific file only
- `--dry-run`: Preview what would happen without making changes
- `--force`: Re-process even if file has MAGI front matter

## Examples

```
/intake                          # Process all Inbox files
/intake meeting-notes.md         # Process specific file
/intake --dry-run                # Preview only
/intake document.pdf --force     # Force re-process
```

## Output

For each processed file:
- Source path
- Detected type
- Generated/updated MAGI fields
- Aurora mode classification
- Target destination
- Related documents found
