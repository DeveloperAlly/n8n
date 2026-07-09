# n8n Community Templates — Scored Ranking (DRAFT for selection)

**Status:** DRAFT · built ahead of the build gate for Ally to pick from · 2026-07-08
**Purpose:** Select the top ~15 (+10 backups) of Ally's *own* n8n workflows to rebuild clean and publish as a community-template portfolio, positioned for the **n8n Senior Developer Advocate** application.
**Basis:** Scored against a rubric derived from `../n8n-deep-dive.md`. Two flagships verified against their live node graphs (✅); the rest scored from the connected instance's own descriptions + prior verified session memory (📝) and will be re-verified node-by-node at build time.

> **You do the picking.** This is the selection menu. Tell me which rows are in and I build the repo (README write-up · sanitized `workflows/*.json` · per-workflow diagram · setup) for exactly those.

---

## 1. What n8n actually rewards (the rubric)

From `n8n-deep-dive.md`: community is n8n's explicit *moat*; **80%+ of workflows now embed AI agents**; the stated DevRel gap is **"teach the hard 20%"** (MCP, RAG/CAG, agents, evaluations, guardrails, production reliability), not the easy 80%. The application literally asks for a shipped workflow. So the rubric weights AI-agent depth highest.

| Criterion | What it measures | Weight |
|---|---|---|
| **AI-agent depth** | Does it teach the hard 20% — agents, MCP, RAG/CAG, multi-model, LLM-in-the-loop? | ×3 |
| **Reuse / install appeal** | Would a broad slice of the community copy it? | ×2 |
| **DevRel narrative** | Teardown / build-in-public story value; differentiation | ×2 |
| **Reproducibility** | Standard nodes, few exotic deps, clean credentials | ×1 |

Weighted score out of **40**. **Compliance** is a gate, not a score:

- 🟢 **Clean** — publishable as-is after credential-stripping.
- 🟠 **De-brand** — client (GamersLab) logic that must be generalised to a neutral example first.
- 🔴 **Rebuild** — currently relies on a scraper / ToS-grey ingestion (Apify, yt-dlp+cookies, forked MCP); per your call, **rebuild compliant before featuring**.

---

## 2. Ranked shortlist (your own workflows)

| # | Workflow | Outcome goal | AI-agent pattern | Score /40 | Compliance | Verified |
|---|---|---|---|---|---|---|
| 1 | **AI Content Repurposer** | G3 Content | LangChain Agent + Claude (OpenRouter) + structured output parser | **35** | 🟢 Clean | ✅ graph |
| 2 | **CAG Knowledge Base** (GamersLab Context Builder) | G1 AI-depth | Cache-Augmented Generation: Postgres intake bank → composed context cache | **34** | 🟠 De-brand | ✅ graph |
| 3 | **Content-Intelligence RAG** (WF-C Enrichment) | G1 AI-depth | RAG over content_items, demand×gap scoring, Claude tagging, pgvector/Supabase | **34** | 🟢 Clean | 📝 desc |
| 4 | **Production Error-Handler** ⭐ | G2 Reliability | Error trigger → Discord alert + GitHub-issue dedup + classify-by-fix-owner + machine-readable footer | **33** | 🟢 Clean | 📝 memory |
| 5 | **n8n Community Question Monitor** ⭐ | G4 Community | Polls the n8n forum → LLM scores each Q vs your expertise → emails matches | **31** | 🟢 Clean | 📝 desc |
| 6 | **AI Trend Curation** (Brand Trend Intelligence) | G3 Content | RSS/API sources → LLM scoring → Google Sheets | **31** | 🟢 Clean | 📝 desc |
| 7 | **n8n as MCP Client** | G1 AI-depth | MCP Client Tool node calling an external MCP server — n8n's flagship 2025 AI feature | **30** | 🔴 Rebuild (forked MCP → sanctioned/public MCP server) | 📝 memory |
| 8 | **CAG Source Ingestion** | G1 AI-depth | Fetch source → LLM maps facts to intake questions → recomposes the CAG cache | **29** | 🟠 De-brand | 📝 memory |
| 9 | **YouTube → Whisper Transcriber** | G5 On-ramp | Audio → Whisper transcription → LLM insights → commit | **29** | 🔴 Rebuild (yt-dlp+cookies → YouTube Data API + user audio) | 📝 memory |
| 10 | **AI Trend Digest** | G3 Content | Posts in → Claude surfaces trends + content angles → dated markdown digest | **24** | 🟠 Decouple from Apify upstream | 📝 desc |
| 11 | **Multi-Platform Blog Publisher** | G3 Content | Markdown → dev.to + Hashnode → auto-share LinkedIn/X | **23** | 🟢 Clean | 📝 desc |
| 12 | **Reddit Community Capture (native)** | G4 Community | Native Reddit node → r/n8n hot+new + comments → Postgres | **23** | 🟢 Clean | 📝 desc |
| 13 | **Forum Capture** | G4 Community | n8n forum questions → normalise → Postgres content_items | **21** | 🟢 Clean | 📝 desc |
| 14 | **Ghost Publisher (JWT auth)** | G3 Content | Markdown → Ghost Admin API; generates Ghost JWT | **19** | 🟢 Clean | 📝 desc |
| 15 | **Social Publisher** | G3 Content | Text/article → LinkedIn and/or Twitter, routed by platform | **19** | 🟢 Clean | 📝 desc |

⭐ = strongest DevRel differentiators (production-grade + meta-relevant to the role).

### Reading the top of the list
The top 7 hit n8n's "hard 20%" gap: an **AI agent** (1), a **CAG** system (2, 8), a **RAG** system (3), **production reliability** (4), a **DevRel-native community tool** (5), **AI news curation** (6), and **MCP** (7). That cluster is the differentiated story — most community portfolios are all publishing pipelines (11–15), which are useful but commodity.

---

## 3. Backups (next 10)

| Workflow | Why it's a backup | Compliance |
|---|---|---|
| Portfolio Contact Form | Clean beginner on-ramp (webhook → email + Notion + reply) | 🟢 Clean |
| MP4 → GIF Converter | Popular utility (ffmpeg); no AI depth | 🟢 Clean |
| Discord Notify (helper) | Reusable "post to Discord" sub-workflow; pairs with the Error-Handler | 🟢 Clean |
| WF0 LinkedIn Orchestrator | Orchestration/sub-workflow pattern; tied to Apify capture | 🔴 Rebuild |
| Fetch YouTube Video Lists | Playlist/RSS enumeration helper | 🟢 Clean |
| Project Showcase Application | Form → approval → actions (human-in-the-loop approval example) | 🟠 De-brand |
| Post to Ghost / X / LinkedIn (singles) | Atomic single-destination publishers | 🟢 Clean |
| Cookie Writer / Playlist Runner | Infra for the YouTube rebuild | 🔴 Rebuild |
| New Project Submission | Form-intake + validation pattern | 🟠 De-brand |
| GamersLab Outreach (v10) | Full CAG-consuming outreach engine; strong "agentic ops" teardown | 🟠 De-brand |

---

## 4. Excluded (not eligible)

- **Livepeer "→ Mintlify" docs family (9):** client/employer work — not yours to publish (also not exportable).
- **Scraper duplicates superseded by clean versions:** LinkedIn Intelligence Gathering (Apify), WF1 Capture LinkedIn Posts (Apify), WF-A Reddit Capture (Apify variant) — the native-node Reddit (#12) replaces it.
- **Personal/irrelevant:** BFT Glofox Auto-Booking, Fetch Jobs on LinkedIn, "My workflow", "n8n workflow chain", Notion Webhook.

---

## 5. Compliance rebuild plan

| Item | Problem | Clean replacement |
|---|---|---|
| MCP Client demo (#7) | Forked LinkedIn MCP (ToS-grey) | Same MCP-Client-Tool pattern pointed at a **public/sanctioned MCP server**, or n8n's own MCP Server Trigger as the target |
| YouTube Transcriber (#9) | yt-dlp + exported cookies | **Official YouTube Data API** + **user-supplied audio file** → Whisper |
| Trend Digest / Orchestrator (#10, WF0) | Apify LinkedIn scraping upstream | Decouple: accept posts via **webhook/RSS/official API**; the AI-analysis half is already clean |
| CAG items (#2, #8) | GamersLab client nouns | Generalise to a **neutral fictional business**; the Context Builder code is already client-agnostic |
