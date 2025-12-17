# Flow Command

Move a document between modes with transition tracking.

## Usage

```
/flow <document> <target-mode> [--reason <reason>]
```

## Description

Like `/move`, but specifically tracks the mode transition in the document's history. Useful for understanding how projects evolve through the Aurora lifecycle.

## The Natural Flow

Projects typically flow through modes:
```
🟣 Explore → 🟢 Focus → 🔴 Commitments → ⚫️ Archive
```

But life isn't linear. Documents might:
- Return from 🔴 to 🟢 for more work
- Jump from 🟣 directly to 🔴 when urgency hits
- Move to 🔵 for a break

## Arguments

- `document`: Path or doc-id
- `target-mode`: Destination mode

## Options

- `--reason <text>`: Why the transition is happening

## Process

1. Locate document
2. Record current mode as `previous-mode`
3. Update `aurora-mode` to target
4. Add transition to `mode-history` array:
   ```yaml
   mode-history:
     - from: explore
       to: focus
       date: 2025-12-17
       reason: "Ready to build"
   ```
5. Move file to target folder
6. Update indexes

## Examples

```
/flow ai-research.md focus --reason "Moving from research to implementation"
/flow client-project.md commitments --reason "Deadline confirmed"
/flow burned-out-project.md life --reason "Taking a break"
```

## Output

```
🌊 Flowing...

Document: ai-research.md
Transition: 🟣 Explore → 🟢 Focus
Reason: "Moving from research to implementation"

Mode History:
  1. Created in 🟣 (2025-12-01)
  2. → 🟢 Focus (2025-12-17) "Moving from research to implementation"

Updates:
  ✓ aurora-mode updated
  ✓ mode-history recorded
  ✓ File moved to Deep-Field/
  ✓ Indexes updated

The wave is building. Paddle into it.
```

## Viewing Flow History

```
/retrieve doc-id --history
```

Shows the complete mode journey of a document.

## Related Commands

- `/move` - Simple move without history
- `/archive` - Move to Done & Dusted
- `/trends` - Analyze flow patterns
