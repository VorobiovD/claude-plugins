# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A collection of Claude Code plugins (skills) distributed via the plugin marketplace format. Each plugin lives in `plugins/<name>/` and is independently installable. The root `marketplace.json` at `.claude-plugin/marketplace.json` registers all plugins.

## Architecture

```
.claude-plugin/marketplace.json          # Root marketplace manifest ($schema, owner, plugins[])
.github/workflows/validate-plugins.yml   # CI validation of all manifests
plugins/<name>/
  .claude-plugin/plugin.json             # Plugin manifest (name, version, author, license, keywords, skills[])
  skills/<name>/SKILL.md                 # Skill definition (frontmatter + instructions)
  README.md                              # Per-plugin documentation and install instructions
```

**Plugin types:**
- **Auto-active** (`user-invocable: false`): Loaded automatically, runs as background rules — `cost-optimization`, `clean-commits`, `docs-sync`
- **User-invocable** (`user-invocable: true` or has `argument-hint`): Triggered via slash command — `slack-message`, `laravel-docker-switch`

## Adding a New Plugin

1. Create `plugins/<name>/.claude-plugin/plugin.json` with name, description, version, license, keywords, author, repository, homepage, and skills array
2. Create `plugins/<name>/skills/<name>/SKILL.md` with YAML frontmatter (`name`, `description`, `user-invocable`) and skill instructions in markdown
3. Create `plugins/<name>/README.md` with description, usage, and install snippet
4. Add the plugin entry to `.claude-plugin/marketplace.json` under the `plugins` array (include all fields: name, source, description, version, category, license, keywords, author, repository, homepage)
5. Update root `README.md` plugin table

## Conventions

- SKILL.md frontmatter uses `---` delimiters with fields: `name`, `description`, `user-invocable`, optional `argument-hint`
- Plugin names use kebab-case
- Each plugin is self-contained in its directory — no shared code between plugins
- No build step, no dependencies — plugins are pure markdown skill definitions
- CI validates all JSON manifests and cross-references marketplace with plugin directories on push/PR
