# Simplify Command

Create an accessible version of complex content.

## Usage

```
/simplify <document> [--level <level>] [--output <path>]
```

## Description

Takes a complex document and creates a simpler, more accessible version while preserving key information.

## Arguments

- `document`: Path or doc-id to simplify

## Options

- `--level`: Simplification level (light, moderate, heavy)
- `--output`: Save simplified version to path

## Levels

### Light
- Shorter sentences
- Reduced jargon (with explanations)
- Better structure
- ~80% of original detail

### Moderate
- Plain language throughout
- Key points emphasized
- Examples simplified
- ~50% of original detail

### Heavy
- Executive summary style
- Only essential information
- Maximum accessibility
- ~25% of original detail

## Process

1. Analyze document complexity
2. Identify jargon and technical terms
3. Find core concepts vs supporting details
4. Restructure for clarity
5. Simplify language
6. Add explanations where needed
7. Preserve accuracy

## Output

```
📖 Simplification: architecture-spec.md

Original:
  Words: 2,450
  Reading level: Graduate
  Technical terms: 47

Simplified (moderate):
  Words: 1,100
  Reading level: High School
  Technical terms: 12 (with explanations)

---

## Simplified Version

### What This System Does

[Simplified explanation...]

### How It Works

Instead of:
"The microservices architecture employs an event-driven
paradigm with eventual consistency guarantees..."

Now:
"The system is built from small, independent parts that
communicate by sending messages to each other. Changes
may take a moment to appear everywhere, but they will
eventually be consistent."

### Key Components

[Simplified list with plain-language descriptions...]

---

Glossary added:
  - API: A way for programs to talk to each other
  - Microservice: A small, focused program
  - [etc...]
```

## Saving Simplified Versions

```
/simplify architecture-spec.md --output architecture-simple.md
```

Creates a new document with:
- Reference to original
- Simplified content
- Glossary of terms

## Use Cases

1. **Onboarding**: Simplify technical docs for new team members
2. **Client Communication**: Make specs accessible to non-technical stakeholders
3. **Executive Summaries**: Distill complex analyses
4. **Cross-team Sharing**: Bridge technical and non-technical teams

## Related Commands

- `/translate` - Change tone/style without simplifying
- `/expand` - Add detail to thin content
- `/brief` - Generate summary from multiple docs
