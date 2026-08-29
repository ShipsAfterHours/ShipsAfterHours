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
  chips: [help, projects, bank, swim, tools, hire, cv]

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
    watchfire: https://github.com/OpenAfterHours/watchfire
    moonlit: https://github.com/OpenAfterHours/moonlit
    mooring: https://github.com/OpenAfterHours/mooring
    curfew: https://github.com/OpenAfterHours/curfew
    github: https://github.com/OpenAfterHours
    gooseup: https://github.com/gooseup
    linkedin: https://www.linkedin.com/in/phil-harrison-859a0bb8/

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
        - '<span class="k">trainingden</span>       <span class="g">live</span>          Training Den — session planning for swim clubs'
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
        - '<span class="w">Training Den</span> <span class="d">·</span> <span class="g">live</span> <span class="d">· a closed repo, an open product</span>'
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
        - '<span class="d">→</span> <a href="https://trainingden.app" target="_blank" rel="noopener">trainingden.app</a>'

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
        - '<span class="row"><span class="rk">reach me</span><span class="rv"><a href="https://www.linkedin.com/in/phil-harrison-859a0bb8/" target="_blank" rel="noopener">linkedin.com/in/phil-harrison</a> <span class="d">— or</span> <span class="k">open linkedin</span></span></span>'

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
read_time: 1 min

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

# ─────────────────────────────────────────────────────────────
# Where the work lives. The projects are catalogued on the
# OpenAfterHours org page — this block points at it rather than
# restating it. Rendered by the `.feature.elsewhere` section.
# ─────────────────────────────────────────────────────────────
elsewhere:
  deck: Elsewhere · Where the work lives
  head_lead: "The projects live at"
  head_emphasis: OpenAfterHours
  head_tail: "."
  body: >-
    Six repositories — a Basel 3.1 risk-weighted assets engine, a
    regulatory citation checker that fails the build when a citation
    rots, and the small Python tooling that ships them. They are
    catalogued properly over there rather than restated here.
  coda: >-
    One is not open source. Training Den is a live product used by
    swimming clubs, so the application itself is the only place to
    see it working.
  actions:
    - { label: "OpenAfterHours →", url: "https://openafterhours.github.io/", primary: true }
    - { label: "Training Den · live", url: "https://trainingden.app", primary: false }

# Scatter for the elsewhere panel — the repo names, no descriptions.
elsewhere_scatter:
  - { text: "rwa_calculator",  top: "8%",  left: "5%",  fs: 14, rot: -2.0 }
  - { text: "Basel 3.1",       top: "16%", left: "60%", fs: 12, rot:  1.5 }
  - { text: "watchfire",       top: "26%", left: "8%",  fs: 13, rot:  2.2 }
  - { text: "moonlit",         top: "34%", left: "48%", fs: 16, rot: -1.0 }
  - { text: "mooring",         top: "42%", left: "74%", fs: 11, rot:  2.5 }
  - { text: "curfew",          top: "50%", left: "3%",  fs: 12, rot: -2.0 }
  - { text: "trainingden",     top: "56%", left: "52%", fs: 10, rot:  1.5 }
  - { text: "after hours",     top: "62%", left: "78%", fs: 12, rot: -2.5 }

# Footer links
links:
  - { label: "github · personal",        url: "https://github.com/luckyphil122",                     external: true }
  - { label: "github · openafterhours",  url: "https://github.com/OpenAfterHours",                   external: true }
  - { label: "training den",             url: "https://trainingden.app",                             external: true }
  - { label: "linkedin",                 url: "https://www.linkedin.com/in/phil-harrison-859a0bb8/", external: true }
---
