# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Repo purpose / current state
- The git repository currently tracks only `LICENSE`.
- The working directory looks like an Obsidian vault (currently untracked in git): `.obsidian/` configuration, top-level daily-note style Markdown files (e.g. `YYYY-MM-DD.md`), and plugin-related folders such as `copilot/`.

## Common commands
### Inspect what’s actually versioned
- Show tracked vs untracked changes:
  - `git status`
- List tracked files:
  - `git ls-files`

### Build / lint / test
- There is currently no build/test/lint tooling checked into this repo (no `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Makefile`, etc.).
- If this repo later becomes an application/library repo, update this section with the canonical build/test/lint commands.

## High-level structure (big picture)
### Obsidian configuration
- `.obsidian/` contains Obsidian JSON configuration (workspace/app/appearance, etc.) and plugin enablement.
- `.obsidian/core-plugins.json` controls which Obsidian core plugins are enabled (includes things like Daily Notes, Templates, Graph view, etc.).
- `.obsidian/community-plugins.json` lists enabled community plugins. Current list includes:
  - `calendar`, `table-editor-obsidian`, `obsidian-tasks-plugin`, `templater-obsidian`, `dataview`, `obsidian-excalidraw-plugin`, `obsidian-kanban`, `obsidian-git`, `obsidian-style-settings`, `obsidian-icon-folder`, `remotely-save`, `quickadd`, `omnisearch`, `copilot`.

### Copilot plugin prompts
- `copilot/copilot-custom-prompts/` contains Markdown prompt templates (with YAML frontmatter) used by the Obsidian Copilot plugin.
  - Examples: `Make longer.md`, `Make shorter.md`.

### Notes
- Markdown files like `2025-12-12.md` appear to be note files (currently empty and untracked).

## Working assumptions for future agents
- Treat this repository primarily as a content vault unless build/test tooling is added later.
- When asked to “make changes”, clarify whether the change should be:
  - an Obsidian config change under `.obsidian/`,
  - editing/adding Markdown notes,
  - editing/adding Copilot prompt templates under `copilot/`,
  - or adding actual executable source code (and, if so, what language/tooling to use).