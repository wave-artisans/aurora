# Ask Command

Ask questions and get answers from your knowledge base.

## Usage

```
/ask <question>
```

## Description

The ask command searches your Aurora knowledge base, finds relevant documents, and synthesizes an answer. This is Claude-powered knowledge Q&A.

## How It Works

1. **Parse Question**: Understand what you're asking
2. **Search Documents**: Find relevant content across all modes
3. **Synthesize Answer**: Combine information from multiple sources
4. **Cite Sources**: Reference documents used

## Examples

```
/ask What are the main findings from our AI governance research?
/ask How does our authentication system work?
/ask What decisions were made in the Alpha project meetings?
/ask Create an onboarding guide from our documentation
/ask Summarize our Q4 achievements
```

## Output

```
Based on 12 documents in your knowledge base:

[Synthesized answer here...]

Sources:
- [[Deep-Field/ai-governance/findings|AI Governance Findings]]
- [[Curiosity-Queue/ai-research/notes|AI Research Notes]]
- [[Jam-Sync/2025-12-10_sync|Project Sync Notes]]
```

## Capabilities

- Multi-document synthesis
- Cross-mode searching
- Temporal context (recent vs historical)
- Relationship-aware (follows document links)
- Citation generation

## Tips

- Be specific in your questions
- Ask for comparisons: "How does X differ from Y?"
- Ask for synthesis: "Summarize all our notes on X"
- Ask for creation: "Create a brief on X from our docs"

## Related Commands

- `/retrieve` - Direct search without synthesis
- `/brief` - Executive summary on a topic
- `/report` - Detailed report generation
