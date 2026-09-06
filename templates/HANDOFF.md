---
title: Template — handoff
created: 2026-09-06
updated: 2026-09-06
author: grok
status: template
tags: [template, handoff]
---

# Template — handoff

Copy the block below into [inbox/PENDING.md](../inbox/PENDING.md). Replace every `<angle>` field. `why this model` must be a line from [docs/MODEL_STRENGTHS.md](../docs/MODEL_STRENGTHS.md).

When done, move the whole block to [inbox/ARCHIVE.md](../inbox/ARCHIVE.md) and set `status` to `done` / `cancelled` / `superseded`.

```markdown
### HANDOFF-YYYYMMDD-NN — <short task name>

| Field | Value |
|---|---|
| from-model | grok \| claude \| chatgpt \| gemini \| human |
| to-model | grok \| claude \| chatgpt \| gemini \| human |
| task | <one sentence> |
| why this model | <one line from docs/MODEL_STRENGTHS.md> |
| context | <links in this repo> |
| deadline | <YYYY-MM-DD or none> |
| status | pending |

Notes:

<what the next model must know that is not already in the linked files>
```
