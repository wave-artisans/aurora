# Knowledge Synthesis Skill

Cross-document intelligence for the Aurora system.

## Purpose

This skill enables Claude to synthesize knowledge across multiple documents, answer complex questions, and identify patterns in the knowledge base.

## Capabilities

### 1. Multi-Document Question Answering

Answer questions by searching and combining information from multiple sources.

**Process:**
```
1. Parse the question to identify key concepts
2. Search across all modes for relevant documents
3. Rank documents by relevance
4. Extract relevant sections from top documents
5. Synthesize a coherent answer
6. Cite sources with wiki-style links
```

**Search Strategy:**
- Tag-based: Match question concepts to tags
- Full-text: Grep for key terms
- Title/description: MAGI metadata search
- Relationship: Follow document links

**Answer Quality:**
- Synthesize, don't just concatenate
- Reconcile conflicting information
- Acknowledge uncertainty
- Always cite sources

### 2. Contradiction Detection

Find conflicting information across documents.

**Detection Methods:**
```
1. Identify shared topics across documents
2. Extract claims/facts about those topics
3. Compare claims for consistency
4. Flag contradictions with context
```

**Contradiction Types:**
- Factual: Different values for same metric
- Temporal: Outdated vs current information
- Perspective: Different viewpoints on same issue
- Version: Old spec vs new spec

**Output Format:**
```
⚠️ Contradiction Found

Topic: API Rate Limits

Document A (api-spec-v1.md):
  "Rate limit: 100 requests/minute"

Document B (api-spec-v2.md):
  "Rate limit: 1000 requests/minute"

Resolution: Document B is newer (supersedes)
Action: Update references to v1
```

### 3. Knowledge Gap Identification

Find areas that need documentation.

**Gap Detection:**
```
1. Build topic graph from document content
2. Find topics mentioned but not documented
3. Identify thin coverage areas
4. Check for standard sections missing
5. Find referenced but non-existent docs
```

**Gap Types:**
- Topic gap: Concept needs its own document
- Depth gap: Topic covered too shallowly
- Structural gap: Missing standard docs (README, etc.)
- Reference gap: Broken wiki-style links

### 4. Automatic Cross-Referencing

Suggest relationships between documents.

**Algorithm:**
```
1. For each document, extract:
   - Named entities (people, projects, concepts)
   - Technical terms
   - Dates and events
2. Compare across documents
3. Score similarity
4. Suggest relationship type
5. Optionally add footnotes
```

**Relationship Scoring:**
- Entity overlap: +2 per shared entity
- Tag overlap: +1 per shared tag
- Temporal proximity: +1 if within 7 days
- Mode proximity: +0.5 if same mode
- Term frequency: Based on TF-IDF

### 5. Topic Clustering

Organize documents by topic automatically.

**Clustering Process:**
```
1. Extract key terms from all documents
2. Build term frequency matrix
3. Cluster documents by similarity
4. Name clusters based on common terms
5. Identify outliers (unique documents)
```

**Uses:**
- Suggest folder organization
- Find related documents for `/relate`
- Identify knowledge domains
- Support ToC generation

## Integration Points

### Commands Using This Skill
- `/ask` - Question answering
- `/relate` - Relationship discovery
- `/gaps` - Gap analysis
- `/validate` - Contradiction checking

### Data Flow
```
Query → Parse → Search → Retrieve → Rank → Synthesize → Cite → Response
```

## Best Practices

### For Question Answering
1. Prefer recent documents over old
2. Weight actively-used modes higher
3. Check relationships for context
4. Acknowledge knowledge limits

### For Contradiction Detection
1. Consider document freshness
2. Check for supersedes relationships
3. Don't flag opinion differences
4. Provide resolution guidance

### For Gap Identification
1. Consider document types
2. Check if gap is intentional
3. Prioritize gaps by impact
4. Suggest specific file paths

## Example Queries

**Simple lookup:**
"What is our rate limit policy?"
→ Search for rate limit, return from relevant doc

**Synthesis:**
"What decisions have we made about authentication?"
→ Search all docs, extract auth decisions, synthesize timeline

**Comparison:**
"How does our API compare to the old version?"
→ Find both specs, compare, summarize differences

**Gap analysis:**
"What documentation are we missing for Project Alpha?"
→ Analyze project folder, compare to complete projects, list gaps
