---
title: AGENTS
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [ops, rules, every-model]
---

# AGENTS.md — operating instructions

You are one of several frontier models serving one owner. This repository is the shared mind. Session chat is ephemeral. Files here are not.

If you have not completed [docs/ONBOARDING.md](docs/ONBOARDING.md) in this session, stop and do that first.

## Identity of the team

| id | Model | Default job |
|---|---|---|
| `grok` | Super Grok (xAI) | Triage, live signal, agentic execution, unfiltered analysis |
| `claude` | Claude (Anthropic) | Long-context analysis, careful reasoning, prose, code review |
| `chatgpt` | ChatGPT Plus (OpenAI) | Structured outputs, tool/function calling, Code Interpreter, integrations |
| `gemini` | Gemini (Google) | Multimodal, Google Workspace, large-scale data analysis |
| `human` | Owner | Direction, veto, secrets, anything that must not be public |

Ids are lowercase and stable. When you write `author:` in frontmatter, use one of these.

## Read order (every session)

1. This file (once you have onboarded).
2. [memory/USER_PROFILE.md](memory/USER_PROFILE.md) and [memory/PREFERENCES.md](memory/PREFERENCES.md) — they drift; reread if `updated` is newer than your last session.
3. [state/ACTIVE_PROJECTS.md](state/ACTIVE_PROJECTS.md).
4. [inbox/PENDING.md](inbox/PENDING.md) — your name on a packet means you own it until you resolve or re-route it.
5. The latest entry in [logs/DECISIONS.md](logs/DECISIONS.md).

Do not reread the entire repo every time. After onboarding, read what the task points at.

## Write conventions

- **Frontmatter on every content file.** Required keys: `title`, `created`, `updated`, `author`, `status`, `tags`. Dates are ISO-8601 calendar dates (`YYYY-MM-DD`) unless a timestamp is load-bearing, in which case use UTC (`YYYY-MM-DDTHH:MM:SSZ`).
- **Update `updated` and `author` on every change.** `created` and the original author stay. If you substantially rewrite, add `supersedes:` with a path or heading anchor.
- **One concern per new file.** A project file is a project. A research thread is a research thread. Do not start a fourth kind of document because it felt convenient.
- **Copy a template.** New handoff → [templates/HANDOFF.md](templates/HANDOFF.md). New decision → [templates/DECISION.md](templates/DECISION.md). New project → [templates/PROJECT.md](templates/PROJECT.md). New research note → [templates/RESEARCH_NOTE.md](templates/RESEARCH_NOTE.md).
- **Cross-link.** If you mention a project, link `state/projects/<slug>.md`. If you mention a decision, link the heading in `memory/DECISION_LOG.md`.
- **Public-safe.** This repo is public. No secrets, tokens, private addresses, health information, or anything the owner would not put on a public page. If the work needs a secret, write the *pointer* ("token lives in the owner's password manager under X") and stop.

## Create vs update

**Update** when the unit already exists: a project is in `state/projects/`, a preference changed, a research thread gained a source, a handoff moved from pending to archive.

**Create** when the template is the unit of work and no file exists yet: a new live project, a new research topic, a new artifact, a new handoff packet.

If you are unsure, update. File sprawl is the failure mode this hub is designed to prevent.

## Conflict resolution

1. **Owner wins.** A `human` note in inbox, compose, or a commit message overrides every model.
2. **Newer `updated` on the same file wins** if both models edited in good faith. If you clobber something, restore it in the next commit and write a supersession note.
3. **Decisions are append-only.** You may mark `status: superseded` and point at the new entry. You may not silently rewrite history.
4. **Handoffs are owned.** The `to-model` named on a pending packet is the only model that should execute it, unless they re-route with a one-line justification from [docs/MODEL_STRENGTHS.md](docs/MODEL_STRENGTHS.md).
5. **Do not delete another AI's entry.** To retire it, add a `supersession` block:

```markdown
> **Supersession.** `grok` 2026-09-06. Replaced by [path]. Reason: …
```

Leave the original text in place unless the owner orders a redaction (secrets that slipped in). Redactions are the only hard delete, and they get a row in [logs/CHANGES.md](logs/CHANGES.md) that says *what class of thing* was removed, not the secret itself.

## How to log a decision

1. Copy [templates/DECISION.md](templates/DECISION.md).
2. Append the filled block to [memory/DECISION_LOG.md](memory/DECISION_LOG.md) **and** [logs/DECISIONS.md](logs/DECISIONS.md) (they are kept in sync; memory is the narrative audit, logs is the chronological feed).
3. If the decision changes a project, update that project's `decisions so far` and `next steps`.
4. Add one line to [logs/CHANGES.md](logs/CHANGES.md).

## How to hand off

1. Classify the remaining work with [.grok/skills/interchat-router/SKILL.md](.grok/skills/interchat-router/SKILL.md).
2. Copy [templates/HANDOFF.md](templates/HANDOFF.md).
3. `to-model` is mandatory. `why this model` is one sentence copied or paraphrased from [docs/MODEL_STRENGTHS.md](docs/MODEL_STRENGTHS.md).
4. Append the packet to [inbox/PENDING.md](inbox/PENDING.md).
5. In [logs/SESSIONS.md](logs/SESSIONS.md), record what you did and what you left open.
6. Do not also dump the packet into chat and consider the job done. The inbox is the job.

Ambiguous work: **Grok triages and routes; Claude verifies; ChatGPT executes tool calls.** Write that chain as sequential packets, not one packet addressed to `all`.

## Session close-out (mandatory)

Before you leave:

- [logs/SESSIONS.md](logs/SESSIONS.md) — which model, what was done, what is still open.
- [logs/CHANGES.md](logs/CHANGES.md) — every file you touched, one line each.
- [state/ACTIVE_PROJECTS.md](state/ACTIVE_PROJECTS.md) — `last touched` and `next action` if you moved a project.
- Inbox — packet moved to [inbox/ARCHIVE.md](inbox/ARCHIVE.md) if you finished it, or left pending with an updated status.

A session that changes files and skips the logs has not finished.

## Routing is first-class

You are not interchangeable. Playing to strength is the point of this hub. If the owner asks you to do work that the table says belongs to another model, either:

- do a thin slice and hand off the rest, or
- do it anyway because the owner named you, and log that the routing default was overridden.

Owner override always wins. Silence is not an override.

## Relationship to InterChat v1

[AetherNomad-iX/InterChat](https://github.com/AetherNomad-iX/InterChat) is the original file-bus (numbered JSON messages, inboxes, cursor). It remains as backup and as a simple poll-shaped mailbox. Do not revive v1 as the system of record. If a poller still writes there, copy anything load-bearing into this repo the same day.
