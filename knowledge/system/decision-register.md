---
id: sys-decision-register
tier: L3
roles: [system]
status: active
summary: The canon of "we use Y not X because Z" decisions. Read before choosing any library, tool, or pattern.
links: [system-index, conventions, governance]
review_by: 2026-09-30
---

# Decision Register — why we do it the way we do

One entry per decision. Each records a divergence from the obvious/common choice and the reason. **Honor these, or challenge them with evidence (Article III) — never silently revert to the default.**

Entry format:

```
### DR-NNN — <short title>            [status: active | superseded]
- Decision: we use <Y>, not <X>.
- Because: <Z — the constraint or reason that makes the default wrong here>.
- Cost if ignored: <what breaks / what time is lost when an agent uses X anyway>.
- Added: <YYYY-MM-DD> · Review by: <YYYY-MM-DD>
```

Keep entries terse. The point is fast recall at the moment of choice, not a history essay.

---

## Decisions

### DR-001 — L1 is a single file, not a folder           [status: active]
- Decision: we keep L1 as exactly one file (`Constitution.md`), not a `articles/` folder of one-rule-per-file.
- Because: L1 is read *in full by every agent on every task*. Splitting it into N files turns one read into N reads and N chances to miss a rule. The token cost of one dense file beats the latency and miss-rate of many.
- Cost if ignored: agents skip articles, the "always read" guarantee breaks, and L1 silently becomes L2.
- Added: 2026-06-28 · Review by: 2026-12-31

### DR-002 — Routing table holds pointers, never content   [status: active]
- Decision: `ROUTING.md` (L2) contains only role/region → doc mappings. Actual knowledge always lives in an L3 doc.
- Because: the routing table is read by everyone who needs *anything*. If it carries content, it bloats and re-introduces the scanning problem tiering was meant to kill. Pointers stay terse at any scale; content does not.
- Cost if ignored: ROUTING grows unbounded, agents read paragraphs they don't need, Article VII ("route, don't scan") fails from the inside.
- Added: 2026-06-28 · Review by: 2026-12-31

### DR-003 — Frontmatter is mandatory and load-bearing     [status: active]
- Decision: every doc carries YAML frontmatter with `id`/`links`/`status`/`review_by`, even when it feels like overhead.
- Because: the janitor maintains the KB *mechanically* against this metadata — deadlink detection, orphan detection, staleness sweeps all read frontmatter. Prose-only docs are unmaintainable at scale.
- Cost if ignored: the KB can't be audited automatically; rot accumulates invisibly until an agent acts on a stale fact.
- Added: 2026-06-28 · Review by: 2026-12-31

### DR-004 — Knowledge sinks: the kb only; agent files are pointers   [status: active]
- Decision: durable knowledge is written only to the kb. Agent-specific stores — `CLAUDE.md`, model/agent memory, scratch files — hold no knowledge, only a pointer to the kb (or nothing). Those sources are sunset.
- Because: knowledge must be agent-agnostic and single-sourced. Anything in a Claude-specific store is invisible to other agents, drifts from the kb, and re-creates the duplication and ablation problems the kb exists to solve. (Codifies Article XIII.)
- Cost if ignored: truth forks across sources; an agent trusts a stale `CLAUDE.md`/memory that contradicts the kb; agent-agnosticism breaks.
- Added: 2026-06-28 · Review by: 2026-12-31

---

> **This register seeds itself with the KB's own architecture decisions** — they're real, they demonstrate the format, and they explain divergences you'll actually meet while editing the KB. As system agents do real work on the *running* system, add the divergences *that* system requires (the package you swapped, the flag you must set, the service you can't call directly). One decision, one entry. That is Article VI applied to system lore.
