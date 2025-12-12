# Repository Guidelines

## Project Structure & Module Organization
- This repo is currently an Obsidian vault plus support files. Git only tracks `LICENSE`; most content is untracked notes and plugin config.
- Obsidian config lives in `.obsidian/` (core/community plugin enablement, appearance, workspace state).
- Copilot plugin prompts live in `copilot/copilot-custom-prompts/` (Markdown with YAML frontmatter; examples: `Make shorter.md`, `Make longer.md`).
- Daily-style notes sit at the repo root (e.g., `YYYY-MM-DD.md`). Treat these as content, not code.

## Build, Test, and Development Commands
- No build/test/lint tooling is checked in. Standard helpers:
  - `git status` to view tracked vs untracked files.
  - `git ls-files` to list tracked files.
- If you add tooling (e.g., `package.json`, `Makefile`), document canonical commands here and keep them reproducible.

## Coding Style & Naming Conventions
- Markdown: prefer concise headings and bullets; keep frontmatter only where required by Obsidian plugins.
- File naming: keep prompts descriptive and imperative (e.g., `Summarize note.md`), daily notes as `YYYY-MM-DD.md`.
- Config JSON under `.obsidian/` should remain compact, valid JSON with no trailing commas.

## Testing Guidelines
- There are no automated tests today. If you introduce executable code, add the minimal test harness for that language and document how to run it.
- Name tests to mirror the subject (e.g., `feature_name.test.ext`); keep them alongside source or under a `tests/` directory you create.

## Commit & Pull Request Guidelines
- Use clear, action-oriented commit messages (`<verb>: <summary>`), e.g., `add: new copilot prompt`.
- Keep commits scoped and small; avoid bundling unrelated note edits with config changes.
- PRs should state intent, list key files touched, and include screenshots/gifs only if UI/visual output is affected.
- Link to relevant issues/tasks if available; note any new commands or manual steps reviewers must run.

## Security & Configuration Tips
- Do not commit secrets; Obsidian plugin tokens or sync credentials should stay local.
- Back up the vault externally if you rely on Obsidian sync; this repo currently does not capture most note content unless explicitly added.
- Before pushing, double-check `.obsidian/` changes for accidental workspace state you do not want to share.***
