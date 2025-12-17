# Report Factory Skill

Document generation and multi-source synthesis for the Aurora system.

## Purpose

This skill enables Claude to generate comprehensive documents by combining information from multiple sources in the knowledge base.

## Capabilities

### 1. Multi-Source Report Generation

Create reports by synthesizing from multiple documents.

**Report Types:**
- Status reports
- Review reports
- Analysis reports
- Comparison reports
- Retrospective reports

**Generation Process:**
```
1. Identify report type and requirements
2. Search for relevant source documents
3. Extract structured information
4. Organize by report template
5. Synthesize narrative
6. Add citations
7. Format for output
```

**Template Structure:**
```markdown
---
doc-id: generated-uuid
title: Report Title
description: Generated report
aurora-mode: focus
tags: [report, generated]
created: 2025-12-17
updated: 2025-12-17
generated-from:
  - source-doc-1
  - source-doc-2
---

# Report Title

## Executive Summary
[Synthesized overview]

## [Section 1]
[Content with citations]

## [Section 2]
[Content with citations]

## Sources
[List of source documents]
```

### 2. Presentation Generation

Create presentation-ready content from knowledge base.

**Output Format:**
```markdown
# Presentation: Project Alpha Overview

---

## Slide 1: Title
**Project Alpha**
API Redesign for Acme Corp
December 2025

---

## Slide 2: Objective
- Modernize API architecture
- Improve security
- Enable scalability

---

## Slide 3: Progress
[Visual progress representation]

---

## Slide 4: Key Decisions
| Decision | Rationale |
|----------|-----------|
| OAuth 2.0 | Security |
| PostgreSQL | Scale |

---

## Slide 5: Timeline
[Milestone timeline]

---

## Slide 6: Next Steps
1. Complete auth module
2. Integration testing
3. Client demo

---

## Speaker Notes
[Detailed notes for each slide]
```

### 3. Onboarding Doc Creation

Generate onboarding materials from existing content.

**Source Analysis:**
```
1. Scan Library/ for reference docs
2. Find project READMEs
3. Identify process documentation
4. Extract team/role information
5. Collect tool/tech documentation
```

**Onboarding Structure:**
```markdown
# Welcome to [Project/Team]

## Getting Started
[Synthesized from various docs]

## Key Systems
[From technical docs]

## Important Processes
[From ops docs]

## Key Contacts
[Extracted from team docs]

## Essential Reading
[Prioritized doc list]

## First Week Checklist
[Generated from common patterns]
```

### 4. FAQ Generation

Build FAQ from common questions in documents.

**Detection Methods:**
```
1. Find question patterns in docs:
   - "Q:", "Question:", "FAQ:"
   - Headers ending in "?"
   - "How do I...", "What is..."
2. Find answers in same docs
3. Deduplicate similar questions
4. Categorize by topic
5. Format as FAQ
```

**FAQ Structure:**
```markdown
# Frequently Asked Questions

## General

### What is Project Alpha?
[Answer synthesized from overview docs]

### Who is responsible for what?
[Answer from team docs]

## Technical

### How does authentication work?
[Answer from technical docs]

### What database do we use?
[Answer from architecture docs]

## Process

### How do I submit a change?
[Answer from process docs]
```

### 5. Executive Summary Generation

Create executive-level documents from detailed content.

**Transformation Rules:**
```
1. Remove implementation details
2. Focus on outcomes and impact
3. Add business context
4. Include key metrics
5. Highlight decisions needed
6. Keep under 2 pages
```

**Executive Structure:**
```markdown
# Executive Summary: [Topic]

## Situation
[Brief context]

## Key Points
- [High-level point 1]
- [High-level point 2]
- [High-level point 3]

## Impact
[Business implications]

## Recommendations
1. [Action 1]
2. [Action 2]

## Timeline
[High-level milestones]

## Resources Required
[Budget/people/time overview]
```

## Integration Points

### Commands Using This Skill
- `/report` - Report generation
- `/brief` - Executive summaries
- `/ask` - When creating documents

### Output Options
- Display in terminal
- Save to file with MAGI
- Both

### Source Tracking
Generated documents include:
- List of source documents
- Generation timestamp
- Query/parameters used

## Templates

### Status Report Template
```
# Status Report: [Subject]
Generated: [Date]
Period: [Date Range]

## Executive Summary

## Progress
### Completed
### In Progress
### Blocked

## Metrics
| Metric | Target | Actual |
|--------|--------|--------|

## Risks

## Next Period

## Sources
```

### Retrospective Template
```
# Retrospective: [Subject]
Generated: [Date]
Period: [Date Range]

## What Happened

## What Went Well
-
-

## What Didn't Go Well
-
-

## Lessons Learned

## Action Items

## Sources
```

## Best Practices

### For Report Generation
1. Always cite sources
2. Maintain factual accuracy
3. Preserve key details
4. Flag synthesized content
5. Include generation metadata

### For Presentation Creation
1. One idea per slide
2. Use visuals where possible
3. Include speaker notes
4. Keep text minimal
5. Ensure logical flow

### For FAQ Building
1. Use actual questions
2. Keep answers concise
3. Link to detailed docs
4. Update regularly
5. Categorize well
