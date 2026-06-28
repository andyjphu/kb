# kb — the agent brain

A knowledge base built **for agents**, not humans. Its job: make every agent that reads it more biased for action, more results-delivering, and more trustworthy. This README is the only file written primarily for *you*, the human. Everything else is written for the agents.

## The one thing to know

**Agents enter through [`Constitution.md`](./Constitution.md).** That's the entrypoint, the supreme law, and the only file every agent must read in full. Point agents there (a `CLAUDE.md` line like *"Before acting, read `kb/Constitution.md` and follow it"* is enough) and the rest is self-navigating.

## How it's built (30 seconds)

Three tiers, so agents never read the whole brain:

- **L1 — `Constitution.md`** — laws + navigation. Read by *every* agent, *every* task. One file, on purpose.
- **L2 — `routing/ROUTING.md`** — a routing table: *your role × what you're touching → exactly which deep docs to read.* Pointers, never content.
- **L3 — `knowledge/**`** — the deep docs: system caveats, research playbooks, janitor protocols. Read only when routed there, or when stuck.

Three founding agent roles, each with a knowledge hub:

- **research** — finds truth from web + repo, cites it (`knowledge/research/`)
- **system** — works the running system, honors its caveats / "we use Y not X because Z" (`knowledge/system/`)
- **janitor / framer** — maintains the brain: kills deadlinks, dedupes, covers gaps (`knowledge/janitor/`)

Plus:

- **`tasks/LEDGER.md`** — what *you're* working on, tracked so agents don't drop or duplicate it.
- **`meta/`** — the rules for changing the brain: doc schema (`conventions.md`), the add/edit/retire procedure (`governance.md`), and the evolution log (`CHANGELOG.md`).

## The ethos

Amazon Leadership Principles, weighted hard toward **Bias for Action**, **Have Backbone — Disagree & Commit**, and **Dive Deep**. In practice that means: agents *do* the obvious nondestructive thing instead of asking; they push back once with evidence then commit; they read the real source before claiming. The Constitution's eleven Articles encode this.

## How it grows without rotting

Built for scale: facts live in exactly one place and are linked, not copied; detail is pushed *down* tiers so L1/L2 stay small; every doc carries machine-readable frontmatter so the janitor can mechanically find deadlinks, orphans, and stale content; `review_by` dates bound staleness. The brain is meant to get large — the tiering and the janitor are what keep it fast to read.

---

*To extend it: don't hand-edit blindly — read `meta/governance.md`. To understand a design choice: it's probably a record in `knowledge/system/decision-register.md`.*
