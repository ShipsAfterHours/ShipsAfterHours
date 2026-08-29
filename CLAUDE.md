# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal static site — Phil Harrison / OpenAfterHours — built with [Zensical](https://zensical.org/docs/) (a static site generator from the MkDocs/Material team) and deployed to GitHub Pages. The repo is **content + theme only**; the software it writes about (`abeam`, the RWA calculator, `kedge`, `watchfire`, `moonlit`, `mooring`, `curfew`) lives in separate repos under the `OpenAfterHours` GitHub org. There is no application code here to test.

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

`docs/index.md` is **almost entirely YAML front matter with an empty body**, and it is the only page in the site. It selects `template: home.html`, and every visible element — the `terminal:` block, the lede, `learning`, `agents`, `built`, `practice` and footer `links` — is a structured field read by `overrides/home.html` via `{{ page.meta.* }}`.

This means: **to change page content, edit the front matter in `docs/index.md`, not the HTML.** Edit `overrides/home.html` only to change structure/markup. Adding a section requires touching both: a new front-matter block *and* a matching template section.

The page has two layers. The `terminal:` block renders a working shell over everything, gated behind `html.js` (see `docs/stylesheets/terminal.css`); its `bail` button and `read` command call `handOver()`, which dissolves the terminal and reveals the page beneath in `data-step` order. With JavaScript off the terminal never appears and the page below is simply the page — so it must stand on its own, and is the only thing crawlers see.

**The one coupling between the two layers.** `handOver()` retypes four specific elements — `#lede-deck`, `#lede-head`, `#lede-body`, `#lede-coda` — and reveals `.reveal[data-step="1"]` through `"5"` in order. Any restructuring of the page must keep those four ids and that step range, or edit the `LEDE` / `LEDE_SPEED` arrays to match. It fails silently otherwise.

**What the page says.** The through-line is *"I learn things by building them — the domains are unrelated, the practice is identical."* Keep it domain-general: banking is one of several examples (swimming, Python packaging), never the frame. The `learning:` block is the one thing worth keeping current; a stale `asof` date there is worse than no date.

The `built:` block lists every project at equal weight — no domain leads. It is the one thing that goes stale when a repo is added: the list, `built.note`'s count, the `hire` and `projects` terminal commands, `terminal.urls`, and the README table all have to move together. `status:` drives the chip colour via `.ps-<status>`. The org page catalogues them properly; the `actions:` buttons point at it. Training Den's repo (`gooseup/thecoachesapp`) is **private** — never link to it, link to <https://trainingden.app>.

### Styling

`docs/stylesheets/colors_and_type.css` is the design system — all colors, type, spacing, radii, and motion are CSS custom properties prefixed `--oah-*` (brand) or semantic (`--bg`, `--fg`, `--card`, …) using `light-dark()`. `docs/stylesheets/page.css` holds homepage layout and introduces no hex values of its own. Use the existing tokens rather than hardcoding values; the same token vocabulary is mirrored in the OpenAfterHours apps (see the header comment in `colors_and_type.css`).

The terminal overlay is always dark. The page beneath follows the visitor's system preference — `page.css` sets `color-scheme: light dark` on the root so the `light-dark()` tokens resolve both ways, so check any new colour in both.
