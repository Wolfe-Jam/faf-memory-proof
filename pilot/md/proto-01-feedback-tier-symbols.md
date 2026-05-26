---
name: FAF tier symbols — no emojis except trophy
description: Tier system uses geometric Unicode symbols from faf-cli, not emoji. Only 🏆 Trophy allowed. Score cap is 100, not 105.
type: feedback
---

FAF tier symbols are geometric Unicode, not emoji. The canonical set from faf-cli (`src/core/tiers.ts`):

🏆 Trophy (100%) — the ONLY emoji
★ Gold (99%) — orange
◆ Silver (95%) — cyan
◇ Bronze (85%) — cyan
● Green (70%) — bold
● Yellow (55%) — dim
○ Red (1%+) — dim
♡ White (0%) — dim

**Why:** Clean, professional, consistent with faf-cli. Old emoji soup (🥇🥈🥉🟢🟡🔴🤍) is deprecated.

**How to apply:** Any UI showing FAF scores must use these symbols. Never use medal/circle emojis. Score maximum is 100 — never 105. Big Orange 🍊 is a badge (AI-awarded), not a score tier.
