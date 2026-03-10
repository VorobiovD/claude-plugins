# clean-commits

Auto-active skill that keeps git history clean and professional.

## What it does

- Removes AI fingerprints from commit messages and PR descriptions
- Enforces imperative mood, concise subject lines (under 72 chars)
- Strips task lists, time tracking, and TODO items from commits
- Ensures source code has no AI attribution comments

## Install

```json
{
  "skills": {
    "clean-commits": {
      "source": "github:VorobiovD/claude-plugins/plugins/clean-commits"
    }
  }
}
```

No configuration needed — works automatically once installed.
