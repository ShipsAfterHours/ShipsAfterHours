---
template: home.html
title: Phil Harrison · OpenAfterHours
description: I learn things by building them. Open-source Python tooling, a Basel 3.1 risk engine and a session planner for swimming clubs — built after the day job, mostly alongside a swarm of coding agents.

# ─────────────────────────────────────────────────────────────
# The landing terminal (overrides/home.html renders this over
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
  chips: [help, learn, ai, projects, swim, hire, cv]

  boot:
    - { t: "openafterhours.club · sh · after hours", cls: d, speed: 10 }
    - ""
    - { t: "Hi. I'm Phil.", cls: w, speed: 55 }
    - ""
    - { t: "I learn things by building them. A capital engine for banks, a session", speed: 12 }
    - { t: "planner that swimming coaches use at the poolside, and the tooling I", speed: 12 }
    - { t: "wanted for working with coding agents. The domains are unrelated; the", speed: 12 }
    - { t: "practice is identical.", speed: 12 }
    - ""
    - { t: "This prompt works. Type <span class=\"k\">help</span>, or click something below.", cls: d, speed: 10 }

  # `open <name>` targets
  urls:
    abeam: https://github.com/OpenAfterHours/abeam
    kedge: https://github.com/OpenAfterHours/kedge
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
        - '<span class="w">I learn things by building them.</span>'
        - ""
        - "Bank capital, swim training, Python packaging. The domains have"
        - "nothing to do with each other. The practice is identical: pick"
        - "something I don't understand, build it properly, and find out"
        - "where the specification goes quiet."
        - ""
        - "Most of that now happens alongside a swarm of coding agents. They"
        - '<span class="k">interpret</span>, organise and suggest; they never <span class="k">assert</span> a number.'
        - ""
        - '<span class="d">try</span> <span class="k">learn</span> <span class="d">for what I''m chewing on, or</span> <span class="k">ai</span> <span class="d">for how that actually works</span>'

    - name: learn
      blurb: what I'm chewing on right now
      lines:
        - ""
        - '<span class="d">August 2026</span>'
        - ""
        - '<span class="row"><span class="rk">agents</span><span class="rv">Orchestrating swarms of coding agents — plan, fan out, review, merge. The fan-out is the cheap part; the review step is where the value is.</span></span>'
        - '<span class="row"><span class="rk">polars</span><span class="rv">Query-plan internals. Why the 50–100× speed-up happens, not just that it does.</span></span>'
        - '<span class="row"><span class="rk">swimming</span><span class="rv">Training periodisation, from coaches who have been doing it for thirty years.</span></span>'
        - '<span class="row"><span class="rk">regulation</span><span class="rv">PRA PS1/26 — the UK Basel 3.1 transposition, and where its worked examples disagree with the text.</span></span>'
        - ""
        - '<span class="d">None of these are my job. That is rather the point — I pick something</span>'
        - '<span class="d">I don''t understand, build the thing, and find out what the spec left out.</span>'

    - name: ai
      blurb: how the agents actually get used
      lines:
        - ""
        - '<span class="w">Working with agents</span>'
        - ""
        - '<span class="row"><span class="rk">the loop</span><span class="rv">plan → fan out → review → merge. Running several agents at once is easy and cheap. Reviewing what they produce is the job.</span></span>'
        - '<span class="row"><span class="rk">the rule</span><span class="rv">The model may interpret, organise and suggest. It may not assert a number.</span></span>'
        - '<span class="row"><span class="rk">the window</span><span class="rv"><span class="k">abeam</span> — the agent in a pty pane, with the git worktree, the file it just wrote and a shell beside it. A watcher drives the right-hand side, so it always shows what the agent just did. Written in Rust; used daily against Claude Code.</span></span>'
        - ""
        - "In Training Den, a coach describes a session in their own words and"
        - "the model drafts it. The application then computes the distance:"
        - ""
        - '  <span class="d">draft</span> <span class="g">→</span> 3 rounds × 2,050 m · 12 sets · 2 assumptions flagged'
        - '  <span class="d">check</span> <span class="g">→</span> <span class="k">6,150 m</span> — calculated and tested against worked examples'
        - ""
        - "Same rule in the risk engine, in a drier building. If a computed"
        - "number is wrong you can find out why. If a model asserted it, you"
        - "cannot — and in both of those buildings, that matters."
        - ""
        - '<span class="d">→</span> <span class="k">open abeam</span> <span class="d">for the window I work in.</span>'

    - name: projects
      blurb: everything, in one table
      lines:
        - ""
        - '<span class="d">NAME              WHERE         WHAT</span>'
        - '<span class="k">trainingden</span>       <span class="g">live</span>          Training Den — session planning for swim clubs'
        - '<span class="k">abeam</span>             <span class="d">rust</span>          one window for an AI coding session'
        - '<span class="k">rwa_calculator</span>    <span class="d">python</span>        UK Basel 3.1 / CRR risk-weighted assets engine'
        - '<span class="k">kedge</span>             <span class="d">python</span>        Excel processes into reviewable marimo runbooks'
        - '<span class="k">watchfire</span>         <span class="d">python</span>        regulatory citations, checkable in CI'
        - '<span class="k">moonlit</span>           <span class="d">python</span>        uv-native zipapp builder'
        - '<span class="k">mooring</span>           <span class="d">python</span>        git-free notebook sharing over the GitHub API'
        - '<span class="k">curfew</span>            <span class="d">python</span>        local-first dependency &amp; boundary checking'
        - ""
        - '<span class="d">try</span> <span class="k">swim</span><span class="d">,</span> <span class="k">bank</span><span class="d">,</span> <span class="k">ai</span> <span class="d">or</span> <span class="k">tools</span> <span class="d">for detail ·</span> <span class="k">open &lt;name&gt;</span> <span class="d">to visit one</span>'

    - name: swim
      blurb: Training Den
      lines:
        - ""
        - '<span class="w">Training Den</span> <span class="d">·</span> <span class="g">live</span> <span class="d">· a closed repo, an open product</span>'
        - "A coach-first session planner for British swimming clubs."
        - ""
        - "A coach describes a session in normal language, on the way to the pool:"
        - ""
        - '  <span class="b">coach ›</span> <span class="w">"three rounds. twelve by fifty, six by seventy-five,</span>'
        - '          <span class="w">six by hundred, two by two hundred. all A2,</span>'
        - '          <span class="w">twenty seconds rest. the hundreds stay IM."</span>'
        - ""
        - '  <span class="d">draft</span> <span class="g">→</span> 3 rounds × 2,050 m · 12 sets · 2 assumptions flagged'
        - '  <span class="d">check</span> <span class="g">→</span> <span class="k">6,150 m</span> — computed by the application, never by the model'
        - ""
        - "That last line is the whole design. The model may interpret, organise"
        - "and suggest; it may not assert a number. Totals are calculated"
        - "deterministically and tested against worked examples — the same rule"
        - "as the risk engine, in a wetter building."
        - ""
        - '<span class="d">→</span> <a href="https://trainingden.app" target="_blank" rel="noopener">trainingden.app</a>'

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

    - name: hire
      blurb: what I'm looking for
      lines:
        - ""
        - '<span class="row"><span class="rk">now</span><span class="rv">Software engineering in financial services, Edinburgh.</span></span>'
        - '<span class="row"><span class="rk">after hours</span><span class="rv">Seven open-source repos and one live product, shipped solo.</span></span>'
        - '<span class="row"><span class="rk">good at</span><span class="rv">Picking up an unfamiliar domain fast, and turning a dense specification into tested, boring, correct code.</span></span>'
        - '<span class="row"><span class="rk">and lately</span><span class="rv">Getting real work out of coding agents without letting them near the numbers.</span></span>'
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

# ─────────────────────────────────────────────────────────────
# The page beneath the terminal. Everything below is read by
# overrides/home.html via {{ page.meta.* }} — to change what the
# page says, change it here, not in the template.
# ─────────────────────────────────────────────────────────────

# Header bar
whoami: phil harrison
location: Edinburgh · GMT · after hours

# Lede. The terminal retypes these four fields in place on hand-off,
# so they must stay as deck / headline / intro_long / intro_coda —
# see LEDE in overrides/home.html.
deck: Software engineer · open source · after hours
headline_lead: "I learn things by "
headline_emphasis: building
headline_tail: " them."
intro_long: >-
  Bank capital, swim training, Python packaging. The domains have nothing to do
  with each other; the practice is identical — pick something I don't understand,
  build the thing properly, and find out where the specification goes quiet.
intro_coda: >-
  Most of it happens after the day job, alongside a swarm of coding agents, and
  most of it ends up open.
byline: Phil Harrison

actions:
  - { label: "OpenAfterHours →", url: "https://openafterhours.github.io/", primary: true }
  - { label: "Training Den · live", url: "https://trainingden.app", primary: false }

# Left panel — the learning ledger. This is the one block worth
# keeping current; a stale date here is worse than no date.
learning:
  label: Currently learning
  asof: August 2026
  items:
    - k: agents
      v: Orchestrating swarms of coding agents — plan, fan out, review, merge.
    - k: polars
      v: Query-plan internals. Why the speed-up happens, not just that it does.
    - k: swimming
      v: Training periodisation, from coaches who have done it for thirty years.
    - k: regulation
      v: PRA PS1/26, and where its worked examples disagree with its text.
    - k: rust
      v: Learning it the only way that sticks — by writing abeam in it.

# Right panel — the AI practice, stated as a rule rather than a claim.
agents:
  label: Working with agents
  lead: >-
    Plan, fan out, review, merge. Running several agents at once is the cheap
    part; reviewing what they produce is the job.
  rule: The model may interpret, organise and suggest. It may not assert a number.
  demo:
    - { p: "draft", arrow: "→", v: "3 rounds × 2,050 m · 2 assumptions flagged" }
    - { p: "check", arrow: "→", v: "6,150 m — computed, then tested" }
  note: >-
    A coach describes a session in their own words; the model drafts it and the
    application does the arithmetic. If a computed number is wrong you can find
    out why. If a model asserted it, you cannot.
  # Reviewing is the expensive half of the loop, so it gets its own tool.
  tool:
    name: abeam
    lang: rust
    url: https://github.com/OpenAfterHours/abeam
    body: >-
      Since reviewing is the job, I built the window for it — the agent in a
      pty pane, with the git worktree, the file it just wrote and a shell
      beside it, so the right-hand side always shows what the agent just did.

# The work, at equal weight. No domain leads.
built:
  label: Built
  note: Seven open repositories and one live product, shipped solo after hours.
  items:
    - name: trainingden
      status: live
      live: true
      blurb: Session planning for British swimming clubs. A coach describes a set in words; the app computes the metres.
      url: https://trainingden.app
    - name: abeam
      status: rust
      blurb: One window for an AI coding session — the agent in a pty pane, with git, the file it just wrote and a shell beside it.
      url: https://github.com/OpenAfterHours/abeam
    - name: rwa_calculator
      status: python
      blurb: UK Basel 3.1 and CRR risk-weighted assets engine. Standardised, F-IRB and A-IRB, on Polars.
      url: https://github.com/OpenAfterHours/rwa_calculator
    - name: kedge
      status: python
      blurb: Turns manual Excel processes into reviewable marimo runbooks, with an AI copilot held to a controlled tool surface.
      url: https://github.com/OpenAfterHours/kedge
    - name: watchfire
      status: python
      blurb: Regulatory citations as code annotations that fail the build when they rot.
      url: https://github.com/OpenAfterHours/watchfire
    - name: moonlit
      status: python
      blurb: uv-native zipapp builder. One .pyz, and no virtualenv on the target machine.
      url: https://github.com/OpenAfterHours/moonlit
    - name: mooring
      status: python
      blurb: Git-free marimo notebook sharing for analyst teams — all sync over the GitHub API, no git on the machine.
      url: https://github.com/OpenAfterHours/mooring
    - name: curfew
      status: python
      blurb: Local-first dependency and module-boundary checks. No network, no telemetry.
      url: https://github.com/OpenAfterHours/curfew

# How the work gets done — three, because there are three.
practice:
  label: The practice
  items:
    - head: Build to understand.
      body: >-
        Reading a specification teaches you its vocabulary. Implementing it
        teaches you its shape, and shows you exactly where it goes quiet. Basel
        3.1, swim periodisation, PEP 441 zipapps — different documents,
        identical move.
    - head: Small batches, honest tests.
      body: >-
        Agile is not a ceremony; it's a way to ship for years without burning
        out. Numbers the machine computes rather than asserts, and code that
        explains itself to whoever reads it next.
    - head: Leave it behind.
      body: >-
        Open where it can be, live where it can't. Mostly these are things I
        needed once and then made properly, so the next person can have them
        for free.

# Footer links
links:
  - { label: "github · personal",        url: "https://github.com/luckyphil122",                     external: true }
  - { label: "github · openafterhours",  url: "https://github.com/OpenAfterHours",                   external: true }
  - { label: "training den",             url: "https://trainingden.app",                             external: true }
  - { label: "linkedin",                 url: "https://www.linkedin.com/in/phil-harrison-859a0bb8/", external: true }
---
