---
name: "Stateless and Stubless" — MCPaaS brand line (wolfejam 2026-05-12)
description: Two-word slogan coined by wolfejam right after the v1.5.17 stub-copy refresh. Captures MCPaaS engineering identity — stateless (SEP-2567 DONE in prod) + stubless (SEP-2663 full lifecycle, the v1.6 commitment). Both "less" describe what's NOT there as the feature.
type: project
---
# "Stateless and Stubless" — MCPaaS Brand Line

**Coined by wolfejam 2026-05-12 03:48 UTC**, immediately after the v1.5.17 Tasks stub-copy refresh deploy.

## Why It Works

```
  stateless     SEP-2567 / SEP-2575 — server holds no session
                state between requests. Done. Live in prod
                tonight at v1.5.17.

  stubless      SEP-2663 full Tasks lifecycle — no more
                _stub: true responses. The commitment. v1.6
                lane on infrastructure that already exists
                (waitUntil + KV + crons).

  Two adjectives. Alliterative. Parallel "-less" suffix on
  both. "Less" describes what is NOT there as the feature —
  no state, no stubs. Same shape as "fearless," "tireless."

  Engineering identity in 3 words.
```

## Maps Directly to Tonight's Work

| Word | Status | Receipt |
|------|--------|---------|
| Stateless | ✅ DONE | mcpaas.live v1.5.17 enforces SEP-2567 strict mode in production; HEADER_MISMATCH -32001 without proper headers; `_sessionMode: "stateless"` confirmed |
| Stubless | ✅ DONE (2026-05-12 04:00 UTC) | mcpaas.live v1.6.0 ships real KV-backed task lifecycle. Live receipt: `tasks/create generate_faf_from_github Wolfe-Jam/grok-faf-mcp` → queued → running → complete in 700ms, score 100, full .faf returned. NO `_stub: true` anywhere. 8/8 Tyres tests green against deployed worker `<worker-id-redacted>`. |

## Status — Both Halves Hold (2026-05-12)

**The brand line is now deployable in public copy.** Both halves verifiable by curl against `mcpaas.live/mcp`:

```
stateless  →  POST /mcp without Mcp-Method header → -32001 HEADER_MISMATCH
              (SEP-2567 strict-mode default enforced)

stubless   →  POST /mcp tasks/create + tasks/get → full lifecycle returns
              real result with NO `_stub: true` field
              (SEP-2663 real KV-backed implementation, v1.6.0+)
```

**Deployable surfaces:**
- X / public posts ✅
- README copy ✅
- mcpaas.live tagline ✅
- vendor inbox lines ✅

The phrase served its purpose as a forcing function — coined 03:48 UTC, stubless deployed 04:00 UTC, ~12 minutes from coinage to receipt.

## Cross-References

- Stateless side: `mcpaas-live-sessionless-mcp-reference-impl-2026-05-11.md` (the deploy receipt)
- Stubless side: `mcpaas-tasks-infrastructure-already-exists.md` (the path to make it true)
- Doctrine: `doesnt-claim-what-wasnt-measured.md` — don't use the phrase publicly until both halves hold
- Doctrine: `quiet-receipt-doctrine.md` — even after stubless ships, the receipt IS the broadcast; the phrase is the label, the curl-able behavior is the proof
- Adjacent: `zeph-brand-register-locked.md` — same shape, MCPaaS brand register starts here
