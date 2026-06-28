---
id: routing
tier: L2
roles: [all]
status: active
summary: The routing table. Maps your role and the region you're touching to the exact L3 docs to read.
links: [constitution, escalation, system-index, sys-decision-register, research-playbook, source-registry, janitor-maintenance, conventions, governance, ledger, jurisprudence]
review_by: 2026-12-31
---

# ROUTING — your second stop, after the Constitution

You arrive here knowing two things about yourself (Constitution §0): your **role** and your **region**. Find your rows. Open only the docs they name. Read nothing else. This is Article VII in practice.

> Routing holds **pointers, not content.** If you want to add knowledge here, you're in the wrong place — add an L3 doc and point a row at it (`governance`).

---

## A. By role — what you always read for your job

| Role | Read on every task of this kind | Then route by region (§B) |
|------|----------------------------------|---------------------------|
| **research** | `research-playbook`, `source-registry` | yes |
| **system** | `system-index` (caveats hub), `sys-decision-register` | yes |
| **janitor / framer** | `janitor-maintenance` | yes |
| **other / general** | — (Constitution is enough to start) | yes |
| **anyone who is stuck** | `escalation` (Article IX) | — |

---

## B. By region — what you're touching → what to read

Match the region you named. If your region isn't listed, that's a **routing gap**: add a row here (cheap) or file a janitor task (Article VIII). Never just guess and proceed.

| Region (what you're touching) | Read these (L3) | Owner role |
|-------------------------------|-----------------|------------|
| Choosing a library / tool / package | `sys-decision-register` | system |
| A non-obvious "why do we do it this way" | `sys-decision-register`, `system-index` | system |
| Running, building, or operating the system | `system-index` | system |
| External facts, prior art, docs, current events | `research-playbook`, `source-registry` | research |
| Searching this repo / workspace internally | `research-playbook` | research |
| Editing the KB's structure, tiers, or links | `janitor-maintenance`, `conventions` | janitor |
| Deadlinks, orphans, stale docs, duplication | `janitor-maintenance` | janitor |
| Adding/retiring a knowledge doc | `governance`, `conventions` | janitor |
| Refactoring / consolidating the KB | `governance` (refactor semantics), `janitor-maintenance`, `jurisprudence` | janitor |
| Amending the Constitution (an Article) | Constitution §4, `governance`, `jurisprudence` | janitor |
| What the user is working on right now | `ledger` | all |
| You're stuck (≥3 turns, no progress) | `escalation` | all |

---

## C. How to extend this table (do it, don't ask)

Per Article I and VIII, if you discover a region or role that isn't routed:

1. Add a row above pointing to the right L3 doc (create the doc via `governance` if it doesn't exist).
2. Add the new doc's `id` to this file's `links` frontmatter.
3. Log it in `meta/CHANGELOG.md` if it's a structural change.

A routing table that lags reality is the most expensive bug in this KB — it sends agents scanning. Keep it current.
