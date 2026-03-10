# slack-message

Format messages with Slack markup and copy to clipboard.

## Usage

```
/slack-message [message topic or content]
```

Available as both a command (always in autocomplete) and a skill (auto-detected by context).

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
