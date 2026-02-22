# Gemini CLI Provider Configuration

This file contains Gemini-specific instructions for Claude Octopus workflows.

## Provider Information

- **Provider**: Gemini CLI (Google)
- **Emoji**: 🟡
- **API Key**: Uses `GEMINI_API_KEY` or `GOOGLE_API_KEY` environment variable
- **CLI Command**: `gemini`

## Usage Patterns

### Invoking Gemini

```bash
# Basic query
gemini -y "your question here"

# With reasoning mode
gemini -r "complex analysis question"

# Flash mode (faster, cheaper)
gemini -f "quick question"
```

### Gemini Strengths

Gemini excels at:
1. **Ecosystem Research** - Broad technology landscape analysis
2. **Market Trends** - Community adoption and popularity
3. **Alternative Approaches** - Multiple solution perspectives
4. **Documentation Synthesis** - Combining multiple sources
5. **Comparative Analysis** - Technology/library comparisons

### When to Use Gemini

Use Gemini for:
- Ecosystem and community research
- Technology comparison and alternatives
- Market trends and adoption analysis
- Multi-source documentation synthesis
- Strategic technology decisions

### Models

| Model | Context | Thinking Levels | Cost |
|-------|---------|-----------------|------|
| `gemini-3.1-pro-preview` | 1M | minimal, low, medium, high | $2.00/$12.00 per MTok |
| `gemini-3-pro-preview` | 1M | low, high | $2.00/$12.00 per MTok |
| `gemini-3-flash-preview` | 1M | minimal, low, medium, high | $0.50/$3.00 per MTok |

### Cost Considerations

- Default model: `gemini-3.1-pro-preview` (premium reasoning, 1M context)
- Flash model: `gemini-3-flash-preview` (fast, low-cost)
- Estimated cost: ~$0.01-0.05 per query depending on model
- Flash mode is cheaper for simple queries
- Uses your personal GEMINI_API_KEY

## Security

- API key stored securely in `~/.gemini/oauth_creds.json` (OAuth)
- OR via `GEMINI_API_KEY`/`GOOGLE_API_KEY` environment variable
- Never log or expose API keys in output
- All API calls are authenticated

## Timeout Configuration

Default timeout: 60 seconds
Can be configured in orchestrate.sh:
```bash
GEMINI_TIMEOUT=120  # 2 minutes for complex queries
```

## Error Handling

Common errors:
- `401 Unauthorized`: Check API key configuration
- `429 Rate Limited`: Too many requests, wait and retry
- `Timeout`: Query too complex, simplify or increase timeout
- `Safety Filter`: Content blocked by safety settings

## Integration with Workflows

Gemini is used in:
- **Discover Phase**: Ecosystem research and alternatives
- **Define Phase**: Consensus building with multiple perspectives
- **Develop Phase**: Alternative implementation approaches
- **Grapple Phase**: Adversarial review from different angle
