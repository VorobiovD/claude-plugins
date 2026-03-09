# Claude Code Plugins

Shared skills for Claude Code — cost optimization and productivity.

## Plugins

### cost-optimization
Auto-active rules that reduce token usage by 30-60%. Automatically applies to every conversation — no need to invoke manually.

**What it does:**
- Routes subagent tasks to Haiku (cheapest model)
- Prefers Sonnet for routine work instead of Opus
- Uses Edit over Write (sends diffs instead of full files)
- Keeps responses concise, suggests fresh sessions for new tasks

### slack-message
Format messages with proper Slack markup and copy to clipboard. Invoke with `/slack-message`.

**What it does:**
- Converts your request into properly formatted Slack markup
- Handles bold, italic, bullets, code blocks, emoji, blockquotes
- Copies to clipboard — just paste with Cmd+V in Slack
- No more broken markdown tables or links in Slack

## Install

Add to your `~/.claude/settings.json`:

```json
{
  "skills": {
    "claude-plugins": {
      "source": "github:VorobiovD/claude-plugins"
    }
  }
}
```

Or install individual plugins:

```json
{
  "skills": {
    "cost-optimization": {
      "source": "github:VorobiovD/claude-plugins/plugins/cost-optimization"
    },
    "slack-message": {
      "source": "github:VorobiovD/claude-plugins/plugins/slack-message"
    }
  }
}
```

## Clipboard permissions (for slack-message)

Add to `~/.claude/settings.json` under `permissions.allow`:

```json
"Bash(printf*pbcopy)",
"Bash(*pbcopy*)",
"Bash(pbcopy*)"
```

## Structure

```
.claude-plugin/
  marketplace.json          # Plugin catalog
plugins/
  cost-optimization/
    .claude-plugin/
      plugin.json           # Plugin manifest
    skills/
      cost-optimization/
        SKILL.md            # Skill definition
  slack-message/
    .claude-plugin/
      plugin.json
    skills/
      slack-message/
        SKILL.md
```

## License

MIT
