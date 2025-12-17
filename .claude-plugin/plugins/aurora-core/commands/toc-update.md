---
description: Regenerate table of contents files
argument-hint: [folder] [--all] [--dry-run]
---

# ToC Update Command

Regenerate table of contents files.

## Usage

```
/toc-update [folder] [--all] [--dry-run]
```

## Description

Regenerate TOC.md files based on current document structure. Keeps navigation in sync with actual content.

## Arguments

- `folder`: Specific folder to update (optional)

## Options

- `--all`: Update all TOC files (global + all mode folders)
- `--dry-run`: Preview changes without writing

## Scope

### Single Folder
```
/toc-update Deep-Field
```
Updates only `Deep-Field/TOC.md`

### All Folders
```
/toc-update --all
```
Updates:
- `TOC.md` (global)
- `Curiosity-Queue/TOC.md`
- `Deep-Field/TOC.md`
- `Waves-Pumping/TOC.md`
- `Quick-Ops/TOC.md`
- `Jam-Sync/TOC.md`
- `Recharge/TOC.md`
- `Done-Dusted/TOC.md`
- `Library/TOC.md`
- Any project subfolder TOCs

## Process

1. Scan target folder(s) for markdown files
2. Read MAGI front matter from each document
3. Extract title, description, updated date
4. Group by subfolder/project
5. Sort by date or alphabetically
6. Generate markdown table
7. Update TOC.md file
8. Update global TOC with folder summaries

## Output

```
📑 Updating Tables of Contents...

Deep-Field/TOC.md:
  Found: 12 documents, 2 projects
  Added: project-alpha-spec.md
  Updated: api-design.md (new date)
  ✓ Written

Global TOC.md:
  Updated Deep Field count: 12 docs
  ✓ Written

Summary:
  2 TOC files updated
  1 new document indexed
  1 date refreshed
```

## When to Run

- After bulk `/intake` operations
- After manual file organization
- After using `/move` or `/archive`
- Periodically to catch manual edits

## Related Commands

- `/validate --check toc` - Check TOC accuracy
- `/intake` - Auto-updates TOC on intake
