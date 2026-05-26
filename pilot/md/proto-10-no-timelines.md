---
name: NO TIMELINES on public sites
description: Public-facing FAF surfaces (websites, demos, READMEs, social posts, etc.) carry NO timelines, NO future-dated promises, NO "coming in N weeks," NO "Phase X landing soon." State current capabilities. Future work goes in private docs / project memos / internal task lists. wolfejam doctrine 2026-05-08.
type: feedback
---
**Rule:** **NO timelines on public sites.** Public-facing FAF surfaces — websites, demos, READMEs, blog posts, social, anything visible to outside audiences — carry zero future-dated promises.

Forbidden phrases on public copy:
- "Coming in N weeks"
- "Phase 1 landing soon"
- "Real X arriving in 4–6 weeks"
- "Next month / quarter / sprint"
- "Q3 2026"
- Any specific date for unfinished work
- Any "Phase N" label that implies future delivery

What public copy SHOULD say instead:
- "X is the next deliverable" (no when)
- "Demo numbers are measured on Y" (current state)
- "Engine numbers are real" (current state)
- "In-browser WASM execution is the next phase" (no when, just sequence)
- Version numbers (current state, like `v0.1.0`)

**Why:** wolfejam doctrine 2026-05-08: *"NO TIMELINES on public sites."* Direct rule. Connects to:
- **Quiet Receipt doctrine** — operational receipts over broadcast promises
- **Receipts not promises** (semver memory) — don't bump until receipts; don't claim until shipped
- **Brand discipline** — outside audiences don't get to hold us to estimates we made internally
- **Look like infrastructure, not launch** — quiet ship doctrine
- **The 4-6 week Phase 1 estimate ended up being hours** — proof that timelines on public sites are usually wrong AND visible to anyone who later checks them

**How to apply:**
- Editing any public-facing markdown / HTML / copy → grep for "weeks", "months", "Phase N landing", "coming", "soon", future-dated language → strip
- Internal docs / project memos / private notes / memories → timelines are FINE there (they help planning)
- Status labels like "Phase 1" can be a problem if they imply future-phase promises; safest to drop or convert to version numbers
- ROADMAP.md is a special case — it CAN have phase descriptions and high-level goals, but specific dates ("4-6 weeks") should still be avoided in the public-facing form
- Test: would a competitor screenshot this and laugh in 6 weeks if we missed the date? If yes, strip it.

**Counter-doctrine warning:** Don't go to the opposite extreme and refuse to describe future work at all. The line is between sequence ("X comes next") and promise ("X comes in 4 weeks"). Sequence is fine, promise is not. Phase descriptions ARE OK as long as they describe scope ("Phase 2 — production grade") not duration ("Phase 2 lands in 8 weeks").

**The Soon clause (wolfejam refinement 2026-05-12):** *"Soon"* + capability language is fine **when we're wiring up existing tested capability, not day-dreaming.* Operational test:
- Engine built + tested? → "Soon" is sequence (fine on public copy)
- Engine doesn't exist yet? → "Soon" is promise (forbidden)
- Capability tested in isolation, just not yet exposed? → "Soon: we'll wire X to Y" is fine — the work is integration, not invention

Example pass: *"Soon, the Agent will read live from FAF-RAG."* — RAG exists, faf-sync exists, Agent has the rag_client, we're connecting tested wires. Sequence + capability + integration scope = safe.

Example fail: *"Soon, the Agent will support 50 languages."* — capability doesn't exist; this is invention dressed as integration. Forbidden.

**Adjacent doctrines:**
- `quiet-receipt-doctrine.md` — operational receipts over broadcast
- `feedback-semver-receipts-not-promises.md` — semver discipline
- `faf-dont-lie-deterministic-scoring.md` — measurement vs opinion
