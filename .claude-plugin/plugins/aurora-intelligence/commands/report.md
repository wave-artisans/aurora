# Report Command

Generate comprehensive reports from multiple sources.

## Usage

```
/report <topic> [--template <type>] [--output <path>]
```

## Description

Creates detailed, structured reports by gathering and synthesizing information from across your Aurora knowledge base. More comprehensive than `/brief`.

## Arguments

- `topic`: Report subject

## Options

- `--template`: Report type (status, review, analysis, comparison, retrospective)
- `--output`: Save report to specific path

## Templates

### Status Report
```
/report "Project Alpha" --template status
```
- Current state
- Progress vs plan
- Blockers
- Next steps
- Timeline

### Review Report
```
/report "Q4 2025" --template review
```
- Period summary
- Achievements
- Challenges
- Metrics
- Lessons learned

### Analysis Report
```
/report "AI Governance" --template analysis
```
- Background
- Current landscape
- Key findings
- Implications
- Recommendations

### Comparison Report
```
/report "API Options" --template comparison
```
- Options overview
- Criteria
- Comparison matrix
- Trade-offs
- Recommendation

### Retrospective Report
```
/report "Campaign Launch" --template retrospective
```
- What happened
- What went well
- What didn't
- Action items
- Takeaways

## Process

1. Search knowledge base for all related content
2. Identify documents by mode and relevance
3. Extract structured information per template
4. Synthesize into coherent narrative
5. Generate tables, timelines where appropriate
6. Add citations and source links
7. Format for readability

## Output Example

```
📊 Status Report: Project Alpha
Generated: 2025-12-17
Period: Q4 2025

---

## Executive Summary

Project Alpha is a strategic API redesign for Acme Corp,
currently at 70% completion with on-track delivery for
Dec 30, 2025.

## Progress Overview

| Phase | Status | Completion |
|-------|--------|------------|
| Discovery | ✅ Complete | 100% |
| Design | ✅ Complete | 100% |
| Build | 🔄 In Progress | 70% |
| Test | ⏳ Pending | 0% |
| Deploy | ⏳ Pending | 0% |

## Key Accomplishments This Period

1. Core API framework implemented
2. Database schema finalized
3. CI/CD pipeline established

## Current Blockers

| Blocker | Owner | Status |
|---------|-------|--------|
| Auth provider selection | Alice | Resolving |

## Timeline

[Timeline visualization]

## Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Scope creep | Medium | High | Weekly scope review |

## Next Steps

1. Complete authentication module (Dec 18)
2. Begin integration testing (Dec 20)
3. Client demo preparation (Dec 23)

---

Sources: 12 documents
[[See full source list|#sources]]
```

## Saving Reports

```
/report "Project Alpha" --output Deep-Field/project-alpha/status-2025-12.md
```

Creates a dated report document with MAGI front matter.

## Related Commands

- `/brief` - Quick executive summary
- `/ask` - Interactive Q&A
- `/digest` - Periodic activity summary
