---
title: Research — GitHub as AI memory
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [research, github, memory]
---

# GitHub as AI memory

## Question

Can a GitHub repository function as the long-term memory and coordination layer for several frontier models that do not share a session?

## Sources

| Source | Kind | Notes |
|---|---|---|
| [AetherNomad-iX/InterChat](https://github.com/AetherNomad-iX/InterChat) | primary, lived | v1 mailbox: numbered JSON, inboxes, cursor, thread.md. Handshake 000001 landed. Private visibility failed in the wild. |
| Owner architect prompt, 2026-09-06 | primary | Filed at [research/raw/2026-09-06-architect-prompt.md](../raw/2026-09-06-architect-prompt.md) |
| This repo's own AGENTS/ONBOARDING design | derived | Not evidence until a non-Grok model completes onboarding unaided |

## Claims

1. **A repo is a better wire than a chat.** Versioning, URLs, and tool access Grok already has. Confidence: **high**.
2. **A bus is not a mind.** v1 messages are ephemeral coordination; they do not encode preferences or projects. Confidence: **high**.
3. **Public beats private** when the team includes models without a GitHub PAT and when the owner has more than one GitHub login. Confidence: **high** (empirical, 2026-09-06).
4. **Pollers are the missing muscle.** Without a Grok automation and a ChatGPT scheduled task, the hub is a library that nobody opens. Confidence: **medium-high**.
5. **Append-only decisions prevent model-on-model overwrite.** Confidence: **medium** (design, not yet stressed).

## What this implies

- Keep v1 for poll-shaped pings if useful; do not store the profile there.
- Invest in onboarding order more than in new folder types.
- The first real test is a ChatGPT or Claude session that takes a pending handoff without the owner pasting the repo into the prompt (or after pasting only the URL).

## Open

Does ChatGPT Plus follow a GitHub URL deeply enough in a scheduled task, or do we still need the courier path (`human` commits the files ChatGPT prints)?
