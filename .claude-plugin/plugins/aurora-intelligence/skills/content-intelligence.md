---
name: content-intelligence
description: Document understanding and content analysis. Use when summarizing documents, extracting entities, analyzing sentiment, scoring document quality, or extracting actions and decisions.
---

# Content Intelligence Skill

Document understanding and content analysis for the Aurora system.

## Purpose

This skill enables Claude to deeply understand document content, extract structured information, and assess document quality.

## Capabilities

### 1. Multi-Level Summarization

Generate summaries at different levels of detail.

**Levels:**
```
ONELINER:   Single sentence, <50 words
PARAGRAPH:  3-5 sentences, ~100 words
PAGE:       Structured sections, ~500 words
FULL:       Comprehensive, 50% of original
```

**Process:**
```
1. Parse document structure
2. Identify key sections and main points
3. Extract crucial facts and decisions
4. Compress based on target level
5. Maintain coherence and accuracy
```

**Summarization Principles:**
- Preserve core meaning
- Prioritize decisions and actions
- Maintain chronological order where relevant
- Keep proper nouns and specific details

### 2. Key Entity Extraction

Extract named entities from documents.

**Entity Types:**
```yaml
people:
  - name: "Alice Smith"
    role: "Project Lead"
    mentions: 5

organizations:
  - name: "Acme Corp"
    type: "Client"
    mentions: 12

projects:
  - name: "Project Alpha"
    status: "Active"
    mentions: 24

dates:
  - date: "2025-12-20"
    context: "Milestone deadline"
  - date: "2025-12-30"
    context: "Project delivery"

technologies:
  - name: "OAuth 2.0"
    category: "Authentication"
  - name: "PostgreSQL"
    category: "Database"
```

**Extraction Process:**
1. Run NER (Named Entity Recognition) patterns
2. Classify entities by type
3. Count mentions
4. Extract context for each
5. Link to existing knowledge base entries

### 3. Sentiment and Tone Analysis

Analyze emotional tone, especially for meeting notes.

**Tone Categories:**
- Positive: Enthusiasm, agreement, progress
- Negative: Concerns, blockers, frustration
- Neutral: Factual, informational
- Urgent: Deadline pressure, escalation
- Collaborative: Discussion, brainstorming

**Meeting Note Analysis:**
```
Document: 2025-12-17_sync.md

Overall Tone: Mixed (70% positive, 30% concerned)

Positive Signals:
  - "Great progress on the API"
  - "Team alignment is strong"

Concern Signals:
  - "Worried about the timeline"
  - "Blocker with third-party service"

Recommendation: Address blocker urgently
```

### 4. Action Item and Decision Extraction

Pull actionable items from content.

**Action Patterns:**
- "TODO:", "Action:", "ACTION ITEM:"
- "@Name will...", "Name to..."
- "needs to", "should", "must"
- Checkbox items: "- [ ]"
- "by [date]", "due [date]"

**Decision Patterns:**
- "Decided:", "Decision:"
- "We agreed", "The team chose"
- "Going with", "Selected"
- "Approved", "Rejected"

**Extraction Output:**
```yaml
actions:
  - text: "Review API design"
    owner: "Alice"
    due: "2025-12-19"
    source_line: 45

decisions:
  - text: "Use OAuth 2.0 for authentication"
    date: "2025-12-17"
    rationale: "Client security requirements"
    participants: ["Alice", "Bob"]
```

### 5. Quality Scoring

Assess document quality and completeness.

**Quality Dimensions:**

| Dimension | Weight | Criteria |
|-----------|--------|----------|
| Completeness | 25% | Has all required sections |
| Clarity | 25% | Clear language, good structure |
| Freshness | 20% | Recently updated |
| Connectivity | 15% | Links to related docs |
| Metadata | 15% | MAGI fields complete |

**Scoring Process:**
```
1. Check MAGI completeness (all required fields)
2. Analyze structure (headings, sections)
3. Check update recency
4. Count relationships/links
5. Assess language clarity
6. Calculate weighted score
```

**Score Ranges:**
- 90-100: Excellent
- 75-89: Good
- 60-74: Adequate
- Below 60: Needs improvement

**Quality Report:**
```
📊 Quality Score: 78/100 (Good)

✅ Completeness: 85%
   All major sections present

✅ Clarity: 80%
   Clear structure, minor jargon

⚠️ Freshness: 65%
   Updated 45 days ago

⚠️ Connectivity: 60%
   Only 2 relationships defined

✅ Metadata: 100%
   All MAGI fields complete

Suggestions:
- Add relationships to related docs
- Review for potential updates
```

## Integration Points

### Commands Using This Skill
- `/summarize` - Multi-level summaries
- `/extract-actions` - Action/decision extraction
- `/expand` - Quality gap identification
- `/simplify` - Content analysis for simplification

### Data Sources
- Document content (markdown)
- MAGI front matter
- `.magi/index.json` for freshness
- `.magi/relationships.json` for connectivity

## Best Practices

### For Summarization
1. Always preserve key decisions
2. Include named entities
3. Maintain document's purpose
4. Flag uncertainty

### For Entity Extraction
1. Normalize entity names
2. Link to existing entries
3. Track mention frequency
4. Provide context

### For Quality Scoring
1. Adjust weights by document type
2. Consider document age
3. Compare to similar docs
4. Provide actionable feedback
