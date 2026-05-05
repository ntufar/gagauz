# AGENTS.md — Gagauz stories site

Instructions for AI coding agents (Codex, OpenCode, Copilot agent mode, and others). **Cursor** also reads `.cursor/rules/*.mdc`; keep those aligned with this file.

## What this is

A **static** website of Gagauz stories, legends, and tales. It is **single-language**: visitors see **Gagauz only** (no language switcher, no extra locale files unless the maintainer explicitly asks).

## Repository layout

| Path | Purpose |
|------|--------|
| **`public/`** | **Deployable site root.** GitHub Pages uploads **only** this folder. Put HTML, CSS, images, and client-side JS here. |
| **`.github/workflows/deploy-pages.yml`** | Deploys `public/` to GitHub Pages on push to **`main`** or **`master`**. |
| **`.github/copilot-instructions.md`** | Short norms for **GitHub Copilot** Chat / code review (see also this file). |
| **`.cursor/rules/*.mdc`** | **Cursor** always-on rules; mirror critical constraints here. |
| **`CLAUDE.md`** | **Claude Code** entrypoint; it imports this file via `@AGENTS.md`. |

## Published site — language and markup

- All **visitor-visible** copy: titles, nav, buttons, body text, footers, `<title>`, `meta description`, Open Graph — **Gagauz**.
- Root document: **`<html lang="gag">`**. Encoding: **UTF-8** (`<meta charset="utf-8">`, UTF-8 files on disk).
- Story content stays **Gagauz**; do not add parallel English/Romanian/Russian summaries unless the maintainer requests it.
- Do **not** add `en.json` / `ro.json` / i18n key files for this project unless multilingual support is explicitly requested.
- **Developer-facing** text (code comments, variable names, commit messages) may stay **English** for tooling unless the maintainer prefers Gagauz.

```html
<!-- Correct -->
<html lang="gag">

<!-- Wrong for this repo (visitor-facing root) -->
<html lang="en">
```

## GitHub Pages and links

- Hosting is **GitHub Pages** via the workflow above — **no server secrets** in the repo.
- Use **relative URLs** for internal links and assets (e.g. `./styles.css`, `./images/foo.webp`) so the site works under `https://<user>.github.io/<repo>/` and under a custom domain.
- Default branch for deployment: **`main`** or **`master`** (workflow listens to both).
- Prefer **trusted version tags** (e.g. `@v4`) for Actions; keep workflows minimal.
- Use **`.gitignore`** for `node_modules/`, build output, `.env*`, and editor junk. Do not commit deploy artifacts unless the project intentionally checks in build output.

## Build and check

- **No build step** today: edit files under `public/` and push.
- **Local check**: open `public/index.html` in a browser (or use a static server if you add client routing later).
- **After push**: confirm **Actions → Deploy GitHub Pages** succeeds; site URL appears in the workflow summary and **Settings → Pages**.

## Cross-tool reference

| Tool | Primary instruction files |
|------|-----------------------------|
| **OpenAI Codex** | `AGENTS.md` (repo root) |
| **OpenCode** | `AGENTS.md` (and optional `~/.config/opencode/AGENTS.md` globally) |
| **Claude Code** | `CLAUDE.md` → imports `@AGENTS.md` |
| **GitHub Copilot** | `.github/copilot-instructions.md` plus `AGENTS.md` where the product supports agent instructions |
| **Cursor** | `.cursor/rules/*.mdc` |

When a rule conflicts, apply the **stricter** constraint. Prefer small, focused edits over wide refactors unless asked.
