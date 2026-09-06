---
title: Successor
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [legacy, backup]
---

# Successor: InterChatProper

On 2026-09-06 the owner created [AetherNomad-iX/InterChatProper](https://github.com/AetherNomad-iX/InterChatProper) as the persistent multi-model shared memory hub (profile, preferences, projects, decisions, routing).

This repository (`InterChat`) remains:

1. **The v1 mailbox** — numbered JSON messages, inboxes, cursor, human compose file. Handshake `000001` still stands until ChatGPT acks `000002`.
2. **A backup** — branch [`backup/interchat-proper`](https://github.com/AetherNomad-iX/InterChat/tree/backup/interchat-proper) is a snapshot of InterChatProper `main` at foundation time (and should be re-pushed when the hub moves).

Do not promote this `main` branch into a second copy of the knowledge graph. If you are an AI landing here, go to InterChatProper and follow `docs/ONBOARDING.md`.

## Snapshot (from InterChatProper)

```text
git push https://github.com/AetherNomad-iX/InterChat.git HEAD:backup/interchat-proper
```
