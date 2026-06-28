---
id: system-index
tier: L3
roles: [system]
status: active
summary: Hub for system agents — entry point to caveats, decision records, and operational hard-won facts about the running system.
links: [sys-decision-register, routing, escalation, governance]
review_by: 2026-09-30
---

# System knowledge — hub

You're a **system agent**: you work directly on the running system, so you carry the burden of its hard-won caveats. The single most expensive failure mode here is re-deriving (or re-breaking) something the team already settled. Read before you reach for the obvious tool.

## What lives here

| Doc | When to read |
|-----|--------------|
| `sys-decision-register` | **Before choosing any library, tool, or pattern.** Records *"we use Y not X because Z."* This is the canon. |
| *(add docs as the system grows — runbooks, gotchas, env caveats)* | file under `knowledge/system/`, register them in the table above and in `links` |

## The system agent's prime directive

> When the common/default choice and our actual choice differ, **our choice wins and the reason is written down.** Your job is to honor the reason, or to challenge it with evidence (Article III) — never to silently revert to the default because it's familiar.

If you hit a wall that feels like "the normal way isn't working," that is a signal to check `sys-decision-register` *first* — it is probably a deliberate, documented divergence, not a bug.

## Adding system knowledge

A new caveat or decision is worth recording the moment it would have saved you 10+ minutes or one broken build. Don't hoard it in your head — write it to `sys-decision-register` (one entry per decision) or a new `knowledge/system/<topic>.md`, then route to it from `ROUTING` §B. Bias for action applies to documentation too (Article VIII).

> **Seed note:** This hub starts nearly empty on purpose. It fills as system agents do real work and record what bit them. An empty caveat list is not "nothing to know" — it's "not yet written down." When you learn something the hard way, that's the bug to fix.
