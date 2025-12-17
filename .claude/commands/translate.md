# Translate Command

Rewrite content for a different audience or style.

## Usage

```
/translate <document> <target-style> [--output <path>]
```

## Description

Takes a document and rewrites it for a different audience, maintaining the same information but changing tone, structure, and vocabulary.

## Arguments

- `document`: Path or doc-id to translate
- `target-style`: Target audience/style

## Target Styles

### Audience-Based
- `exec`: Executive summary style
- `technical`: Developer/engineer focused
- `client`: External client communication
- `team`: Internal team update
- `public`: Blog/public announcement

### Tone-Based
- `formal`: Professional, structured
- `casual`: Conversational, approachable
- `urgent`: Action-oriented, direct
- `educational`: Teaching, explanatory

## Examples

```
/translate tech-spec.md exec
/translate meeting-notes.md client
/translate internal-update.md public
/translate formal-report.md casual
```

## Output

```
🔄 Style Translation: tech-spec.md → exec

Original Style:
  Audience: Technical
  Tone: Detailed, precise
  Length: 2,500 words

Translated Style:
  Audience: Executive
  Tone: Strategic, outcome-focused
  Length: 800 words

---

## Executive Version

### Strategic Summary

[Translated content focused on business impact...]

### Key Decisions Required

[Action items framed for executive decision-making...]

### Timeline & Resources

[High-level view without technical details...]

### Risks & Mitigations

[Business risk framing...]

---

Changes Made:
  - Removed implementation details
  - Added business impact framing
  - Condensed technical sections
  - Added decision points
  - Included resource implications
```

## Translation Matrix

| From → To | Focus Change |
|-----------|--------------|
| Tech → Exec | How → Why + Business Impact |
| Internal → Client | Process → Value Delivered |
| Formal → Casual | Structure → Story |
| Detail → Summary | Comprehensive → Key Points |

## Saving Translations

```
/translate spec.md exec --output spec-executive.md
```

Creates a new document with:
- MAGI front matter
- Reference to original
- Translated content
- Note on target audience

## Use Cases

1. **Stakeholder Communication**: Same info, right framing
2. **Documentation Variants**: Tech docs → User guides
3. **Meeting Prep**: Internal notes → Presentation
4. **Announcement Drafts**: Internal → External messaging

## Related Commands

- `/simplify` - Reduce complexity
- `/brief` - Generate summaries
- `/report` - Formal report generation
