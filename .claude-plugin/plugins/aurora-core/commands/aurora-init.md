# Aurora System Initialization

Initialize or verify the Aurora Knowledge Management System structure.

## Usage

```
/aurora-init [--verify] [--fix]
```

## Description

This command initializes the complete Aurora file structure or verifies an existing installation.

## Behavior

### Default (Initialize)

1. Create all Aurora mode folders:
   - `Inbox/` with `assets/`
   - `Tasks/` with `assets/`
   - `Curiosity-Queue/` (🟣 Explore)
   - `Deep-Field/` (🟢 Focus)
   - `Waves-Pumping/` (🔴 Commitments)
   - `Quick-Ops/` (🟡 Ops)
   - `Jam-Sync/` (🟠 Collab)
   - `Recharge/` (🔵 Life)
   - `Done-Dusted/` (⚫️ Archive)
   - `Library/` with `_templates/`

2. Create `.magi/` metadata folder:
   - `index.json` - Document index
   - `relationships.json` - Document graph
   - `tags.json` - Tag taxonomy

3. Create core files:
   - `README.md` - System entry point
   - `TOC.md` - Global navigation
   - `CONVENTIONS.md` - Standards reference
   - `.gitignore` - Git configuration

4. Create folder-level TOC.md in each mode folder

5. Create MAGI templates in `Library/_templates/`:
   - `_template_standard.md`
   - `_template_project.md`
   - `_template_meeting.md`
   - `_template_asset-meta.md`

6. Initialize `Tasks/tasks.json`

### With --verify

Check existing structure for:
- Missing folders
- Missing .gitkeep files
- Missing TOC files
- Missing metadata files
- Missing templates

Report any issues found.

### With --fix

Verify and automatically create any missing components.

## Example

```
/aurora-init          # Full initialization
/aurora-init --verify # Check structure
/aurora-init --fix    # Fix missing components
```

## Notes

- Safe to run multiple times
- Does not overwrite existing files
- Creates .gitkeep files in empty directories for Git tracking
