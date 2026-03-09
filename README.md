# Claude Code Plugins

Shared skills for Claude Code — cost optimization and productivity.

## Skills

### cost-optimization (auto-active)
Reduces token usage by using Haiku for subagent tasks, Sonnet for routine work, Edit over Write, and concise responses.

### slack-message (invoke with `/slack-message`)
Formats messages with proper Slack markup and copies to clipboard. No more broken markdown tables.

## Install

Add the marketplace:
```
/plugin marketplace add VorobiovD/claude-plugins
```

Install skills:
```
/plugin install cost-optimization
/plugin install slack-message
```

## Clipboard permissions

Add to `~/.claude/settings.json` under `permissions.allow`:
```json
"Bash(printf*pbcopy)",
"Bash(*pbcopy*)",
"Bash(pbcopy*)"
```
