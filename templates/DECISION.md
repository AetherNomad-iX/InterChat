---
title: Template — decision
created: 2026-09-06
updated: 2026-09-06
author: grok
status: template
tags: [template, decision]
---

# Template — decision

Append a filled copy to **both** [memory/DECISION_LOG.md](../memory/DECISION_LOG.md) (narrative, newest first) and [logs/DECISIONS.md](../logs/DECISIONS.md) (feed). Status: `proposed` · `accepted` · `rejected` · `superseded` · `executed`.

```markdown
## YYYY-MM-DD — <short name>

| Field | Value |
|---|---|
| Date | YYYY-MM-DD |
| Decision | <the call, in one or two sentences> |
| Reasoning | <why this, not the alternative> |
| Alternatives considered | <at least one real alternative, or "none — owner directive"> |
| Model that proposed it | grok \| claude \| chatgpt \| gemini \| human |
| Outcome | proposed \| accepted \| rejected \| superseded \| executed |
```

If this supersedes an older entry, add `Supersedes: [anchor](url)` and mark the old entry `superseded` without deleting it.
