# Move Command

Move a document between Aurora modes.

## Usage

```
/move <document> <target-mode> [--with-assets]
```

## Description

Move a document from its current Aurora mode folder to a different one. Updates MAGI front matter and indexes.

## Arguments

- `document`: Path or doc-id of the document to move
- `target-mode`: Destination mode (explore, focus, commitments, ops, collab, life, archive)

## Options

- `--with-assets`: Also move related assets from the source assets folder

## Process

1. Locate source document
2. Update `aurora-mode` in MAGI front matter
3. Update `updated` timestamp
4. Move file to target folder
5. Move assets if `--with-assets` specified
6. Update `.magi/index.json` with new path
7. Update source and target TOC.md files
8. Log mode transition

## Examples

```
/move project-alpha.md archive
/move 550e8400-uuid commitments
/move Deep-Field/old-project.md archive --with-assets
```

## Mode Values

| Mode | Folder | Emoji |
|------|--------|-------|
| explore | Curiosity-Queue | 🟣 |
| focus | Deep-Field | 🟢 |
| commitments | Waves-Pumping | 🔴 |
| ops | Quick-Ops | 🟡 |
| collab | Jam-Sync | 🟠 |
| life | Recharge | 🔵 |
| archive | Done-Dusted | ⚫️ |

## Output

```
📦 Moving document...

From: Deep-Field/project-alpha.md (🟢 Focus)
To:   Done-Dusted/project-alpha.md (⚫️ Archive)

Updates:
  ✓ aurora-mode: focus → archive
  ✓ updated: 2025-12-17
  ✓ File moved
  ✓ Index updated
  ✓ TOCs updated

Document archived successfully.
```

## Related Commands

- `/archive` - Shortcut for moving to Done-Dusted
- `/flow` - Move with transition tracking
- `/validate` - Check for mode mismatches
