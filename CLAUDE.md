# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is an Obsidian vault repository with selective git tracking. Currently only `LICENSE` is tracked in git; most content (notes, plugin configuration) remains untracked. The repo serves as a personal knowledge management system with AI-assisted note editing capabilities.

## Common Commands

### Inspect repository state
```bash
git status              # View tracked vs untracked files
git ls-files            # List all tracked files
```

### Build/Test/Lint
No build, test, or lint tooling is currently configured. If you add tooling (e.g., `package.json`, `Makefile`, Python dependencies), document the canonical commands here.

## High-Level Architecture

### Obsidian Configuration
- `.obsidian/` contains all Obsidian settings and plugin configurations
  - `core-plugins.json`: Enabled core plugins (daily-notes, templates, canvas, graph, etc.)
  - `community-plugins.json`: Installed community plugins including calendar, dataview, templater, kanban, copilot, remotely-save, and others
  - `workspace.json`, `app.json`, `appearance.json`: UI state and preferences
  - `plugins/*/`: Individual plugin settings in `data.json` files

### Copilot Plugin Custom Prompts
- `copilot/copilot-custom-prompts/`: Markdown files with YAML frontmatter defining custom AI prompts
  - Each file defines a prompt template with metadata (context menu/slash command enablement, ordering)
  - Pattern: `{}` is replaced with selected text when prompt is invoked
  - Examples: `Make shorter.md`, `Make longer.md`

### Content Organization
- Root-level Markdown files are notes (e.g., `2025-12-12.md` for daily notes)
- `Excalidraw/`: Directory for Excalidraw drawing files (if used)
- Most note content is intentionally untracked by git

## File Naming Conventions

- Copilot prompts: Imperative, action-oriented names (e.g., `Summarize note.md`)
- Daily notes: `YYYY-MM-DD.md` format
- Obsidian config: Standard JSON files with no trailing commas

## Commit Guidelines

- Use action-oriented commit messages: `<verb>: <summary>` (e.g., `add: new copilot prompt`)
- Keep commits scoped and small
- Avoid bundling unrelated note edits with config changes
- Before pushing, verify `.obsidian/` changes don't include unwanted workspace state

## Security Notes

- Never commit secrets, API keys, or Obsidian sync credentials
- The vault should be backed up externally; this git repo intentionally excludes most content
- Review `.obsidian/` changes carefully before committing to avoid leaking personal workspace preferences

## Working with This Repository

When asked to make changes, clarify the intent:
- **Obsidian config changes**: Modify `.obsidian/` JSON files
- **Copilot prompts**: Add/edit templates in `copilot/copilot-custom-prompts/`
- **Notes**: Create/edit Markdown files (usually untracked)
- **Executable code**: Requires adding build tooling and updating this file with commands
