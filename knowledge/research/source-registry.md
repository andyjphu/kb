---
id: source-registry
tier: L3
roles: [research]
status: active
summary: Vetted external sources, so research agents skip cold searches on already-solved questions.
links: [research-playbook, conventions]
review_by: 2026-09-30
---

# Source Registry — vetted external sources

Check here before a cold web search (`research-playbook` step 2). Add a source the moment you've vetted it as reliable — that's the deduplication of research effort across every future agent.

Entry format:

```
### <topic / domain>
- Source: <name> — <URL>
- Trust: primary | official-docs | reputable-secondary | use-with-care
- Good for: <what questions this answers well>
- Watch out: <known biases, paywalls, staleness, version drift>
- Vetted: <YYYY-MM-DD>
```

`Trust` ranking (high → low): **primary** (the thing itself — source code, specs, the API) → **official-docs** → **reputable-secondary** → **use-with-care**. Prefer the highest tier that answers the question.

---

## Sources

> Empty by design — the first research agents fill it. When you vet a source worth returning to, add it here before you move on. A registry that stays empty means research is being repeated; a registry that grows means the team is compounding what it learns. Make it grow.

<!-- Add entries above this line. One source, one entry. Keep "Watch out" honest. -->
