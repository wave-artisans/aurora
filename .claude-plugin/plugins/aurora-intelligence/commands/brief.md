# Brief Command

Generate an executive brief on any topic.

## Usage

```
/brief <topic> [--length short|medium|long] [--audience <audience>]
```

## Description

Creates a concise, executive-style summary on any topic by searching and synthesizing from your Aurora knowledge base. Perfect for quick preparation or sharing.

## Arguments

- `topic`: The subject to brief on (project name, concept, client, etc.)

## Options

- `--length`: Brief length (short: 1 paragraph, medium: 1 page, long: 2-3 pages)
- `--audience`: Target reader (exec, technical, client, team)

## Process

1. Search knowledge base for topic-related documents
2. Identify key documents across all modes
3. Extract core information:
   - What it is
   - Current status
   - Key decisions made
   - Outstanding items
   - Recent activity
4. Synthesize into clear, scannable format
5. Add source citations

## Output

```
📋 Executive Brief: Project Alpha

Generated: 2025-12-17
Sources: 8 documents across 4 modes

---

## Overview

Project Alpha is a client API redesign initiative started
in Q4 2025. Currently in build phase with 70% completion.

## Status

🟢 ON TRACK

- Design phase completed Dec 1
- Core API implementation done
- Authentication module in progress
- Testing scheduled for Dec 20

## Key Decisions

1. Using OAuth 2.0 for authentication (Dec 5)
2. PostgreSQL over MongoDB for data layer (Nov 28)
3. Microservices architecture approved (Nov 20)

## Outstanding Items

- [ ] Complete auth module (due Dec 18)
- [ ] Load testing setup
- [ ] Client documentation

## Recent Activity

- API design spec finalized (Dec 15)
- Team sync held (Dec 14)
- Performance review completed (Dec 12)

---

Sources:
- [[Deep-Field/project-alpha/spec|Project Spec]]
- [[Jam-Sync/alpha-meetings/|Meeting Notes]]
- [[Waves-Pumping/alpha-deadlines|Deadline Tracker]]
```

## Examples

```
/brief "Project Alpha"
/brief "Q4 achievements" --length long
/brief "API architecture" --audience technical
/brief "Acme Corp" --audience client
```

## Related Commands

- `/ask` - Interactive Q&A
- `/report` - Detailed multi-source report
- `/summarize` - Summarize specific documents
