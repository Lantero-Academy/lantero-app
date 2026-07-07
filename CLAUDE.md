# Lantero-App — CLAUDE.md

Private, on-device planner for parent-led family learning. The app sits with the **parent**,
never the child. Product principles live in `../Lantero-Blueprint/` — `02-design-constitution.md`
is binding. Read `README.md` for the product story and `ONBOARDING.md` for first-run flow.

## Architecture (current)

- **Single file, no build step.** The entire app is `docs/index.html` (~1,180 lines):
  vanilla JS in one `<script>`, CSS in one `<style>`, no framework, no bundler, no backend,
  no accounts, no telemetry.
- **Local-first.** All data is a single global state object `S`, persisted to
  `localStorage` under `KEY = "lantero_v1"` via `save()` (write) and a `load()` on boot.
  Nothing leaves the device. Related keys: `lantero_v1_corrupt` (corrupt-state quarantine),
  `lantero_v1_lastBackup`. JSON backups export/import from **Settings → Data**.
- **SPA routing** is a tab switch, not URLs: `TABS` (line ~1135) → `currentTab` → `go(tab)`
  → `renderNav()` + `renderView()`, which dispatches to `viewToday()`, `viewWeek()`,
  `viewMonth()`, `viewQuarter()`, `viewMissions()`, `viewDash()`, `viewSettings()`.
- **Missions** are the core unit — interest-wrapped, single-skill quests. Templates are
  inline data arrays (placeholders `{I}` interest, `{C}` child, etc.); `S.missions` holds
  instances with `status` (`skipped`/etc.).
- **PWA:** `manifest.webmanifest` + `icons/` allow home-screen install over HTTPS.
  **No service worker yet — no offline.**

## Conventions

- **Mutate-then-persist-then-render:** after changing `S`, call `save()` then `renderView()`
  (or `closeModal()` where a modal was open). Follow this exact order — see the existing
  handlers around lines 475–880.
- Helpers: `$(id)` = `getElementById`, `uid()` = new id, `todayYMD()` = date key.
- Keep everything in one file and dependency-free. No npm, no external scripts/CDNs, no
  network calls — those would break the local-first, no-telemetry promise.
- Match the terse existing style (short function names, minimal whitespace) rather than
  reformatting.

## Run / deploy

- **Run:** open `docs/index.html` directly, or serve the folder as a static site.
- **Deploy:** published via **GitHub Pages from `docs/`** on
  `github.com/Lantero-Academy/lantero-app` (branch `main`). Pushing to `main` deploys —
  **confirm the destination before pushing or deploying** (per workspace rule).
- **No tests, no `package.json`, no lint/build.** Verify changes by loading `docs/index.html`
  in a browser and exercising the affected tab. Use a private/incognito window or export a
  backup first so you don't clobber real `localStorage` data.

## Roadmap note

This vanilla single-file build is the **current** prototype for early friends-and-family
feedback. A **React + Vite + TypeScript refactor is planned** once feedback lands, so avoid
large speculative rearchitecting of `index.html` — favor small, targeted changes until the
refactor begins.
