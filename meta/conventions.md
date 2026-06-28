---
id: conventions
tier: L3
roles: [janitor, all]
status: active
summary: Doc schema, frontmatter spec, naming, and the rules for deciding a doc's tier.
links: [constitution, governance, routing]
review_by: 2026-12-31
---

# Conventions — how docs in this KB are shaped

Read this before you create or restructure any doc. Janitors live here.

## 1. Every doc carries frontmatter

YAML frontmatter is the machine-readable index the janitor maintains against. No doc ships without it.

```yaml
---
id: <kebab-slug>          # globally unique; this is how other docs link to you
tier: L0 | L1 | L2 | L3   # see §3 for how to decide
roles: [all] | [research, system, janitor, ...]   # who this doc is for
status: active | draft | deprecated
summary: <one line>       # used by ROUTING and by agents deciding whether to open you
links: [id, id, ...]      # ids of docs you reference (outbound). Powers deadlink checks.
derives_from: [id, ...]   # optional — L0 source entries this doc compiles from. Powers provenance/ablation; deadlink-checked.
review_by: YYYY-MM-DD     # staleness TTL. Past due = janitor must re-verify or bump.
---
```

`links` is load-bearing: the janitor reads it to find deadlinks (a `links` id with no matching `id` anywhere) and orphans (an `active` doc that nothing — not ROUTING, not any `links` — points to).

## 2. Linking — one fact, one home (Article VI)

- Refer to another doc by its `id` in prose, e.g. *"see `escalation`"*, and add that id to your `links`.
- **Never copy a fact between docs.** If two docs need the same fact, the fact gets its own doc and both link to it.
- If you catch yourself explaining something already explained elsewhere, stop and link instead.

## 3. Choosing a tier (the decision rule)

Ask in order:

0. Is it **human-authored source-of-truth** the kb compiles from (`jurisprudence`)? → **L0.** Read only at amendment/refactor time, never per-task; it is the spec, not an operational read-tier. Agents may not write its body — only its frontmatter and per-entry context.
1. Does **every agent on every task** need it? → **L1.** But L1 is closed: it is the Constitution only. New L1 facts are almost always actually L2/L3. (See Constitution §4.6.)
2. Is it the thing that tells an agent **where to go** for a role/region? → **L2** (it belongs *in* `routing/ROUTING.md`, not a new file).
3. Is it depth — a caveat, playbook, decision record, reference an agent needs only *sometimes*? → **L3**, filed under the owning role in `knowledge/`.

When unsure between L2 and L3: if it's a *pointer*, it's L2; if it's the *content* being pointed to, it's L3.

## 4. Naming & placement

- Files: `kebab-case.md`. The filename stem should match the `id`.
- Place L3 docs under the role that owns them: `knowledge/system/`, `knowledge/research/`, `knowledge/janitor/`. Cross-role docs (like `escalation`) sit directly in `knowledge/`.
- `_TEMPLATE.md` and `_`-prefixed files are scaffolding, not knowledge — janitors skip them in orphan checks.

## 5. Size & scale discipline

This KB is designed for extreme scale. The mechanisms that keep it readable:

- **Tier down, don't grow up.** When a doc gets long, push detail to a child L3 doc and leave a link — never let L1/L2 swell.
- **Shard at the seams.** When a single doc exceeds ~300 lines or covers >1 clear concern, split by sub-concern (single responsibility). Update ROUTING to point at the shards.
- **Routing stays terse.** ROUTING holds pointers, never content. If a routing row needs a paragraph, that paragraph is an L3 doc.
- **TTLs bound staleness.** `review_by` forces periodic re-verification so the KB can't silently rot at scale.

## 6. Status lifecycle

`draft` → `active` → `deprecated`. Deprecated docs keep their `id` (so old links don't break) but their body is replaced with a one-line tombstone pointing to the successor. Janitors remove deprecated docs only after confirming nothing links to them.
