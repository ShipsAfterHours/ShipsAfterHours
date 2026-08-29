# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal static site — the "OpenAfterHours · After-hours dispatch" — built with [Zensical](https://zensical.org/docs/) (a static site generator from the MkDocs/Material team) and deployed to GitHub Pages. The repo is **content + theme only**; the software it writes about (the RWA calculator, `watchfire`, `moonlit`, `mooring`, `curfew`) lives in separate repos under the `OpenAfterHours` GitHub org. There is no application code here to test.

## Commands

Dependencies are managed with `uv` (not pip). Python >= 3.12.

```bash
uv sync                  # install/update the environment from uv.lock
uv run zensical serve    # build + live-reload dev server (use this while editing)
uv run zensical build    # one-shot build into ./site (gitignored)
```

CI (`.github/workflows/deploy.yml`) runs `uv sync --frozen` then `uv run zensical build` on every push to `main`, uploading `./site` to GitHub Pages. Pushing to `main` deploys; there is no separate publish step.

## Architecture

Three layers, configured by `zensical.toml`:

1. **`docs/`** — content (Markdown) and assets. `docs_dir` is the root for all relative paths in config and templates.
2. **`overrides/`** — custom Jinja2 templates (`custom_dir`). These are full-page HTML templates, **not** Material theme partial overrides.
3. **`docs/stylesheets/`** — CSS layered on top of Zensical defaults via `extra_css`.

`zensical.toml` also pins the explicit `nav`, enabled `features`, fonts, the light/dark `palette`, and Markdown extensions (pymdownx superfences, admonitions, footnotes, etc.). Edit it to change site-wide behavior.

### The data-driven homepage (the key thing to understand)

`docs/index.md` is **almost entirely YAML front matter with an empty body**, and it is the only page in the site. It selects `template: dispatch.html`, and every visible element — the `terminal:` block, masthead, beliefs columns, the single `elsewhere` card, its `elsewhere_scatter` token background, and footer `links` — is a structured field read by `overrides/dispatch.html` via `{{ page.meta.* }}`.

This means: **to change page content, edit the front matter in `docs/index.md`, not the HTML.** Edit `overrides/dispatch.html` only to change structure/markup. Adding a section requires touching both: a new front-matter block *and* a matching template section.

The page has two layers. The `terminal:` block renders a working shell over everything, gated behind `html.js` (see `docs/stylesheets/terminal.css`); its `bail` button and `read` command call `handOver()`, which dissolves the terminal and reveals the article beneath in `data-step` order. With JavaScript off the terminal never appears and the article is simply the page — so the article must stand on its own, and is the only thing crawlers see.

The projects themselves are catalogued on the OpenAfterHours org page; the `elsewhere` block points at it rather than restating it. Training Den's repo (`gooseup/thecoachesapp`) is **private** — never link to it, link to <https://trainingden.app>.

### Styling

`docs/stylesheets/colors_and_type.css` is the design system — all colors, type, spacing, radii, and motion are CSS custom properties prefixed `--oah-*` (brand) or semantic (`--bg`, `--fg`, `--card`, …) using `light-dark()`. `docs/stylesheets/page.css` holds homepage layout. Use the existing tokens rather than hardcoding values; the same token vocabulary is mirrored in the OpenAfterHours apps (see the header comment in `colors_and_type.css`).
