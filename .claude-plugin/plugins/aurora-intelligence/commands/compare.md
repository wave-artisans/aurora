# Compare Command

Analyze differences between documents.

## Usage

```
/compare <doc1> <doc2> [--aspect <aspect>]
```

## Description

Compares two documents to identify differences, conflicts, evolution, or complementary information.

## Arguments

- `doc1`: First document (path or doc-id)
- `doc2`: Second document (path or doc-id)

## Options

- `--aspect`: Focus comparison on specific aspect (content, structure, decisions, timeline)

## Comparison Types

### Version Comparison
Compare two versions of the same document:
```
/compare spec-v1.md spec-v2.md
```

### Alternative Comparison
Compare different approaches:
```
/compare option-a.md option-b.md
```

### Evolution Comparison
Compare early vs late project docs:
```
/compare kickoff.md final-report.md
```

## Output

```
🔍 Document Comparison

Documents:
  A: spec-v1.md (created: 2025-11-15)
  B: spec-v2.md (created: 2025-12-10)

## Summary

These are versions of the same specification.
V2 represents significant evolution with 3 major changes.

## Key Differences

| Aspect | Document A (v1) | Document B (v2) |
|--------|-----------------|-----------------|
| Auth method | Session-based | OAuth 2.0 |
| Database | MongoDB | PostgreSQL |
| Architecture | Monolith | Microservices |

## Content Changes

### Added in v2:
- Security considerations section
- Performance benchmarks
- API versioning strategy

### Removed in v2:
- Legacy compatibility section
- XML support

### Modified:
- Data model (significant restructure)
- Error handling approach

## Decision Evolution

| Decision | v1 | v2 | Reason |
|----------|----|----|--------|
| Auth | Sessions | OAuth | Client requirement |
| DB | Mongo | Postgres | Scale concerns |

## Conflicts

⚠️ No conflicts detected. V2 supersedes v1.

## Recommendation

V2 should be the source of truth. Consider:
- Archiving v1 with supersedes relationship
- Updating references to point to v2
```

## Use Cases

1. **Spec Evolution**: Track how requirements changed
2. **Option Analysis**: Compare architectural choices
3. **Conflict Detection**: Find contradictory information
4. **Audit Trail**: Document decision changes

## Related Commands

- `/ask` - Query about specific differences
- `/trends` - See evolution over time
- `/flow` - Track mode transitions
