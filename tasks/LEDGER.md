---
id: ledger
tier: L3
roles: [all]
status: active
summary: The board of what the user is working on right now. Shared in-flight memory across agents (Article X).
links: [constitution, escalation, routing]
review_by: 2026-12-31
---

# Task Ledger — what's in flight

This is the shared memory of work the user has going (Article X). **Before substantial work, open an entry. Keep its status truthful. Close it when done.** An untracked task is a task that gets dropped, duplicated, or lost between agents.

Lightweight rule: a quick one-shot answer needs no entry; anything spanning multiple turns, multiple agents, or that you'll hand off does.

## Board

| ID | Task | Status | Owner role | Updated | Detail |
|----|------|--------|-----------|---------|--------|
| _example_ | _Stand up the KB_ | done | janitor | 2026-06-28 | _Founding build; see CHANGELOG_ |

Status values: `todo` · `in-progress` · `blocked` · `done`. A `blocked` row must say what it's blocked on (and link the `escalation` log if relevant).

## How to use it

- **Open:** add a row with a short slug ID, the task, status `todo`/`in-progress`, your role, today's date.
- **Big tasks get a file:** if a task spans many steps or agents, copy `tasks/_TEMPLATE.md` to `tasks/<slug>.md`, link it in the **Detail** column, and keep the deep state there. The board row stays a one-liner.
- **Update on state change, not every turn:** flip to `blocked`/`done` when reality changes. Stale status is worse than no status.
- **Close:** set `done` and, if it taught the KB something durable, make sure that lesson landed in the right L3 doc (don't let knowledge die in a closed task).

## Hygiene

- Janitors sweep `done` rows older than ~30 days into the bottom or out (the CHANGELOG holds anything structural).
- `blocked` rows are the highest-signal entries in the KB — they point straight at gaps. Janitors and framers: mine them.

<!-- Add active rows above. Keep the board scannable; push depth into per-task files. -->
