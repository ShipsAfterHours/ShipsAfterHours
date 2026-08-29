# Hi, I'm Phil 👋

**I learn things by building them.** Bank capital, swim training, Python packaging — the domains have nothing to do with each other; the practice is identical. Pick something I don't understand, build the thing properly, and find out where the specification goes quiet.

Most of it happens after the day job under the [**OpenAfterHours**](https://github.com/OpenAfterHours) banner, alongside a swarm of [Claude Code](https://www.anthropic.com/claude-code) agents — under one rule: the model may interpret, organise and suggest, but it may not assert a number.

💻 **[openafterhours.club →](https://shipsafterhours.github.io/ShipsAfterHours/)** — the landing page is a working shell. Type `learn`, `ai` or `projects`, or skip it and read the page.

## Projects

All under the [OpenAfterHours](https://github.com/OpenAfterHours) org, with docs at [openafterhours.club](https://openafterhours.club/).

| Project | What it does |
| --- | --- |
| [**abeam**](https://github.com/OpenAfterHours/abeam) | One window for an AI coding session — the agent hosted in a pty pane, with the git worktree, the file it just wrote and a shell beside it. Rust. |
| [**kedge**](https://github.com/OpenAfterHours/kedge) | Turns manual Excel processes into reviewable, reproducible [marimo](https://marimo.io) runbooks, with an AI copilot held to a controlled tool surface. |
| [**rwa_calculator**](https://github.com/OpenAfterHours/rwa_calculator) | High-performance, PRA PS1/26-compliant credit-risk RWA calculator (Standardised + F-IRB/A-IRB), built with Python and Polars. · [docs](https://openafterhours.club/rwa_calculator/) |
| [**watchfire**](https://github.com/OpenAfterHours/watchfire) | Static analysis for UK financial regulatory citations in Python — executable audit trails that run in CI. · [docs](https://openafterhours.club/watchfire/) |
| [**curfew**](https://github.com/OpenAfterHours/curfew) | Local-first Python dependency & module-boundary checker — offline architecture enforcement, no phone-home. · [docs](https://openafterhours.club/curfew/) |
| [**moonlit**](https://github.com/OpenAfterHours/moonlit) | uv-native CLI that bundles a Python project (or uv workspace) into a single self-contained zipapp per PEP 441. · [docs](https://openafterhours.club/moonlit/) |
| [**mooring**](https://github.com/OpenAfterHours/mooring) | Git-free [marimo](https://marimo.io) notebook sharing for analyst teams — all sync over the GitHub API, no git on the machine. · [docs](https://openafterhours.club/mooring/) |

## About this repository

This repo doubles as my GitHub profile and the source for my personal site — built with [Zensical](https://zensical.org) and deployed to GitHub Pages on every push to `main`.

- **Content** lives in `docs/` — a single data-driven page (`docs/index.md`, all content in front matter).
- **Theme** — custom Jinja templates in `overrides/`, design tokens and styles in `docs/stylesheets/`.

```bash
uv sync                  # install dependencies (needs uv, Python >= 3.12)
uv run zensical serve    # live-reload preview at a local URL
uv run zensical build    # static build into ./site
```

## Elsewhere

📫 org [@OpenAfterHours](https://github.com/OpenAfterHours)

---

<sub>© 2026 OpenAfterHours · Written after dark from Edinburgh. ☾</sub>
