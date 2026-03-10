# slack-message

User-invocable skill that formats messages with Slack markup and copies to clipboard.

## Usage

```
/slack-message [message topic or content]
```

## What it does

- Converts text to proper Slack markup (bold, italic, bullets, code blocks, emoji)
- Copies formatted message to clipboard via `pbcopy`
- Paste directly into Slack with Cmd+V

## Clipboard permissions

Add to `~/.claude/settings.json` under `permissions.allow`:

```json
"Bash(printf*pbcopy)",
"Bash(*pbcopy*)",
"Bash(pbcopy*)"
```

## Install

```json
{
  "skills": {
    "slack-message": {
      "source": "github:VorobiovD/claude-plugins/plugins/slack-message"
    }
  }
}
```
