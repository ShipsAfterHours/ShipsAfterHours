---
template: dispatch.html
title: OpenAfterHours · After-hours dispatch
description: A personal dispatch from the maintainer of OpenAfterHours — open-source regulatory tools for the financial industry, built after hours.

# ─────────────────────────────────────────────────────────────
# The landing terminal (overrides/dispatch.html renders this over
# the page; docs/stylesheets/terminal.css styles it).
#
# A working shell — Tab completes, ↑↓ recall history, → accepts the
# dim suggestion. With JavaScript off it never appears and this page
# is simply the page.
#
# `lines` accept a small set of inline spans:
#   k = orange   w = white   d = dim   g = green   b = blue   r = red
# An empty string is a blank line.
# ─────────────────────────────────────────────────────────────
terminal:
  ps1: "openafterhours ~ $"
  bar: "openafterhours.club — sh"
  bail: "skip the terminal · read the page →"
  chips: [help, projects, bank, swim, writing, hire, cv]

  boot:
    - { t: "openafterhours.club · sh · after hours", cls: d, speed: 10 }
    - ""
    - { t: "Hi. I'm Phil.", cls: w, speed: 55 }
    - ""
    - { t: "I build software after the day job — regulatory capital engines for", speed: 12 }
    - { t: "banks, developer tooling for Python, and a session planner that", speed: 12 }
    - { t: "swimming coaches use at the poolside.", speed: 12 }
    - ""
    - { t: "This prompt works. Type <span class=\"k\">help</span>, or click something below.", cls: d, speed: 10 }

  # `open <name>` targets
  urls:
    rwa: https://github.com/OpenAfterHours/rwa_calculator
    swim: https://trainingden.app
    coaches: https://github.com/gooseup/thecoachesapp
    watchfire: https://github.com/OpenAfterHours/watchfire
    moonlit: https://github.com/OpenAfterHours/moonlit
    mooring: https://github.com/OpenAfterHours/mooring
    curfew: https://github.com/OpenAfterHours/curfew
    github: https://github.com/OpenAfterHours
    gooseup: https://github.com/gooseup

  commands:
    - name: whoami
      blurb: the short version
      lines:
        - ""
        - '<span class="w">Phil Harrison</span> <span class="d">— Edinburgh, GMT</span>'
        - ""
        - "I build software after the day job. Regulatory capital engines for"
        - "banks, developer tooling for Python, and a session planner that"
        - "swimming coaches use at the poolside."
        - ""
        - "The domains have nothing to do with each other. The practice is"
        - "identical: small batches, honest tests, numbers the machine"
        - '<span class="k">computes</span> rather than <span class="k">asserts</span>, and code that explains itself'
        - "to whoever reads it next."

    - name: projects
      blurb: everything, in one table
      lines:
        - ""
        - '<span class="d">NAME              WHERE         WHAT</span>'
        - '<span class="k">rwa_calculator</span>    <span class="d">python</span>        UK Basel 3.1 / CRR risk-weighted assets engine'
        - '<span class="k">thecoachesapp</span>     <span class="g">live</span>          Training Den — session planning for swim clubs'
        - '<span class="k">watchfire</span>         <span class="d">python</span>        regulatory citations, checkable in CI'
        - '<span class="k">moonlit</span>           <span class="d">python</span>        uv-native zipapp builder'
        - '<span class="k">mooring</span>           <span class="d">python</span>        git-free notebook sharing over the GitHub API'
        - '<span class="k">curfew</span>            <span class="d">python</span>        local-first dependency &amp; boundary checking'
        - ""
        - '<span class="d">try</span> <span class="k">bank</span><span class="d">,</span> <span class="k">swim</span> <span class="d">or</span> <span class="k">tools</span> <span class="d">for detail ·</span> <span class="k">open &lt;name&gt;</span> <span class="d">to visit one</span>'

    - name: bank
      blurb: the regulatory work
      lines:
        - ""
        - '<span class="w">UK Credit Risk RWA Calculator</span>'
        - "High-performance Risk-Weighted Assets calculation for Basel 3.1 and CRR."
        - ""
        - '<span class="row"><span class="rk">approaches</span><span class="rv">Standardised, F-IRB and A-IRB</span></span>'
        - '<span class="row"><span class="rk">performance</span><span class="rv">50–100× the equivalent pandas pipeline (Polars)</span></span>'
        - '<span class="row"><span class="rk">tests</span><span class="rv">c5,000, cross-checked against the regulator''s worked examples</span></span>'
        - '<span class="row"><span class="rk">tracking</span><span class="rv">PRA PS1/26 — the Basel 3.1 transposition for UK firms</span></span>'
        - ""
        - '<span class="w">watchfire</span>'
        - "Regulatory citations as annotations that fail the build when they rot."
        - ""
        - '  <span class="g">@cites</span>(<span class="k">"CRR Art. 153(1)(a)"</span>)'
        - '  <span class="d">def</span> corporate_rw(pd, lgd, m): ...'
        - ""
        - '  <span class="d">$</span> watchfire check'
        - '  <span class="g">→</span> checked 47 citations · no issues found'
        - ""
        - '<span class="d">→</span> <a href="https://github.com/OpenAfterHours/rwa_calculator" target="_blank" rel="noopener">github.com/OpenAfterHours/rwa_calculator</a>'

    - name: swim
      blurb: Training Den
      lines:
        - ""
        - '<span class="w">Training Den</span> <span class="d">·</span> <span class="g">live</span> <span class="d">· gooseup/thecoachesapp</span>'
        - "A coach-first session planner for British swimming clubs."
        - ""
        - "A coach describes a session in normal language, on the way to the pool:"
        - ""
        - '  <span class="b">coach ›</span> <span class="w">"three rounds. twelve by fifty, twelve by seventy-five,</span>'
        - '          <span class="w">twelve by hundred, twelve by two hundred. all A2,</span>'
        - '          <span class="w">twenty seconds rest. the hundreds stay IM."</span>'
        - ""
        - '  <span class="d">draft</span> <span class="g">→</span> 3 rounds · 12 sets · 2 assumptions flagged for review'
        - '  <span class="d">check</span> <span class="g">→</span> <span class="k">15,300 m</span> — computed by the application, never by the model'
        - ""
        - "That last line is the whole design. The model may interpret, organise"
        - "and suggest; it may not assert a number. Totals are calculated"
        - "deterministically and tested against worked examples — the same rule"
        - "as the risk engine, in a wetter building."
        - ""
        - '<span class="d">→</span> <a href="https://trainingden.app" target="_blank" rel="noopener">trainingden.app</a> <span class="d">·</span> <a href="https://github.com/gooseup/thecoachesapp" target="_blank" rel="noopener">github.com/gooseup/thecoachesapp</a>'

    - name: tools
      blurb: the small Python tooling
      lines:
        - ""
        - '<span class="row"><span class="rk">moonlit</span><span class="rv">uv-native zipapp builder. One <span class="k">.pyz</span>, no virtualenv on the target.</span></span>'
        - '<span class="row"><span class="rk">mooring</span><span class="rv">Git-free marimo notebook sharing — all sync over the GitHub API.</span></span>'
        - '<span class="row"><span class="rk">curfew</span><span class="rv">Local-first dependency and module-boundary checks. No network, no telemetry.</span></span>'
        - ""
        - '<span class="d">Mostly things I needed once, then made properly so the next person</span>'
        - '<span class="d">could have them for free.</span>'

    - name: writing
      blurb: the dispatches
      lines:
        - ""
        - '<span class="d">2026-08-04</span>  <span class="k">Part 8</span>  <span class="w">What I Got Wrong, What''s Next</span> <span class="d">· 11 min</span>'
        - '<span class="d">2026-07-21</span>  <span class="k">Part 7</span>  <span class="w">Testing a Regulatory Engine</span> <span class="d">· 13 min</span>'
        - '<span class="d">2026-07-07</span>  <span class="k">Part 6</span>  <span class="w">CRM, MOFs, and Other Edge-Case Archaeology</span> <span class="d">· 14 min</span>'
        - '<span class="d">2026-06-23</span>  <span class="k">Part 5</span>  <span class="w">The Output Floor and Why Basel 3.1 Bites</span> <span class="d">· 14 min</span>'
        - '<span class="d">2026-06-09</span>  <span class="k">Part 4</span>  <span class="w">Building With an Agent Swarm</span> <span class="d">· 13 min</span>'
        - '<span class="d">2026-05-26</span>  <span class="k">Part 3</span>  <span class="w">Risk Weights Are Not a Lookup Table</span> <span class="d">· 13 min</span>'
        - '<span class="d">2026-05-12</span>  <span class="k">Part 2</span>  <span class="w">The Pipeline</span> <span class="d">· 12 min</span>'
        - '<span class="d">2026-04-28</span>  <span class="k">Part 1</span>  <span class="w">Building a UK Basel 3.1 RWA Calculator in Public</span> <span class="d">· 5 min</span>'
        - ""
        - '<span class="d">run</span> <span class="k">read</span> <span class="d">to open the archive properly</span>'

    # NOTE: rewrite this one in your own words — it is the block a hiring
    # manager will read twice.
    - name: hire
      blurb: what I'm looking for
      lines:
        - ""
        - '<span class="row"><span class="rk">now</span><span class="rv">Software engineering in financial services, Edinburgh.</span></span>'
        - '<span class="row"><span class="rk">after hours</span><span class="rv">Five open-source repos and one live product, shipped solo.</span></span>'
        - '<span class="row"><span class="rk">good at</span><span class="rv">Turning a dense specification into tested, boring, correct code.</span></span>'
        - '<span class="row"><span class="rk">looking for</span><span class="rv">Teams that write things down, test what they ship, and can explain their numbers to someone who did not write them.</span></span>'
        - '<span class="row"><span class="rk">reach me</span><span class="rv"><a href="mailto:hello@openafterhours.dev">hello@openafterhours.dev</a></span></span>'

    - name: cv
      blurb: the two-page version
      lines:
        - ""
        - '<span class="d">Harrison_P_CV_2026_v7_FINAL(2).pdf — page 1 of 2</span>'
        - ""
        - '  <span class="d">PROFESSIONAL PROFILE</span>'
        - '  <span class="d">A results-driven and detail-oriented software engineer with a</span>'
        - '  <span class="d">proven track record of delivering high-quality solutions in</span>'
        - '  <span class="d">fast-paced environments. Excellent communicator, comfortable</span>'
        - '  <span class="d">engaging with stakeholders at all levels.</span>'
        - ""
        - '  <span class="d">KEY SKILLS</span>'
        - '  <span class="d">Python · Attention to detail · SQL · Team player · CI/CD ·</span>'
        - '  <span class="d">Stakeholder management · Works well under pressure · Excel</span>'
        - ""
        - '  <span class="d">INTERESTS</span>'
        - '  <span class="d">Reading, technology, </span><span class="k">swimming</span><span class="d">, and spending time with family.</span>'
        - ""
        - '<span class="r">note</span> — the word <span class="k">swimming</span> appears once, under Interests,'
        - 'between "technology" and "family". There is a live application'
        - 'behind that word, used by coaches at a poolside, and the format'
        - 'had no way to tell you. Run <span class="k">swim</span>.'

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
