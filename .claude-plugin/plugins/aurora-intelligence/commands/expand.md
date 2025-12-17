---
description: Suggest content additions for document
argument-hint: <document> [--section <section>] [--focus <focus>]
---

# Expand Command

Suggest additions and elaborations for a document.

## Usage

```
/expand <document> [--section <section>] [--focus <focus>]
```

## Description

Analyzes a document and suggests content that could be added to make it more complete, detailed, or useful.

## Arguments

- `document`: Path or doc-id to expand

## Options

- `--section`: Focus on specific section
- `--focus`: Type of expansion (examples, details, context, alternatives)

## Analysis

The command examines:
1. Document structure and completeness
2. Sections that seem thin
3. Concepts that need elaboration
4. Missing standard sections for document type
5. Related content in knowledge base that could be referenced

## Output

```
📝 Expansion Suggestions: api-design.md

Document Analysis:
  Type: Technical specification
  Completeness: 65%
  Sections: 8 present, 4 suggested

## Suggested Additions

### 1. Missing Sections

**Error Handling** (High Priority)
  Your API spec lacks error handling documentation.
  Suggested content:
  - Error code taxonomy
  - Response format for errors
  - Retry guidance

**Rate Limiting** (Medium Priority)
  Consider adding:
  - Rate limit values
  - Header documentation
  - Quota exceeded responses

### 2. Thin Sections

**Authentication** (Currently 2 paragraphs)
  Could benefit from:
  - Token refresh flow diagram
  - Example requests with headers
  - Scope definitions

### 3. Examples Needed

The following endpoints lack examples:
  - POST /users
  - PUT /users/{id}
  - DELETE /users/{id}

### 4. Related Content

Found in your knowledge base:
  - [[Library/api-patterns|API Patterns Guide]]
    → Could reference for consistency
  - [[Deep-Field/auth-research|Auth Research]]
    → Contains relevant OAuth details

## Quick Actions

Generate specific expansions:
  /expand api-design.md --section "Error Handling"
  /expand api-design.md --focus examples
```

## Focus Types

- `examples`: Add code examples, sample requests/responses
- `details`: Elaborate on existing points
- `context`: Add background, rationale, history
- `alternatives`: Add considerations of other approaches

## Related Commands

- `/simplify` - Make content more accessible
- `/compare` - Compare with similar docs
- `/ask` - Query for specific content to add
