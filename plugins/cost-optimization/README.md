# cost-optimization

Auto-active skill that reduces Claude Code token usage by 30-60%.

## What it does

- Routes subagent tasks to cheaper models (Haiku for exploration/search, Sonnet for routine work)
- Prefers Edit over Write tool to send diffs instead of full files
- Keeps responses concise for straightforward tasks
- Minimizes unnecessary file re-reads

## Install

```json
{
  "skills": {
    "cost-optimization": {
      "source": "github:VorobiovD/claude-plugins/plugins/cost-optimization"
    }
  }
}
```

No configuration needed — works automatically once installed.
