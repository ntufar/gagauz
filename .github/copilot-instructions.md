# GitHub Copilot — repository instructions

Apply **`AGENTS.md`** at the repository root as the **authoritative** guide for edits, chat, and reviews. The bullets below repeat the highest-impact rules for environments that weight this file heavily (including some code review paths).

## Must-follow

- **Deploy root**: Only **`public/`** is published to GitHub Pages (`deploy-pages.yml`). New pages, assets, and CSS belong there unless the workflow is intentionally changed.
- **Gagauz-only UI**: All visitor-visible strings (including `<title>`, meta, nav, story body) are **Gagauz**. Use **`<html lang="gag">`** and **UTF-8**.
- **No i18n sprawl**: Do not add locale JSON / language toggles unless the maintainer explicitly asks.
- **Links and assets**: On **project Pages** (`…/github.io/<repo>/`), use **`/<repo>/…`** paths for internal links and CSS so `…/repo` without a trailing slash does not break `./masallar/…` (see `AGENTS.md`).
- **Secrets**: Never commit tokens, API keys, or private keys. This site is static Pages — no repo secrets required.
- **Branch**: Workflow deploys on **`main`** or **`master`** (match the repo default branch).

## Layout reminder

| Path | Role |
|------|------|
| `public/` | Shipped static site |
| `AGENTS.md` | Full agent instructions (Codex, OpenCode, Copilot agents, humans) |
| `CLAUDE.md` | Claude Code — imports `AGENTS.md` |
| `.cursor/rules/` | Cursor-specific always-on rules |
