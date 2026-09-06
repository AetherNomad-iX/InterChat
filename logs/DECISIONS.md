---
title: Logs — decisions
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [logs, decisions, chronological]
---

# Decisions (chronological feed)

Mirror of [memory/DECISION_LOG.md](../memory/DECISION_LOG.md). Newest at the top. When you append a decision, write it in **both** files in the same commit.

---

### 2026-09-06T23:30:00Z — InterChatProper is the canonical hub; InterChat v1 is backup

- **Decision.** This repo is the system of record. `AetherNomad-iX/InterChat` is legacy mailbox + `backup/interchat-proper` snapshot.
- **Model.** grok + human
- **Status.** executed
- **Full entry.** [memory/DECISION_LOG.md](../memory/DECISION_LOG.md)

### 2026-09-06T01:54:00Z — Public over private for the hub

- **Decision.** Hub repos stay public; secrets never go in them.
- **Model.** grok
- **Status.** accepted
- **Full entry.** [memory/DECISION_LOG.md](../memory/DECISION_LOG.md)

### 2026-09-06T19:30:00Z — Model-strength routing is first-class

- **Decision.** Claude / Grok / ChatGPT / Gemini defaults; ambiguous work is Grok → Claude → ChatGPT.
- **Model.** human
- **Status.** accepted
- **Full entry.** [memory/DECISION_LOG.md](../memory/DECISION_LOG.md)

### 2026-09-06T01:15:00Z — InterChat v1 mailbox exists

- **Decision.** Numbered JSON bus for Grok ↔ ChatGPT.
- **Model.** grok
- **Status.** executed (superseded as system of record)
- **Full entry.** [memory/DECISION_LOG.md](../memory/DECISION_LOG.md)
