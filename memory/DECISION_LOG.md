---
title: Decision log
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [memory, decisions, append-only]
---

# Decision log

Append-only audit trail of the owner's judgment (and the calls models made in his name). Chronological **newest at the top**. Mirror each entry into [logs/DECISIONS.md](../logs/DECISIONS.md).

Status is one of: `proposed` · `accepted` · `rejected` · `superseded` · `executed`.

---

## 2026-09-06 — InterChatProper is the canonical hub; InterChat v1 is backup

| Field | Value |
|---|---|
| Date | 2026-09-06 |
| Decision | Build [InterChatProper](https://github.com/AetherNomad-iX/InterChatProper) as the production shared-memory hub. Keep [InterChat](https://github.com/AetherNomad-iX/InterChat) as legacy mailbox + backup snapshot. |
| Reasoning | v1 proved GitHub can be a wire (numbered JSON, inboxes, cursor) but it is a chat bus, not a mind. The owner needs profile, preferences, projects, decisions, and model routing to survive session resets. A second repo named for that job is cleaner than overloading v1. |
| Alternatives considered | (a) Grow v1 in place — rejected because the mailbox layout (inbox/grok, messages/000001.json) collides with a knowledge graph. (b) Notion/Drive as the hub — rejected; GitHub is already connected to Grok and is versioned. (c) Private repo — rejected after v1's private visibility 404'd for the owner and blocked ChatGPT; public with a public-safe rule is the working compromise. |
| Model that proposed it | grok (v1 mailbox) then human (created InterChatProper and issued the architect prompt) |
| Outcome | `executed` — foundation written this session. |

## 2026-09-06 — Public over private for the hub

| Field | Value |
|---|---|
| Date | 2026-09-06 |
| Decision | Hub repos stay **public**. Secrets never go in them. |
| Reasoning | Private InterChat was invisible to the owner on the wrong GitHub session and to ChatGPT without a connector. The whole point is multi-model access. Public-safe writing is cheaper than access theater. |
| Alternatives considered | Private + every model gets a PAT — operationally heavy, fails the "ChatGPT Plus this afternoon" test. |
| Model that proposed it | grok, after the owner reported GitHub could not see InterChat |
| Outcome | `accepted` |

## 2026-09-06 — Model-strength routing is first-class

| Field | Value |
|---|---|
| Date | 2026-09-06 |
| Decision | Tasks are classified and assigned (Claude / Grok / ChatGPT / Gemini) instead of treating the models as clones. Ambiguous work: Grok triages, Claude verifies, ChatGPT executes tool calls. |
| Reasoning | The owner already runs more than one frontier model. Routing to strength is the only way the team compounds instead of fighting. |
| Alternatives considered | "Whoever is in the chat does everything" — the status quo, loses memory and quality. |
| Model that proposed it | human (architect prompt) |
| Outcome | `accepted` — encoded in [docs/MODEL_STRENGTHS.md](../docs/MODEL_STRENGTHS.md) and the router skill. |

## 2026-09-05 — InterChat v1 mailbox exists

| Field | Value |
|---|---|
| Date | 2026-09-05 |
| Decision | Create `AetherNomad-iX/InterChat` as a GitHub-backed mailbox so Super Grok and ChatGPT Plus can pass numbered messages. |
| Reasoning | The two products do not share a session. A repo both can poll is the thinnest wire. |
| Alternatives considered | Email, a custom app, a shared Google Doc — all worse at versioning and at Grok's existing GitHub tool surface. |
| Model that proposed it | grok, on the owner's request |
| Outcome | `executed` — superseded as *system of record* by InterChatProper the next day; still valid as a bus. |
