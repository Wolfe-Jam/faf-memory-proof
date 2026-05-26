---
name: mcp-family-five-plus-mcpaas
description: The MCP family arc — Anthropic PR
metadata: 
  node_type: memory
  type: project
---

**The arc: Anthropic #2759 was the start → 5 vendor MCPs + MCPaaS now.**

**Start (origin receipt):**
- **Anthropic PR #2759** — Claude-FAF-MCP merged into `modelcontextprotocol/servers` 2025-10-17. Listed by Anthropic as "Persistent Project Context Server." Same PR # anchors the FAF Ecosystem entry in the MCP Registry. First FAF MCP listed by a frontier AI vendor.

**The 5 key vendor-targeted MCPs (one per surface):**
1. **claude-faf-mcp** — Anthropic / Claude · npm (~12.8k DL) · Official Anthropic steward
2. **grok-faf-mcp** — xAI / Grok · npm (~2.1k DL) · "first MCP for Grok" origin credential — put wolfejam on xAI's radar, enabled ZEPH commission
3. **gemini-faf-mcp** — Google / Gemini · PyPI (~6.9k DL)
4. **faf-mcp** — Cursor / IDEs / VS Code · npm (~3.9k DL) · NOT "universal" (see [[faf-mcp-is-cursor-ide-not-universal]])
5. **rust-faf-mcp** — Rust ecosystem · crates.io

**Plus MCPaaS:**
- **mcpaas.live** — production sessionless MCP. *"Stateless and Stubless"* (locked brand line 2026-05-12). SEP-2567 + SEP-2575 + SEP-2663 live, v1.6.0+. All apps + capabilities under one roof. ~25k weekly CF requests.
- Not a 6th MCP — it's the MCP platform/infrastructure surface (apps + capabilities, multi-tenant).

**Plus VML lane (separate, not counted in the 5):**
- **faf-agent-mcp** — Voice of FAF. PyPI (uvx-published, ~2k DL, 422/wk accelerating). Different role: VML/Voice lane, not vendor-targeted IDE/chat context.

**Why this matters:**
- "5 MCPs" is the canonical count for the vendor-targeted family. Don't conflate with faf-agent-mcp (Voice/VML lane) or MCPaaS (platform, not MCP server).
- Anthropic #2759 is the load-bearing origin receipt — start of the arc, falsifiable, dated.
- One MCP per target surface. No "universal" MCP — every MCP is dedicated.

**How to apply:**
- Profile / pitch / vendor docs: lead with #2759 as the start, then enumerate the 5 + MCPaaS.
- Stats per MCP refresh via `/downloads`.
- When someone asks "how many MCPs does FAF have?" — answer: **5 vendor-targeted + MCPaaS platform**, with faf-agent-mcp as a separate VML-lane entry.

Related: [[grok-faf-mcp-first-mcp-origin-credential]] · [[faf-mcp-is-cursor-ide-not-universal]] · [[mcpaas-live-sessionless-mcp-reference-impl-2026-05-11]] · [[mcpaas-stateless-and-stubless-brand-line]] · [[faf-agent-mcp-v0.1.4-first-uvx-receipt]].

wolfejam consolidated 2026-05-13.
