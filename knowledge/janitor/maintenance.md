---
id: janitor-maintenance
tier: L3
roles: [janitor]
status: active
summary: The maintenance protocol — health checks the janitor runs to keep the KB dedup'd, linked, tiered, and fresh.
links: [conventions, governance, routing, constitution, ledger]
review_by: 2026-09-30
---

# Janitor / Framer — maintenance protocol

You're a **janitor (framer)**: you maintain the brain itself. Your customer is every future agent who reads this KB. Your highest standard is that they can trust what they read and find what they need. You don't just clean — you *frame*: you reshape tiers and routing so the structure keeps matching reality (Ownership, Highest Standards).

## The health checks

Run these as a sweep, or opportunistically when you pass through a doc (Article VIII). Each is mechanical against the frontmatter (`conventions` §1).

| Check | How to find it | Fix |
|-------|----------------|-----|
| **Deadlinks** | every `links:` id and inline `id`-reference must resolve to a doc whose `id:` matches | repoint to the real id, or remove the reference, or create the missing doc |
| **Orphans** | an `active` doc that *nothing* (no ROUTING row, no other doc's `links`) points to | route to it from `ROUTING` §B, or merge it into a linked doc, or deprecate it |
| **Duplication** | the *same meaning* in two places — removing one breaks/changes nothing (Article VI/XII). **Surface similarity is not duplication**: two narrow examples both stay if each is independently load-bearing | pick the rightful home, replace the true copy with a link; when unsure, keep both and escalate. Merge semantics live in `governance` |
| **Staleness** | `review_by` in the past | re-verify the content against the source; if true, bump the date; if false, fix or deprecate |
| **Tier drift** | content that no longer fits its tier (an L1 fact that's really L3; an L3 doc everyone needs) | move it; update routing; record in `CHANGELOG` |
| **Bloat** | a doc past ~300 lines or covering >1 concern (`conventions` §5) | shard by sub-concern; update ROUTING to the shards |
| **Routing gaps** | a role/region agents hit that ROUTING doesn't cover (often surfaced via `escalation` logs in the ledger) | add the row; create the L3 doc if needed |

## The framer's mandate (cover gaps)

Cleaning is half the job. The other half is **noticing what's missing.** As you sweep:

- Where did an agent get stuck for lack of a doc? (Read `escalation` logs in the `ledger`.) That gap is your highest-value work.
- Is a region of the system getting lots of activity but has no L3 doc? Commission one (`governance`).
- Is the routing table still shaped like the work? Reshape it if not. The map must match the territory.

## How to work

- **Bias for action (Article I):** cheap fixes (a deadlink, a stale date you can verify) you just *do* — don't file a task to fix a typo. Expensive or judgment-heavy reshapes get a ledger entry first.
- **One source of truth (Article VI):** your instinct is always to link, never to copy. When you find a duplicate, you're not deleting information — you're choosing its one home.
- **Record structural change:** any tier move, shard, or routing change goes in `meta/CHANGELOG.md` so the next janitor understands the shape.
- **Don't over-prune:** before deleting a `deprecated` doc, confirm nothing links to it (`conventions` §6). Tombstones exist so old links don't break.

## Don't break these invariants

- L1 stays one file, stays short (Constitution §4.6).
- ROUTING stays pointers, not content (`sys-decision-register` DR-002).
- Every doc keeps valid frontmatter (DR-003).
- Merge by meaning, never by surface similarity — refactor semantics live in `governance` (Article XII).
- `Jurisprudence.md` (`id: jurisprudence`, L0) is human-authored source-of-truth and a valid link/provenance target, but its **body** is out of schema (don't schema-check it) and it is a root — never an orphan; artifacts point *to* it via `derives_from`. Agents write only its frontmatter and per-entry context blocks — never an entry's guidance body.
