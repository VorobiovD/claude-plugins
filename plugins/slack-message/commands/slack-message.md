---
name: slack-message
description: "Format and copy a Slack-ready message to clipboard"
argument-hint: "[message topic or content]"
---

Format the message using Slack markup. Rules:

- Use `*text*` for bold headers (NEVER use # markdown headers)
- Use `_text_` for italic
- Use `~text~` for strikethrough
- Use `*_text_*` for bold italic
- Use • for bullet points (NEVER use - dashes)
- Use `` `code` `` for inline code
- Use ``` for code blocks
- Use `> text` for blockquotes
- Use `:emoji_name:` for emoji (e.g. `:white_check_mark:` `:warning:` `:rocket:`)
- Use `:large_blue_circle:` `:red_circle:` `:large_yellow_circle:` for status indicators
- NEVER use markdown tables — use bullets instead
- NEVER use markdown links `[text](url)` — paste plain URLs
- NEVER use markdown headers (`#`, `##`) — use `*bold*` for section headers

Copy result to clipboard using single-line printf:
```
printf "formatted text with \n for newlines" | pbcopy
```

After copying, tell the user to paste with Cmd+V in Slack.
