---
name: ""
metadata: 
  node_type: memory
---

**The word "wins" (and "win" / "winning") is banned in FAF context.** Public copy, internal copy, marketing, technical docs, GitHub comments, READMEs — anywhere.

**Why:** wolfejam, 2026-05-12 — *"'wins' is a ridiculous word in FAF."* Said after I'd drafted close comments using `.faf wins on conflict` and `sdk wins over library/cli/wasm`. The objection went deeper than competitive framing: the word itself is wrong for FAF. Parallels the existing `Guaranteed` ban in CLAUDE.md (*"We dont do Guarantees, its free software. The word 'Guaranteed' or any version of it are BANNED."*).

**How to apply:** Never write "wins / win / winning" in FAF context. Substitutes by intent:

| Instead of...                         | Use...                                          |
|---------------------------------------|-------------------------------------------------|
| `.faf wins on conflict`               | `.faf is canonical for shared fields`           |
| `sdk wins over library/cli/wasm`      | `sdk-priority detection routes mixed signals`   |
| `X wins`                              | `X is authoritative / takes precedence / applies` |
| `winning strategy`                    | `chosen approach / canonical path`              |
| `who wins?`                           | `which is authoritative?`                       |

The canonical operational doctrine is the 2-clause form: **"ROM defines. RAM executes."** (see `rom-defines-ram-executes.md`). FAF is ROM, AI is RAM, bi-sync binds. No third "wins" clause — that was a 2026-05-11 fabrication, deleted 2026-05-13 (never said by wolfejam).

Companion: `feedback-quote-doctrine-whole-or-skip.md` — paraphrase rule. This one is the underlying word ban.
