# Trends Command

Analyze how topics evolve over time.

## Usage

```
/trends <topic> [--period <period>] [--output chart|list|narrative]
```

## Description

Analyzes how a topic has evolved across your Aurora knowledge base over time, showing changes in thinking, decisions, and focus.

## Arguments

- `topic`: Subject to analyze trends for

## Options

- `--period`: Time range (30d, 90d, 6m, 1y, all)
- `--output`: Output format

## Analysis Dimensions

1. **Volume**: How often the topic appears over time
2. **Sentiment**: How thinking has evolved (positive/negative/neutral)
3. **Decisions**: Key decisions made and when
4. **Mode Distribution**: Which Aurora modes discuss it
5. **Relationships**: How connections to other topics change

## Output

```
📈 Trend Analysis: "API Design"

Period: Last 6 months
Documents: 24 mentioning this topic

---

## Volume Over Time

     Jun    Jul    Aug    Sep    Oct    Nov    Dec
     ██     ███    ████   ██     █████  ███████████
     2      3      4      2      5      8      (trending up)

Peak: December 2025 (8 documents)
Trigger: Project Alpha API work

## Evolution of Thinking

### Phase 1: Exploration (Jun-Jul)
"Should we use REST or GraphQL?"
Mode: 🟣 Curiosity Queue
Key docs: api-research.md, graphql-evaluation.md

### Phase 2: Decision (Aug)
Decision: "REST with OpenAPI spec"
Mode: 🟢 Deep Field
Key doc: api-architecture-decision.md

### Phase 3: Implementation (Sep-Dec)
Focus shifted to implementation details
Mode: 🟢 Focus → 🔴 Commitments
Key docs: api-spec-v1.md, api-spec-v2.md

## Key Decision Timeline

| Date | Decision | Context |
|------|----------|---------|
| Aug 15 | REST over GraphQL | Simpler client integration |
| Oct 1 | OAuth 2.0 for auth | Security requirements |
| Nov 20 | Version in URL | Client compatibility |
| Dec 5 | Rate limiting added | Scale concerns |

## Sentiment Evolution

Jun-Jul: Uncertain (exploring options)
Aug: Confident (decision made)
Sep-Nov: Focused (building)
Dec: Stressed (deadline pressure) ⚠️

## Related Topics Also Trending

- Authentication (+120% mentions)
- Performance (-30% mentions)
- Client Integration (+80% mentions)

## Insights

1. API work has intensified toward year-end
2. Security concerns emerged in October
3. Consider: Post-launch documentation needed
```

## Use Cases

1. **Project Evolution**: How a project's focus changed
2. **Technology Decisions**: When and why choices were made
3. **Team Patterns**: How collaboration evolved
4. **Personal Growth**: How your thinking developed

## Related Commands

- `/compare` - Compare specific documents
- `/ask` - Query about specific trend points
- `/report` - Generate trend report
