# Gaps Command

Identify missing documentation and knowledge holes.

## Usage

```
/gaps [--scope <scope>] [--focus <area>]
```

## Description

Analyzes your Aurora knowledge base to find gaps - topics that are mentioned but not documented, areas that need more coverage, or structural holes.

## Options

- `--scope`: Analysis scope (all, mode, project)
- `--focus`: Focus area (topics, structure, references)

## Analysis Types

### Topic Gaps
Finds concepts mentioned but not documented:
- Terms that appear frequently without dedicated docs
- References to external resources not captured
- Implied knowledge that should be explicit

### Structural Gaps
Finds organizational holes:
- Empty or sparse mode folders
- Projects without proper documentation
- Missing companion files for binaries

### Reference Gaps
Finds broken or missing connections:
- Mentioned documents that don't exist
- Topics referenced across docs without linking
- Orphaned documents (no relationships)

## Output

```
🕳️ Gap Analysis

Scope: Full knowledge base
Documents analyzed: 145
Gaps identified: 12

---

## Topic Gaps (7)

### High Priority

1. **Authentication Flow**
   Mentioned in: 5 documents
   Context: "see auth flow", "authentication process"
   Suggestion: Create dedicated auth documentation
   → Create in: Library/auth-flow.md

2. **Deployment Process**
   Mentioned in: 3 documents
   Context: "deployment steps", "deploy to production"
   Suggestion: Document deployment procedure
   → Create in: Library/deployment.md

### Medium Priority

3. **Error Codes**
   Mentioned in: 2 documents
   No centralized reference exists
   → Create in: Library/error-codes.md

[...]

## Structural Gaps (3)

1. **Recharge folder is empty**
   You have 0 documents in 🔵 Life mode
   Suggestion: Add some non-work content!

2. **Project Beta lacks README**
   Project folder exists but no overview doc
   → Create: Deep-Field/project-beta/README.md

3. **Q3 has no retrospective**
   Q1, Q2 have retros; Q3 missing
   → Create: Done-Dusted/2025/q3-retro.md

## Reference Gaps (2)

1. **[[api-v2-spec]] referenced but doesn't exist**
   Found in: project-alpha-design.md
   Action: Create document or fix reference

2. **Invoice template mentioned without link**
   Found in: quick-ops-process.md
   Action: Add link to actual template

---

## Quick Actions

/ask "Create outline for Authentication Flow documentation"
/intake # if you have drafts to process
```

## Scope Options

```
/gaps --scope mode:focus          # Gaps in Deep Field only
/gaps --scope project:alpha       # Gaps in specific project
/gaps --focus topics              # Topic gaps only
/gaps --focus structure           # Structural gaps only
```

## Related Commands

- `/validate` - System health checks
- `/stale` - Find outdated content
- `/toc-update` - Fix structural issues
