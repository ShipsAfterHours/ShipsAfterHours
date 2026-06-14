---
template: dispatch.html
title: OpenAfterHours · After-hours dispatch
description: A personal dispatch from the maintainer of OpenAfterHours — open-source regulatory tools for the financial industry, built after hours.

# Masthead strip
issue: "№ 001 · Vol. I · 2026"
masthead_lead: OpenAfterHours
masthead_tail: Co.
dateline: Edinburgh · GMT · MIT licensed

# Meta-row
tagline: A personal dispatch from the maintainer of OpenAfterHours
cadence: Published continuously · ☾ Written after dark

# Lede
deck: From the desk · Letter from the maintainer
headline_lead: "Capital adequacy is a"
headline_emphasis: public good
headline_tail: ". The software for it should be too."
intro_long: >-
  I build open-source tools for the financial industry —
  quietly, after the day job. The premise is simple: banks that run the back-office cheaply can offer the public
  better products. The maths is well-defined; the software shouldn't be a
  moat.
intro_coda: >-
  A parallel practice, kept honest by being open, and kept warm by being
  shared.
byline: The Maintainer - Phil
read_time: 4 min

# // Now strip
now:
  - Working through PRA PS1/26
  - "Reading: On how best to utilise AI in development"
  - "Listening: The Pragmatic Engineer"

# Beliefs (4 columns, § 01 – § 04)
beliefs:
  - n: "01"
    head: Capital adequacy is a public good.
    body: >-
      Risk-Weighted Assets, IRB, the Standardised Approach — these define
      how safely a bank operates and how much it costs to hold a
      customer's mortgage. The arithmetic should be transparent and the
      implementations should be free.
  - n: "02"
    head: Cheap back-office, cheap products.
    body: >-
      Every line item that a bank pays a vendor for compliance computation
      is a line item the customer eventually pays. Open-source the
      computation, push the cost curve down, the saving lands somewhere
      real.
  - n: "03"
    head: Sustainable software, sustainable teams.
    body: >-
      Agile is not a ceremony — it's a way to ship for years without
      burning out. Small batches, honest tests, and code people are proud
      to maintain at 11pm on a Tuesday.
  - n: "04"
    head: Regulators are users, not adversaries.
    body: >-
      PRA, BCBS, EBA — these documents are an interface. Treat them like
      an API spec, write tests against them, and the rest follows.

# Project card
project:
  name: UK Credit Risk RWA Calculator
  tagline: High-performance Risk-Weighted Assets calculation for Basel 3.1 and CRR frameworks.
  repo_url: https://github.com/OpenAfterHours/rwa_calculator
  bullets:
    - { label: "Standardised + IRB", body: "F-IRB and A-IRB on top of the Standardised Approach." }
    - { label: "Polars-fast",        body: "50–100× over the equivalent pandas pipeline." }
    - { label: "c5,000 tests",       body: "Cross-checked against the regulator's worked examples." }
    - { label: "PRA PS1/26",         body: "Tracking the Basel 3.1 transposition for UK firms." }

# 8 formulas with their scatter positions, in render order.
# Each entry merges FORMULAS[i] with FORMULA_SCATTER[i] from the source.
formula_scatter:
  - { text: "K = LGD × Φ[√(1−R)⁻¹ × Φ⁻¹(PD) + √(R/(1−R)) × Φ⁻¹(0.999)] − PD × LGD", top: "6%",  left: "3%",  fs: 12, rot: -2.4 }
  - { text: "RWA = K × 12.5 × EAD",                                                  top: "14%", left: "62%", fs: 14, rot:  1.2 }
  - { text: "R = 0.12 × (1 − e⁻⁵⁰·ᴾᴰ)/(1 − e⁻⁵⁰) + 0.24 × [1 − (1 − e⁻⁵⁰·ᴾᴰ)/(1 − e⁻⁵⁰)]", top: "24%", left: "8%", fs: 11, rot: 2.0 }
  - { text: "b = (0.11852 − 0.05478 × ln(PD))²",                                     top: "32%", left: "42%", fs: 16, rot: -1.0 }
  - { text: "MA = (1 + (M − 2.5) × b) / (1 − 1.5 × b)",                              top: "40%", left: "74%", fs: 11, rot:  2.5 }
  - { text: "Φ(x) = ½[1 + erf(x/√2)]",                                               top: "48%", left: "2%",  fs: 13, rot: -2.0 }
  - { text: "EL = PD × LGD",                                                         top: "54%", left: "50%", fs: 10, rot:  1.5 }
  - { text: "RW = K × 12.5 × MA",                                                    top: "60%", left: "78%", fs: 12, rot: -2.5 }

# Project card — moonlit
project_moonlit:
  name: moonlit
  tagline: A uv-native Python zipapp builder — the build tooling that ships the regulatory work.
  repo_url: https://github.com/OpenAfterHours/moonlit
  docs_url: https://openafterhours.github.io/moonlit/
  bullets:
    - { label: "uv-native",        body: "Dependency graphs read from uv.lock, no pip round-trip." }
    - { label: "Single-file",      body: ".pyz per PEP 441 — one artifact, no virtualenv on target." }
    - { label: "Workspace-aware",  body: "Bundles transitive deps for uv workspaces automatically." }
    - { label: "Cross-version",    body: "--python-version flag for builds across interpreters." }

# Scatter for the moonlit panel — short tokens instead of formulas.
moonlit_scatter:
  - { text: "PEP 441",                  top: "8%",  left: "5%",  fs: 13, rot: -2.0 }
  - { text: "uv.lock",                  top: "16%", left: "60%", fs: 14, rot:  1.5 }
  - { text: "--python-version 3.13",    top: "26%", left: "8%",  fs: 11, rot:  2.2 }
  - { text: "app.pyz",                  top: "34%", left: "44%", fs: 16, rot: -1.0 }
  - { text: "DEFLATE",                  top: "42%", left: "72%", fs: 11, rot:  2.5 }
  - { text: "__main__.py",              top: "50%", left: "3%",  fs: 12, rot: -2.0 }
  - { text: "zipapp",                   top: "56%", left: "52%", fs: 10, rot:  1.5 }
  - { text: "0.2.0",                    top: "62%", left: "78%", fs: 12, rot: -2.5 }

# Project card — watchfire
project_watchfire:
  name: watchfire
  tagline: Static analysis for UK financial regulatory citations in Python — executable audit trails that run in CI.
  repo_url: https://github.com/OpenAfterHours/watchfire
  docs_url: https://openafterhours.club/watchfire/
  bullets:
    - { label: "@cites",              body: "Annotate functions with the CRR, PRA Rulebook, PS or SS rule they implement." }
    - { label: "watchfire check",     body: "Validates every citation against a versioned rulebook snapshot — non-zero exit in CI." }
    - { label: "Traceability matrix", body: "Reverse lookup grouping citations by article, as an audit deliverable." }
    - { label: "Zero overhead",       body: "@cites is a no-op — parsed citations attach to __watchfire__, no wrapping." }

# Scatter for the watchfire panel — short tokens.
watchfire_scatter:
  - { text: "@cites",             top: "8%",  left: "5%",  fs: 14, rot: -2.0 }
  - { text: "CRR Art. 153(1)(a)", top: "16%", left: "58%", fs: 12, rot:  1.5 }
  - { text: "watchfire check",    top: "26%", left: "8%",  fs: 13, rot:  2.2 }
  - { text: "PRA Rulebook",       top: "34%", left: "46%", fs: 15, rot: -1.0 }
  - { text: "__watchfire__",      top: "42%", left: "72%", fs: 11, rot:  2.5 }
  - { text: "PS1/26",             top: "50%", left: "3%",  fs: 12, rot: -2.0 }
  - { text: "matrix",             top: "56%", left: "52%", fs: 10, rot:  1.5 }
  - { text: "2024-07-09",         top: "62%", left: "78%", fs: 12, rot: -2.5 }

# Project card — mooring
project_mooring:
  name: mooring
  tagline: Git-free marimo notebook sharing for analyst teams — all sync over the GitHub API, no git on the machine.
  repo_url: https://github.com/OpenAfterHours/mooring
  docs_url: https://openafterhours.club/mooring/
  bullets:
    - { label: "Git-free",        body: "Pull, edit, and push marimo notebooks with nothing but Python 3.12 installed." }
    - { label: "GitHub API sync", body: "Per-file SHA writes — GitHub itself rejects anything that would clobber a teammate." }
    - { label: "Conflict-safe",   body: "Pull never overwrites local edits; conflicts are resolved per file, never silently." }
    - { label: "Frozen stack",    body: "polars, altair, plotly and more bundled into one .pyz — no pip at runtime." }

# Scatter for the mooring panel — short tokens.
mooring_scatter:
  - { text: "marimo",        top: "8%",  left: "5%",  fs: 14, rot: -2.0 }
  - { text: "mooring.pyz",   top: "16%", left: "58%", fs: 12, rot:  1.5 }
  - { text: "GitHub API",    top: "26%", left: "8%",  fs: 13, rot:  2.2 }
  - { text: "device code",   top: "34%", left: "46%", fs: 15, rot: -1.0 }
  - { text: "notebooks/",    top: "42%", left: "72%", fs: 11, rot:  2.5 }
  - { text: "blob SHA",      top: "50%", left: "3%",  fs: 12, rot: -2.0 }
  - { text: "Python 3.12",   top: "56%", left: "52%", fs: 10, rot:  1.5 }
  - { text: "no git",        top: "62%", left: "78%", fs: 12, rot: -2.5 }

# Project card — curfew
project_curfew:
  name: curfew
  tagline: Local-first Python dependency & module-boundary checker — offline architecture enforcement, no phone-home.
  repo_url: https://github.com/OpenAfterHours/curfew
  docs_url: https://openafterhours.club/curfew/
  bullets:
    - { label: "Module boundaries",       body: "Enforce which first-party modules may import which — dependency direction as code." }
    - { label: "Dependency validation",   body: "Flags undeclared, unused, and uv workspace-leaked third-party imports." }
    - { label: "Offline by construction", body: "No network, no telemetry; graphs render as Mermaid with no GraphViz binary." }
    - { label: "Zero runtime deps",       body: "uv tool install curfew pulls in nothing — the engine runs on the stdlib alone." }

# Scatter for the curfew panel — short tokens.
curfew_scatter:
  - { text: "curfew check",     top: "8%",  left: "5%",  fs: 14, rot: -2.0 }
  - { text: "[tool.curfew]",    top: "16%", left: "56%", fs: 12, rot:  1.5 }
  - { text: "--boundaries",     top: "26%", left: "8%",  fs: 13, rot:  2.2 }
  - { text: "import graph",     top: "34%", left: "46%", fs: 15, rot: -1.0 }
  - { text: "Mermaid",          top: "42%", left: "72%", fs: 11, rot:  2.5 }
  - { text: "workspace leak",   top: "50%", left: "3%",  fs: 12, rot: -2.0 }
  - { text: "stdlib-only",      top: "56%", left: "52%", fs: 10, rot:  1.5 }
  - { text: "uv tool install",  top: "62%", left: "78%", fs: 12, rot: -2.5 }

# Recent dispatches — newest first.
posts:
  - { url: "dispatches/2026-08-04-what-i-got-wrong-whats-next/",                     date: "2026-08-04", kicker: "Part 8", title: "What I Got Wrong, What's Next",                            read: "11 min" }
  - { url: "dispatches/2026-07-21-testing-a-regulatory-engine/",                     date: "2026-07-21", kicker: "Part 7", title: "Testing a Regulatory Engine",                              read: "13 min" }
  - { url: "dispatches/2026-07-07-crm-mofs-and-other-edge-case-archaeology/",        date: "2026-07-07", kicker: "Part 6", title: "CRM, MOFs, and Other Edge-Case Archaeology",               read: "14 min" }
  - { url: "dispatches/2026-06-23-the-output-floor-and-why-basel-31-bites/",         date: "2026-06-23", kicker: "Part 5", title: "The Output Floor and Why Basel 3.1 Bites",                 read: "14 min" }
  - { url: "dispatches/2026-06-09-building-with-an-agent-swarm/",                    date: "2026-06-09", kicker: "Part 4", title: "Building With an Agent Swarm",                             read: "13 min" }
  - { url: "dispatches/2026-05-26-risk-weights-are-not-a-lookup-table/",             date: "2026-05-26", kicker: "Part 3", title: "Risk Weights Are Not a Lookup Table",                      read: "13 min" }
  - { url: "dispatches/2026-05-12-the-pipeline/",                                    date: "2026-05-12", kicker: "Part 2", title: "The Pipeline: Why Regulation Forced an Immutable Design",  read: "12 min" }
  - { url: "dispatches/2026-04-28-building-a-uk-basel-31-rwa-calculator-in-public/", date: "2026-04-28", kicker: "Part 1", title: "Building a UK Basel 3.1 RWA Calculator in Public",         read: "5 min" }

# Footer links
links:
  - { label: "github · personal",        url: "https://github.com/luckyphil122",                  external: true }
  - { label: "github · openafterhours",  url: "https://github.com/OpenAfterHours",                 external: true }
  - { label: "github · moonlit",         url: "https://github.com/OpenAfterHours/moonlit",         external: true }
  - { label: "github · watchfire",       url: "https://github.com/OpenAfterHours/watchfire",       external: true }
  - { label: "github · mooring",         url: "https://github.com/OpenAfterHours/mooring",         external: true }
  - { label: "github · curfew",          url: "https://github.com/OpenAfterHours/curfew",          external: true }
  - { label: "email",                    url: "mailto:hello@openafterhours.dev",                   external: false }
---
