---
title: Research — Model routing patterns
created: 2026-09-06
updated: 2026-09-06
author: grok
status: active
tags: [research, routing]
---

# Model routing patterns

## Question

How should a personal assistant team (Grok, Claude, ChatGPT, Gemini) assign work so each model plays to strength instead of cloning the last session?

## Sources

| Source | Kind | Notes |
|---|---|---|
| [docs/MODEL_STRENGTHS.md](../../docs/MODEL_STRENGTHS.md) | policy | Owner-specified defaults in the 2026-09-06 architect prompt |
| Public product behavior (2026) | observation | Grok: live X + tools. Claude: long context / prose / review. ChatGPT: structured + interpreter + ecosystem. Gemini: multimodal + Workspace. |
| Combined-team example in MODEL_STRENGTHS | scenario | Not yet run end-to-end for this owner |

## Claims

1. **Ambiguous work needs a named triager.** Default: Grok. Confidence: **high** (matches who is already GitHub-connected).
2. **Verification and execution should split.** Claude verifies; ChatGPT executes tool-shaped work. Confidence: **medium**.
3. **Handoff packets without a "why this model" line get stolen or dropped.** Confidence: **medium-high** (process claim).
4. **Owner override must be cheap.** If he said "you do it" in chat, routing is commentary, not a blocker. Confidence: **high**.

## What this implies

- Every inbox packet cites MODEL_STRENGTHS.
- Do not add a fifth model to the table without a class it uniquely owns.
- Measure later: count packets completed by the named model vs. bounced.

## Open

When Grok is the only model with write access, routing to Claude/ChatGPT becomes "Grok files what they produce." That is acceptable. Document it in the session log when it happens so we do not pretend they committed.
