# Summarize Command

Create summaries at various levels of detail.

## Usage

```
/summarize <target> [--level <level>] [--format <format>]
```

## Description

Generates summaries of documents, folders, projects, or time periods at configurable levels of detail.

## Arguments

- `target`: What to summarize (document, folder, project, or period)

## Options

- `--level`: Detail level (oneliner, paragraph, page, full)
- `--format`: Output format (text, bullets, structured)

## Targets

### Single Document
```
/summarize project-spec.md
```

### Folder/Mode
```
/summarize Deep-Field/
/summarize mode:commitments
```

### Project
```
/summarize project:alpha
```

### Time Period
```
/summarize period:this-week
/summarize period:december
/summarize period:q4
```

## Levels

### Oneliner
Single sentence capturing the essence:
```
Project Alpha is an API redesign for Acme Corp, currently 70% complete and on track for Dec 30 delivery.
```

### Paragraph
3-5 sentences with key details:
```
Project Alpha is a strategic API redesign initiative for Acme Corp.
The project moved from design to build phase in November, with core
implementation now 70% complete. Key decisions include OAuth 2.0 for
authentication and PostgreSQL for data storage. The team is on track
for the December 30 delivery date, with integration testing scheduled
to begin December 20.
```

### Page
One page with sections:
```
## Overview
[Paragraph summary]

## Current Status
[Status details]

## Key Points
- Point 1
- Point 2
- Point 3

## Next Steps
[Upcoming actions]
```

### Full
Comprehensive summary preserving most information in condensed form.

## Output Examples

```
📝 Summary: Deep-Field/ (Focus Mode)

Level: Paragraph
Scope: 42 documents, 5 projects

---

The Deep Field contains your core creative and technical work.
Currently, Project Alpha dominates with 18 documents focused on
API design and implementation. Project Beta is in early stages
with 6 documents. The remaining work consists of technical
documentation, research notes, and coding standards. Recent
activity (last 7 days) has focused on Alpha's API specification
and authentication module.

Key themes: API design, authentication, client integration
Active projects: Alpha (active), Beta (starting), Gamma (paused)
```

## Period Summaries

```
/summarize period:this-week
```

```
📅 Week Summary: Dec 11-17, 2025

Activity by Mode:
  🟢 Focus: 12 document updates
  🔴 Commitments: 3 deadlines met
  🟠 Collab: 2 meetings captured

Highlights:
  - Project Alpha milestone reached
  - Client proposal submitted
  - New research thread started

Key Decisions:
  - OAuth 2.0 selected for auth
  - Q1 roadmap approved

Documents Created: 5
Documents Updated: 18
Tasks Completed: 8
```

## Related Commands

- `/brief` - Executive summary on topic
- `/digest` - Periodic activity digest
- `/report` - Detailed report generation
