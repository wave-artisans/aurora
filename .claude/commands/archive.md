# Archive Command

Move a document to Done & Dusted.

## Usage

```
/archive <document> [--with-assets] [--note <completion-note>]
```

## Description

Shortcut for moving a document to the ⚫️ Done & Dusted archive. Marks work as complete and worth preserving.

## Arguments

- `document`: Path or doc-id of the document to archive

## Options

- `--with-assets`: Also move related assets
- `--note <text>`: Add a completion note to the document

## Process

1. Locate document
2. Update MAGI front matter:
   - `aurora-mode: archive`
   - `updated: <now>`
   - Add `archived: <date>` field
   - Add `completion-note` if provided
3. Move to `Done-Dusted/` (organized by year or project)
4. Update indexes and TOCs
5. Check for related tasks and mark complete
6. Log the archival

## Examples

```
/archive project-alpha-spec.md
/archive invoice-batch-dec.md --note "Q4 invoicing complete"
/archive Deep-Field/campaign/ --with-assets
```

## Output

```
⚫️ Archiving...

Document: project-alpha-spec.md
From: Deep-Field/project-alpha/
To: Done-Dusted/2025/project-alpha/

Updates:
  ✓ aurora-mode: focus → archive
  ✓ archived: 2025-12-17
  ✓ completion-note: "Shipped to production"
  ✓ Related tasks marked complete (2)
  ✓ Indexes updated

🎉 Project Alpha is Done & Dusted!

The wave has been ridden. Time for the next one.
```

## Philosophy

Done & Dusted is the echo - work worth preserving. Archive when:
- A project ships
- A client engagement ends
- A goal is achieved
- Something is complete and valuable

Don't archive:
- Abandoned work (delete instead)
- Temporary notes (delete)
- Superseded docs (use `/move` with supersedes relationship)

## Related Commands

- `/move` - Move to any mode
- `/flow` - Track mode transitions
- `/retrieve mode:archive` - Search archives
