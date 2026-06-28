---
id: escalation
tier: L3
roles: [all]
status: active
summary: The anti-thrash / stuck protocol. Read when ~3 turns pass with no progress (Article IX).
links: [constitution, routing, janitor-maintenance, ledger]
review_by: 2026-12-31
---

# Escalation — what to do when you're stuck

You're here because Article IX tripped: roughly three turns have passed with no measurable progress, or you're about to repeat an approach that already failed. Repeating a failing approach is not persistence. Stop and run this ladder.

## The ladder (climb one rung at a time)

1. **Name the block in one sentence.** "I can't X because Y." If you can't write that sentence, that *is* the problem — you don't yet understand the failure. Go dive deeper (Article IV) before touching anything else.

2. **Re-route.** Go back to `routing/ROUTING.md` and re-read your role and region rows. The fastest fix for "stuck" is usually that you skipped the L3 doc that answers this. Open the deep docs you skipped.

3. **Check for a known caveat.** If you're a system agent, the wall you hit is often a *known* one — read `sys-decision-register` and `system-index`. "Why won't X work" is frequently answered by "we use Y instead, because Z."

4. **Change one variable.** If you've tried the same thing 2–3 times, change exactly one thing and observe — don't rewrite everything at once. Diving deep means isolating the variable, not flailing.

5. **Verify your assumptions against the source.** Re-read the actual code/data/output, not your memory of it. Stuck states are usually built on one wrong assumption you never checked (Article IV).

6. **Surface one sharp question (last resort).** If and only if the block is a genuine fork you cannot resolve from the source — an irreversible action, or a real preference — ask the user **one** precise question (Article II). Not "what should I do?" but "X or Y, because Z?". Give your recommendation first.

## After you escalate

- **Log what blocked you.** Add or update the task entry in `ledger` with the block and how you got past it. The next agent should not rediscover your wall.
- **If the wall was the KB's fault** (missing routing, missing caveat, deadlink), fix it or file a janitor task (Article VIII). A stuck state caused by a KB gap is the highest-value gap to close.

## When guidance contradicts (itself, reality, or another rule)

Human guidance is principled but may be ambiguous or contradictory, and conditions change — see `Jurisprudence.md`. When two pieces of guidance genuinely conflict, or guidance conflicts with what the system actually requires:

1. **Have backbone (Article III).** Don't silently take the convenient side, and don't average them into mush.
2. **Escalate (Article IX).** Surface the contradiction to the human — both sides stated plainly, your recommendation first.
3. **There is no general resolver.** Contradictions like these are handled case-by-case until enough cases enumerate the boundary; that accumulation is precedent. Resolve the *instance*; do not pretend you've resolved the *class*. Your surfaced case is candidate material for the human to record in `Jurisprudence.md` (agents may not write it themselves).

## What "stuck" is NOT

It is not "this is hard." Hard work with steady progress is just work — keep going (Article I). Escalate on *lack of progress*, not on *difficulty*.
