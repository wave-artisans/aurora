---
description: Search documents in knowledge base
argument-hint: <query> [options]
---

# Retrieve Command

Search and find documents in the Aurora knowledge base.

## Usage

```
/retrieve <query> [options]
```

## Description

High-performance search across the Aurora knowledge base with multiple query types.

## Query Syntax

### Tag Filter
```
tag:photography
tags:surf,travel
-tag:archived
```

### Mode Filter
```
mode:focus
@commitments
mode:explore,archive
```

### Date Filter
```
created:2025-12
modified:>2025-12-01
modified:<7d
created:2025-Q4
```

### Full-Text Search
```
"exact phrase"
machine learning
word*
```

### Title/Description
```
title:aurora
title:~photgraphy    # fuzzy match
desc:knowledge
```

### Relationship Traversal
```
related:doc-id-here
linked:document-title
refs:doc-id          # docs referencing this
refby:doc-id         # docs this references
```

### Combined Queries
```
"machine learning" tag:ai mode:focus created:>2025-01
```

## Options

- `--limit <n>`: Maximum results (default: 20)
- `--mode <mode>`: Filter by Aurora mode
- `--json`: Output as JSON
- `--paths`: Show file paths only
- `--recent`: Last 7 days modified

## Examples

```
/retrieve "project alpha"
/retrieve tag:photography mode:archive
/retrieve created:>2025-12-01 --limit 50
/retrieve related:abc123-def456
/retrieve --recent
/retrieve title:~desing    # fuzzy search for typos
```

## Output

For each result:
- Title
- Aurora mode (with color emoji)
- Description snippet
- Tags
- Last modified
- Match context (for text searches)

## Performance Notes

- Uses `.magi/index.json` for fast lookups
- Tag queries use `.magi/tags.json`
- Relationship queries use `.magi/relationships.json`
- Full-text uses ripgrep for speed
