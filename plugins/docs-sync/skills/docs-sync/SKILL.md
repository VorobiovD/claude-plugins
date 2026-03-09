---
name: docs-sync
description: Keep local project documentation in sync with code changes
user-invocable: false
---

## When to update docs
- After implementing a feature, refactor, or architectural change that affects project structure, APIs, or workflows
- After changing configuration, environment setup, or deployment procedures
- After adding, removing, or renaming major components or services

## How to update
- Look for a `docs/` directory in the project root (or the path the user specifies)
- Update only the docs that are affected by the current change
- Match the existing style and structure of the documentation
- Keep docs concise and factual — describe the current state, not the history of changes
- If a doc doesn't exist yet for a new major component, suggest creating one

## Rules
- NEVER commit docs unless the user explicitly asks — docs may be local-only
- NEVER create docs unprompted — only update existing ones or suggest new ones
- If unsure whether a change warrants a doc update, mention it to the user rather than silently skipping
