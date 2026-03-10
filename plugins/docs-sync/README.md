# docs-sync

Auto-active skill that keeps local project documentation in sync with code changes.

## What it does

- Watches for changes to project structure, APIs, or workflows
- Updates affected docs in your `docs/` directory
- Never commits docs unless explicitly asked — designed for local-only documentation
- Matches existing documentation style and structure

## Install

```json
{
  "skills": {
    "docs-sync": {
      "source": "github:VorobiovD/claude-plugins/plugins/docs-sync"
    }
  }
}
```

No configuration needed — works automatically once installed.
