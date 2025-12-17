# Validate Command

Run consistency checks on the Aurora knowledge base.

## Usage

```
/validate [--check <name>] [--fix] [--report]
```

## Description

The validate command checks the Aurora system for:

1. **Orphaned Files**: Documents without MAGI front matter
2. **Broken Relationships**: References to non-existent doc-ids
3. **Missing Companions**: Binary files without companion markdown
4. **TOC Accuracy**: ToC entries matching actual documents
5. **Folder Structure**: Correct Aurora mode folder organization
6. **Duplicate Doc-IDs**: Same doc-id used in multiple files
7. **MAGI Completeness**: Missing required front matter fields
8. **Mode Mismatches**: Document aurora-mode vs actual folder location

## Checks

### orphaned-files
Find markdown files missing MAGI front matter.
- Severity: HIGH
- Auto-fix: No (requires content analysis)

### broken-relationships
Find doc-id references pointing to non-existent documents.
- Severity: MEDIUM
- Auto-fix: Yes (remove broken edges)

### missing-companions
Find binary files without companion metadata markdown.
- Severity: HIGH
- Auto-fix: Partial (generate basic companion)

### toc-accuracy
Verify ToC files reflect actual document structure.
- Severity: LOW
- Auto-fix: Yes (regenerate ToC)

### folder-structure
Check Aurora mode folders exist with proper structure.
- Severity: MEDIUM
- Auto-fix: Yes (create missing folders)

### duplicate-docid
Find duplicate doc-id values across documents.
- Severity: CRITICAL
- Auto-fix: No (requires manual decision)

### magi-completeness
Check all documents have required MAGI fields.
- Severity: MEDIUM
- Auto-fix: Partial (generate missing fields)

### mode-mismatch
Documents in wrong folder based on aurora-mode value.
- Severity: MEDIUM
- Auto-fix: Yes (move to correct folder)

## Options

- `--check <name>`: Run specific check only
- `--fix`: Apply safe automatic fixes
- `--report`: Generate detailed markdown report

## Examples

```
/validate                      # Run all checks
/validate --check orphaned     # Run specific check
/validate --fix                # Auto-fix where safe
/validate --report             # Detailed report
```

## Output

Summary table:
| Check | Status | Issues |
|-------|--------|--------|
| Orphaned Files | PASS/FAIL | count |
| ... | ... | ... |

Followed by details for each issue found.
