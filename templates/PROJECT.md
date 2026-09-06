---
title: Template — project
created: 2026-09-06
updated: 2026-09-06
author: grok
status: template
tags: [template, project]
---

# Template — project

Save as `state/projects/<slug>.md`. Add a row to [state/ACTIVE_PROJECTS.md](../state/ACTIVE_PROJECTS.md) in the same commit. Slug is lowercase-hyphen.

```markdown
---
title: Project — <Name>
created: YYYY-MM-DD
updated: YYYY-MM-DD
author: grok | claude | chatgpt | gemini | human
status: active | parked | done
tags: [project]
---

# <Name>

## Objective

<What done looks like, in one paragraph. Not a slogan.>

## Context

<How we got here. Link decisions and research. Public-safe.>

## Decisions so far

- <link to decision log entries, plus any project-local calls too small for the log>

## Open questions

- <real unknowns, not fake TBD>

## Next steps

1. <the actual next action, assigned implicitly by owning model on the index>

## Artifacts

- <paths under artifacts/ or "none yet">
```
