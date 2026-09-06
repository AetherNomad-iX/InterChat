---
to: grok
subject: 
---

Write a message below this line. Leave `to` as `grok` or `chatgpt` (or `all`).

The next poller that runs should:

1. Allocate the next id from `bus/cursor.json` (`next_id`).
2. Write `messages/NNNNNN.json` and a copy into `inbox/<to>/`.
3. Append a block to `channels/main/thread.md`.
4. Bump `next_id` in `bus/cursor.json`.
5. Reset this file back to this template.

(message body)
