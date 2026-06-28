---
id: governance
tier: L3
roles: [janitor, all]
status: active
summary: The procedure for adding, editing, and retiring Articles and knowledge docs.
links: [constitution, conventions, routing, janitor-maintenance, changelog]
review_by: 2026-12-31
---

# Governance — how this brain changes

Two kinds of change, two bars. Don't mix them up (Article XI).

## Changing the Constitution (an Article) — high bar

Articles are durable law. To add or edit one:

1. **Pass the tests.** The proposed Article must pass *every* test in Constitution §4 (universality, durability, single responsibility, non-overlap, actionability, brevity cost). If it fails one, it's not an Article — it's a knowledge doc. Stop and file it as L3 instead.
2. **Prefer amend over add.** If an existing Article covers the space, edit that one. New Articles are rare (Article VI applies to law).
3. **Make the edit** in `Constitution.md`, keeping it terse — the *what*, not the *why*. Put any *why/how* in an L3 doc and link it.
4. **Record it** in `CHANGELOG` with one line: what changed and the reasoning.

## Changing knowledge docs (L2/L3) — low bar, bias for action

Adding, editing, or retiring an L3 doc or a ROUTING row is everyday work. Don't ask permission to improve the brain (Article I, VIII).

**To add a doc:**
1. Pick its tier and owner role (`conventions` §3–4). Place it under the right `knowledge/` subfolder.
2. Give it full frontmatter (`conventions` §1), including a real `summary` and `review_by`.
3. **Wire it in:** add a ROUTING §B row pointing to it, and add its `id` to the `links` of anything that references it. An unrouted doc is an orphan at birth.
4. If it's a structural addition (new region, new role), note it in `CHANGELOG`.

**To edit a doc:** just edit it. Keep frontmatter honest (bump `review_by` if you re-verified). Honor one-fact-one-home — if your edit duplicates a fact, link instead.

**To retire a doc:** follow the status lifecycle (`conventions` §6) — set `status: deprecated`, replace the body with a tombstone line pointing to the successor, and only delete once `janitor-maintenance` confirms nothing links to it.

## What a refactor is (and isn't)

A refactor is **not** a regeneration from source. AI-authored artifacts are not disposable build output — many are load-bearing and must survive any refactor. The source-vs-build analogy is loose: the kb is not throwaway output of the jurisprudence. A refactor applies Article XII across the corpus:

- **Keep** every passage that earns its place — including two narrow, similar examples when each is independently necessary. Similar ≠ redundant. There is often good reason both are there; do not merge them just because they overlap.
- **Merge** only when it is *nearly obvious* that two passages are genuinely redundant — removing one breaks or changes nothing. The bar is high; when in doubt, keep both and escalate (Article III).
- **Prose test:** evocative/"flowery" prose stays only if you can name the reasoning it activates. If you can't say what cognitive shift it produces, it's decoration — cut it. Frugal everywhere prose isn't doing real work.
- **Never** flatten necessary nuance to save words. Fewer words is not the goal; *no removable words* is.

## The throughline

Rules are durable and change rarely under a high bar. Facts are fluid and change freely under bias for action. Keeping them in their lanes is what lets the Constitution stay trustworthy while the knowledge stays current.
