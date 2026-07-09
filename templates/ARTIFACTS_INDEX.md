# n8n Community Templates — Artifacts Index

**Purpose:** publishable n8n community templates for Ally's n8n Developer Advocate application. Built + tested in her instance `n8n.developerally.tech` → project `Personal` → folder **n8n-template**; published to the public **creators.n8n.io** portal (creator: `developerally`).
**Status:** 2026-07-08 — 7 built + tested + guideline-compliant (sticky notes added). 1 SUBMITTED (weak, pre-guidelines — see failure below). Sequential publishing gated by n8n (one at a time until 3 approved → verified → batches of 4).

## ⚠️ Governing failure
- **`/CLAUDE_FAILURES.md` F5** — submitted a non-compliant, not-the-best template to the public portal BEFORE reading n8n's guidelines or choosing the best lead. #1 rule broken: **plan & verify before execution**. Memory: [[plan-verify-before-execution]], [[n8n-template-guidelines]].

## Artifacts
| Artifact | Path / ID | Status |
|---|---|---|
| Scored ranking (selection) | `RANKING.md` | DRAFT |
| #1 AI Content Repurposer | instance `Tjhi8VEcE6YO2qdl` · `workflows/01-ai-content-repurposer.json` | ⚠️ SUBMITTED to portal (workflow 16907, "Under review") — weak lead, likely to be rejected (submitted version lacked stickies) |
| #2 CAG Knowledge Base | instance `B3Z0KnD3kCzMswo7` · `workflows/02-cag-knowledge-base.json` | Built + tested + stickied; queue-ready |
| #3 Content Intelligence Enrichment | instance `067MHqxVrP3JsDir` · `workflows/03-content-intelligence-enrichment.json` | Built + tested + stickied |
| #4 Production Error Handler | instance `gjUOIh4XJCDbKxGg` · `workflows/04-production-error-handler.json` | Built + tested + stickied |
| #5 n8n Forum Question Monitor | instance `nDXRAKHH5T8qsqiP` · `workflows/05-forum-question-monitor.json` | Built + tested + stickied |
| #6 AI Trend Curation | instance `HEQsW3Ye3HqXRaXr` · `workflows/06-ai-trend-curation.json` | Built + tested + stickied |
| #7 AI Agent with MCP Client | instance `jxKTI1RdCsYrchxr` · `workflows/07-mcp-client-agent.json` | Built + stickied; validated (needs live MCP to run). **CHOSEN LEAD** once slot frees |

## Next actions
1. When #1 leaves review (likely rejected for missing stickies) → submit the **MCP template** as the lead (its JSON is ready).
2. Then submit #4 Error Handler + #5 Forum Monitor → reach 3 approved → verified creator → batch-submit the rest.
3. Add Set-config nodes; finalize per-template markdown descriptions.
