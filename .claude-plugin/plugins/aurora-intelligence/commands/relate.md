# Relate Command

Discover connections between documents.

## Usage

```
/relate <document> [--depth <depth>] [--add]
```

## Description

AI-powered relationship discovery. Analyzes a document and finds connections to other documents in your Aurora knowledge base that may not be explicitly linked.

## Arguments

- `document`: Path or doc-id to analyze

## Options

- `--depth`: How deep to search (1-3, default 2)
- `--add`: Automatically add discovered relationships

## Discovery Methods

1. **Topic Similarity**: Documents about similar subjects
2. **Entity Matching**: Shared people, projects, concepts
3. **Temporal Proximity**: Created/modified around same time
4. **Tag Overlap**: Shared categorization
5. **Citation Analysis**: Referenced by same sources

## Output

```
🔗 Relationship Discovery: project-alpha-spec.md

Existing Relationships: 3
Discovered Relationships: 8

---

## Strong Matches (High Confidence)

1. **api-design-patterns.md** 📚 Library
   Similarity: 92%
   Reason: Shared concepts (REST, versioning, auth)
   Type: references
   → This spec could reference the patterns guide

2. **2025-12-10_alpha-sync.md** 🟠 Collab
   Similarity: 88%
   Reason: Same project, temporal proximity
   Type: supports
   → Meeting notes discuss this spec

3. **auth-research.md** 🟣 Explore
   Similarity: 85%
   Reason: OAuth concepts appear in both
   Type: extends
   → Spec builds on this research

## Moderate Matches

4. **client-acme-requirements.md** 🔴 Commitments
   Similarity: 72%
   Reason: Client requirements drive this spec
   Type: implements

5. **security-policy.md** 📚 Library
   Similarity: 68%
   Reason: Auth section overlaps
   Type: references

## Weak Matches (For Review)

6. **old-api-spec.md** ⚫️ Archive
   Similarity: 65%
   Reason: Previous version
   Type: supersedes

---

## Relationship Graph

project-alpha-spec
├── references
│   ├── api-design-patterns (suggested)
│   └── security-policy (suggested)
├── extends
│   └── auth-research (suggested)
├── implements
│   └── client-acme-requirements (suggested)
├── supersedes
│   └── old-api-spec (suggested)
└── supported-by
    └── 2025-12-10_alpha-sync (suggested)

## Add Relationships?

/relate project-alpha-spec.md --add

Will add MAGI footnote relationships for strong matches.
```

## Adding Relationships

When using `--add`:
1. Creates footnote syntax in document
2. Updates `.magi/relationships.json`
3. Adds reverse relationships where appropriate

## Relationship Types Discovered

| Type | When Used |
|------|-----------|
| references | Document cites another |
| extends | Document builds on another |
| implements | Concrete from abstract |
| supersedes | Replaces older version |
| supports | Meeting/notes support a doc |
| contains | Parent-child relationship |

## Related Commands

- `/validate --check relationships` - Check for broken links
- `/retrieve related:doc-id` - Search by relationship
- `/compare` - Deep comparison of two docs
