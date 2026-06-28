---
id: changelog
tier: L3
roles: [janitor, all]
status: active
summary: Append-only log of how this brain has structurally evolved. Read to understand why the KB is shaped as it is.
links: [governance, constitution]
review_by: 2027-06-30
---

# CHANGELOG — how this brain evolved

Append-only. One entry per structural change (new/changed Article, new region/role, tier move, shard, routing reshape). Routine content edits don't need an entry; structure does. Newest on top.

Entry format: `## YYYY-MM-DD — <change>` then 1–3 bullets of *what* and *why*.

---

## 2026-06-28 — KB declared the only source of truth; external sinks sunset
- Ratified **Article XIII — The KB Is the Only Source**: all durable knowledge lives in the kb and nowhere else; agent-specific stores (`CLAUDE.md`, model memory, scratch) may hold at most a knowledge-free pointer. Serves agent-agnosticism.
- Recorded **DR-004** (system register): kb-only knowledge sinks; agent files are pointers; the why and the cost.
- **Migrated + sunset:** stripped `CLAUDE.md` to a knowledge-free pointer (its ethos summary already lived in the Constitution — nothing lost); wrote a tombstone to internal Claude memory redirecting to the kb. The only external knowledge found was CLAUDE.md's summary, which duplicated L1.
- Candidate `Jurisprudence` entry #3 (the human guidance behind this rule) left for the human to record.

## 2026-06-28 — Jurisprudence wired in as the L0 source layer
- Gave `Jurisprudence.md` minimal frontmatter (`id: jurisprudence`, `tier: L0`) — now addressable, so artifacts trace provenance to it. Introduced **L0**: the human-authored source layer the tiers compile from; read at amendment/refactor time, never per-task (`conventions` §3).
- Revised the document's write-rule (per human direction): agents may now author a minimal **context** block preceding each entry, plus the file's frontmatter. Entry guidance bodies stay Human Written.
- Recorded **Jurisprudence entry #2** (frugality & contradiction) with an agent-authored context preamble carrying forward-provenance (entry → the artifacts it compiled into).
- Added the `derives_from` provenance field (`conventions` §1, deadlink-checked); demonstrated on the Constitution (`derives_from: [jurisprudence]`). Routing now sends amend/refactor work to `jurisprudence`.

## 2026-06-28 — Article XII ratified; refactor semantics defined
- Ratified **Article XII — Every Word Earns Its Place**: text justifies itself by necessity (the irreducibility test), redundancy is judged by meaning not surface form, and evocative prose is kept only when it names the reasoning it activates. Passed all six §4 tests — including self-application (removing XII would lose the irreducibility test and the prose discriminator, a breaking change). Derives from human guidance in this discussion; candidate `Jurisprudence.md` entry #2.
- Defined **what a refactor is/isn't** in `governance`: not a regeneration from source; AI artifacts persist and may be load-bearing through any refactor; merge only nearly-obvious redundancy; the goal is *no removable words*, not *fewer words*.
- Added contradiction handling to `escalation`: backbone + escalate; case-by-case until enumerated; surfaced cases are candidate precedent for the human to record.
- Marked `Jurisprudence.md` out-of-schema (human source-of-truth), excluded from janitor mechanical checks.
- **Open / deferred (pending human direction):** wiring `Jurisprudence.md` into the link graph — provenance (`derives_from`) and an addressable id — so kb artifacts trace to the guidance that justifies them (#1/#2 from prior discussion).

## 2026-06-28 — Founding ratification
- Established the three-tier model (L1 Constitution / L2 routing / L3 deep docs) and the reading protocol (Constitution §0).
- Ratified Articles I–XI, weighted toward Bias for Action, Backbone-then-Commit, and Dive Deep (Constitution §1–2).
- Defined three founding agent roles — `research`, `janitor/framer`, `system` — each with a knowledge hub under `knowledge/` and routing rows in `ROUTING` §A.
- Seeded the system decision register (DR-001..003) with the KB's own architecture decisions.
- Stood up the task ledger (`ledger`) as the shared in-flight memory (Article X).
- Recorded the foundational design rationale as decision records rather than prose, so the *why* is itself queryable.
