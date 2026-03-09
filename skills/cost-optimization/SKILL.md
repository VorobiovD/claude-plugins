---
name: cost-optimization
description: Cost optimization rules for reducing Claude Code token usage and API costs
user-invocable: false
---

- Use Haiku (model: "haiku") for ALL subagent tasks: file exploration, codebase search, research, reading and summarizing
- For routine tasks (simple refactors, renames, test writing, config changes, small bug fixes), prefer Sonnet over Opus
- ALWAYS use Edit tool over Write tool for modifying existing files — Edit sends only the diff, Write resends the entire file
- Keep responses concise for straightforward work — save detailed explanations for complex architecture and debugging
- Suggest starting fresh sessions when switching to unrelated tasks instead of continuing in bloated contexts
- Minimize unnecessary file reads — if you already have the context, don't re-read
