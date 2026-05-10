---
template: dispatch.html
title: OpenAfterHours · After-hours dispatch
description: A personal dispatch from the maintainer of OpenAfterHours — open-source regulatory tools for the financial industry, built after hours.

# Masthead strip
issue: "№ 001 · Vol. I · 2026"
masthead_lead: The After-Hours
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
  I build open-source regulatory tools for the financial industry —
  quietly, after the day job. The premise is simple: banks that hold the
  right capital and run the back-office cheaply can offer the public
  better products. The maths is well-defined; the software shouldn't be a
  moat.
intro_coda: >-
  A parallel practice, kept honest by being open, and kept warm by being
  shared.
byline: The Maintainer - Phil
read_time: 4 min

# // Now strip
now:
  - Working through PRA PS1/26 mapping for the SA module.
  - "Reading: Bank of England SS9/17, on internal model governance."
  - "Listening: shipping forecasts, mostly."

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
  - { label: "email",                    url: "mailto:hello@openafterhours.dev",                   external: false }
---
