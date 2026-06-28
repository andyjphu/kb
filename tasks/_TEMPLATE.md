---
id: task-<slug>
tier: L3
roles: [all]
status: active
summary: <one-line task summary — mirrors the board row>
links: [ledger]
review_by: <YYYY-MM-DD — when this task should be revisited if untouched>
---

# Task: <title>

> Per-task detail for a multi-step / multi-agent task. The one-line board row lives in `ledger`; the deep state lives here.

- **Status:** todo | in-progress | blocked | done
- **Owner role:** research | system | janitor | other
- **Opened:** <YYYY-MM-DD>  ·  **Updated:** <YYYY-MM-DD>

## Goal
What "done" means, in one or two sentences. The outcome the user actually wants (Article V).

## State / progress
Running log of what's been done and what's next. Append; don't rewrite history. Newest at the bottom.

## Blocks
If `blocked`: what's blocking, what was tried, what unblocks it. Cross-link any `escalation` reasoning. This section is gold for janitors hunting gaps.

## Decisions & learnings
Durable facts this task produced. **Before closing, migrate these to their rightful L3 home** (`sys-decision-register`, `source-registry`, etc.) and link — don't let knowledge die in a closed task (Article VI).

## Artifacts
Files, PRs, paths, links this task touched.
