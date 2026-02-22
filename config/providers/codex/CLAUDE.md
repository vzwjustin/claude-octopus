# Codex CLI Provider Configuration

This file contains Codex-specific instructions for Claude Octopus workflows.

## Provider Information

- **Provider**: Codex CLI (OpenAI)
- **Emoji**: 🔴
- **API Key**: Uses `OPENAI_API_KEY` environment variable
- **CLI Command**: `codex`

## Usage Patterns

### Invoking Codex

```bash
# Basic query (uses CLI default model)
codex "your question here"

# With GPT-5.3-Codex (premium, high-capability)
codex --model gpt-5.3-codex "your question here"

# Reading from stdin
echo "your question" | codex
```

### Codex Strengths

Codex excels at:
1. **Technical Implementation Analysis** - Deep code pattern understanding
2. **Framework-Specific Guidance** - React, Next.js, Python, etc.
3. **Code Generation** - Production-ready code examples
4. **API Documentation Analysis** - Understanding official docs
5. **Debugging Assistance** - Error analysis and fixes

### When to Use Codex

Use Codex for:
- Technical implementation details
- Code pattern recommendations
- Framework-specific best practices
- Error debugging and resolution
- API integration patterns

### Models

| Model | Context | Reasoning Effort | Cost |
|-------|---------|------------------|------|
| `gpt-5.3-codex` | 400K | low, medium, high, xhigh | $1.75/$14.00 per MTok |
| `gpt-5.3-codex-spark` | 128K | - (1000+ tok/s) | Pro-only |
| `gpt-5.2-codex` | 400K | low, medium, high, xhigh | $1.75/$14.00 per MTok |
| `gpt-5.1-codex-mini` | 400K | - | $0.30/$1.25 per MTok |

### Cost Considerations

- Default model: `gpt-5.3-codex` ($1.75/$14.00 per MTok input/output)
- Spark model: `gpt-5.3-codex-spark` (15x faster, Pro subscription required)
- Estimated cost: ~$0.01-0.15 per query depending on model
- Cost depends on input/output token count and reasoning effort
- Uses your personal OPENAI_API_KEY (or OAuth via `codex auth`)

## Security

- API key stored securely in `~/.codex/auth.json` (OAuth)
- OR via `OPENAI_API_KEY` environment variable
- Never log or expose API keys in output
- All API calls are authenticated

## Timeout Configuration

Default timeout: 60 seconds
Can be configured in orchestrate.sh:
```bash
CODEX_TIMEOUT=120  # 2 minutes for complex queries
```

## Error Handling

Common errors:
- `401 Unauthorized`: Check API key configuration
- `429 Rate Limited`: Too many requests, wait and retry
- `Timeout`: Query too complex, simplify or increase timeout

## Integration with Workflows

Codex is used in:
- **Discover Phase**: Technical research and implementation analysis
- **Develop Phase**: Code generation and pattern guidance
- **Grapple Phase**: Adversarial review and critique
