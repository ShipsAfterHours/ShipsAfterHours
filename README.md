# Hi, I'm Phil 👋

I build open-source regulatory tools for the financial industry — quietly, after the day job, under the [**OpenAfterHours**](https://github.com/OpenAfterHours) banner.

The premise is simple: **capital adequacy is a public good, and the software for it should be too.** Banks that hold the right capital and run a cheap back-office can offer the public better products. The maths is well-defined; the software shouldn't be a moat.

📡 **[Read the After-Hours Dispatch →](https://shipsafterhours.github.io/ShipsAfterHours/)** — a running letter on building these tools: the regulation, the engineering, and what it's like driving the work through a swarm of [Claude Code](https://www.anthropic.com/claude-code) agents.

## Projects

All under the [OpenAfterHours](https://github.com/OpenAfterHours) org, with docs at [openafterhours.club](https://openafterhours.club/).

| Project | What it does |
| --- | --- |
| [**rwa_calculator**](https://github.com/OpenAfterHours/rwa_calculator) | High-performance, PRA PS1/26-compliant credit-risk RWA calculator (Standardised + F-IRB/A-IRB), built with Python and Polars. · [docs](https://openafterhours.club/rwa_calculator/) |
| [**watchfire**](https://github.com/OpenAfterHours/watchfire) | Static analysis for UK financial regulatory citations in Python — executable audit trails that run in CI. · [docs](https://openafterhours.club/watchfire/) |
| [**curfew**](https://github.com/OpenAfterHours/curfew) | Local-first Python dependency & module-boundary checker — offline architecture enforcement, no phone-home. · [docs](https://openafterhours.club/curfew/) |
| [**moonlit**](https://github.com/OpenAfterHours/moonlit) | uv-native CLI that bundles a Python project (or uv workspace) into a single self-contained zipapp per PEP 441. · [docs](https://openafterhours.club/moonlit/) |
| [**mooring**](https://github.com/OpenAfterHours/mooring) | Git-free [marimo](https://marimo.io) notebook sharing for analyst teams — all sync over the GitHub API, no git on the machine. · [docs](https://openafterhours.club/mooring/) |

## About this repository

This repo doubles as my GitHub profile and the source for the **After-Hours Dispatch** — a static site built with [Zensical](https://zensical.org) and deployed to GitHub Pages on every push to `main`.

- **Content** lives in `docs/` — the data-driven homepage (`docs/index.md`, all content in front matter) and dispatch posts under `docs/dispatches/`.
- **Theme** — custom Jinja templates in `overrides/`, design tokens and styles in `docs/stylesheets/`.

```bash
uv sync                  # install dependencies (needs uv, Python >= 3.12)
uv run zensical serve    # live-reload preview at a local URL
uv run zensical build    # static build into ./site
```

## Elsewhere

📫 [hello@openafterhours.dev](mailto:hello@openafterhours.dev) · personal GitHub [@luckyphil122](https://github.com/luckyphil122) · org [@OpenAfterHours](https://github.com/OpenAfterHours)

---

<sub>© 2026 OpenAfterHours · Written after dark from Edinburgh. ☾</sub>
