# LLM Comparison — Agentic Project Management
**Source:** Arena.ai leaderboard (342,134 sessions, May 30 2026) + provider pricing pages  
**Generated:** June 2026 | **Review cycle:** Quarterly or on major model release

---

## TL;DR — Default Model Selection

| Scenario | Use this model | Why |
|---|---|---|
| Primary orchestrator (most tasks) | Claude Sonnet 4.6 | Best cost/capability balance; flat 1M ctx; #2 Bash Recovery |
| High-stakes / confirmed completion | Claude Opus 4.7 Thinking | #1 Confirmed Success (7.95%); leads Document + Text Arena |
| Max steerability / tool orchestration | GPT-5.5 High | #1 Agent Arena; #1 Steerability (12.03%); #1 Bash Recovery (17.73%) |
| High-volume triage / classification | Gemini 2.5 Flash | $0.30/$2.50/M — 10× cheaper output than Sonnet; use for sub-agents only |
| Budget mid-tier coding | GPT-5.4 Mini | $0.40/$1.60/M; 94% of GPT-5.4 coding performance |

---

## Token Pricing Reference (June 2026)

All prices USD per 1 million tokens (input / output).

### Anthropic Claude

| Model | Input /1M | Output /1M | Context | Batch | Cache |
|---|---|---|---|---|---|
| Claude Opus 4.7 | $5.00 | $25.00 | 1M flat | 50% off | 90% off input |
| Claude Opus 4.6 | $5.00 | $25.00 | 1M flat | 50% off | 90% off input |
| Claude Sonnet 4.6 | $3.00 | $15.00 | 1M flat | 50% off | 90% off input |
| Claude Haiku 4.5 | $1.00 | $5.00 | 200K | 50% off | 90% off input |

> **Key advantage:** 1M context at flat rate — no surcharge at any prompt size (Opus 4.7, Opus 4.6, Sonnet 4.6).  
> **Cache write cost:** 1.25× base for 5-min TTL; 2× base for 1-hr TTL. Cache read: 0.1× base.

### OpenAI GPT

| Model | Input /1M | Output /1M | Context | Notes |
|---|---|---|---|---|
| GPT-5.5 | $5.00 | $30.00 | 1M | Flat rate |
| GPT-5.5 Pro | $30.00 | $180.00 | 1M | Research / high-accuracy only |
| GPT-5.4 | $2.50 | $15.00 | 1M* | **⚠ Surcharge above 272K tokens** |
| GPT-5.4 Mini | $0.40 | $1.60 | 128K | High-volume budget option |

> **⚠ GPT-5.4 long-context trap:** Input cost doubles from $2.50 → $5.00/M for tokens above 272K.  
> Batch API: 50% discount (async, 24-hr delivery). Cached input: $0.50/M on GPT-5.5.

### Google Gemini

| Model | Input /1M | Output /1M | Context | Notes |
|---|---|---|---|---|
| Gemini 3.1 Pro (Preview) | $2.00 | $12.00 | 1M* | **⚠ Doubles above 200K** |
| Gemini 2.5 Pro | $1.25 | $10.00 | 1M* | **⚠ Doubles above 200K** |
| Gemini 2.5 Flash | $0.30 | $2.50 | 1M* | **⚠ Doubles above 200K** |
| Gemini 2.5 Flash-Lite | $0.10 | $0.40 | 1M | No surcharge; cheapest option |

> **⚠ Gemini long-context trap:** All Pro/Flash models charge double input AND output above 200K tokens per call.  
> Grounding with Google Search billed separately ($14–$45/1K requests depending on tier).  
> Batch API: 50% off (async). Free tier: up to 1,000 requests/day via AI Studio.

---

## Arena.ai Leaderboard Rankings (Human Preference)

### Agent Arena — top 10 (342,134 sessions, May 30 2026)

Ranked on: net improvement, confirmed success, praise/complaint ratio, steerability, bash recovery, tool hallucination rate.

| Rank | Model | Net Improvement | Confirmed Success | Steerability | Bash Recovery |
|---|---|---|---|---|---|
| 1 | GPT-5.5 High | 10.66% | 7.06% | **12.03%** | **17.73%** |
| 2 | Claude Opus 4.7 Thinking | 9.47% | **7.95%** | 9.04% | 16.69% |
| 3 | GPT-5.4 High | 8.92% | 6.89% | 10.12% | 16.34% |
| 4 | Claude Opus 4.6 | 8.14% | 7.17% | 7.06% | 16.26% |
| 5 | GPT-5.5 | 7.47% | 2.97% | 8.91% | 16.58% |
| 6 | Claude Opus 4.7 | 6.95% | 5.46% | 5.60% | 15.95% |
| 7 | Claude Sonnet 4.6 | 4.59% | 1.22% | 3.38% | **17.23%** |
| 9 | Gemini 3.1 Pro Preview | 1.38% | 0.64% | 4.33% | 0.95% |
| 10 | Gemini 3.5 Flash | 0.40% | 2.46% | 1.17% | 4.08% |

> **Signal leaders:**  
> - Confirmed task done: Claude Opus 4.7 Thinking (7.95%)  
> - Steerability: GPT-5.5 High (12.03%)  
> - Bash recovery: GPT-5.5 High (17.73%) — Claude Sonnet 4.6 close at #2 (17.23%)  
> - Tool hallucination (lowest = best): Claude Sonnet 4.6 (1.43%)

### Text Arena — overall ranking (relevant models only)

| Rank | Model | Expert | Coding | Creative | Instruction Following |
|---|---|---|---|---|---|
| 1 | Claude Opus 4.6 Thinking | 1 | 1 | 1 | 1 |
| 2 | Claude Opus 4.7 Thinking | 6 | 2 | 2 | 2 |
| 3 | Claude Opus 4.6 | 2 | 4 | 6 | 3 |
| 4 | Claude Opus 4.7 | 3 | 3 | 4 | 4 |
| 6 | Gemini 3.1 Pro Preview | 7 | 8 | 5 | 6 |
| 8 | GPT-5.5 High | 4 | 12 | 16 | 7 |
| 9 | GPT-5.4 High | 5 | 13 | 25 | 8 |
| 21 | Claude Sonnet 4.6 | 11 | 10 | 18 | 9 |
| 49 | Gemini 2.5 Pro | 59 | 84 | 27 | 43 |
| 104 | Gemini 2.5 Flash | 102 | 142 | 73 | 101 |

### Other Arena categories — top 3 per category (PM-relevant)

| Category | #1 | #2 | #3 |
|---|---|---|---|
| WebDev / Code | Claude Opus 4.7 Thinking | Claude Opus 4.7 | Claude Opus 4.6 Thinking |
| Document | Claude Opus 4.6 | Claude Opus 4.6 Thinking | Claude Opus 4.7 |
| Search | Claude Opus 4.6 (search) | GPT-5.5 search | Claude Opus 4.7 |
| Vision | Claude Opus 4.7 Thinking | Claude Opus 4.6 Thinking | Claude Opus 4.7 |

---

## Cost Scenario — 1,000 Agentic PM Tasks/Day

Assumes 2,000 input tokens + 800 output tokens per task.  
Daily: ~2M input tokens + 800K output tokens. Monthly ≈ 30×.

| Model | Daily (standard) | Daily (w/ savings) | Savings mechanism | Monthly est. |
|---|---|---|---|---|
| Claude Sonnet 4.6 | $18.00 | ~$4.80 | 90% prompt cache hit on system prompt | ~$144 |
| Claude Opus 4.7 | $26.00 | ~$13.00 | 50% batch API | ~$390 |
| GPT-5.5 High | $29.00 | ~$14.50 | 50% batch API | ~$435 |
| GPT-5.4 High | $17.00 | ~$8.50 | 50% batch API | ~$255 |
| Gemini 2.5 Flash | $2.60 | ~$1.30 | 50% batch API | ~$39 |

> **Caching multiplier:** Claude's 90% cache discount is most powerful for PM agents that reuse large system prompts, project charters, or knowledge bases across many calls. On a 50K-token shared context, caching alone can reduce input cost from $0.15 → $0.015 per call.

---

## Capability Summary — PM Workflow Fit

### Document & Writing (PRDs, BRDs, SOPs, status reports)
- **Best:** Claude Opus 4.6 / Opus 4.7 (leads Document Arena #1–3)
- **Mid:** Claude Sonnet 4.6 (#7 Document Arena at fraction of cost)
- **Avoid for primary drafting:** Gemini Flash (ranked ~100+ in text tasks)

### Multi-step Agentic Execution (tool chains, MCP workflows)
- **Best confirmed completion:** Claude Opus 4.7 Thinking (7.95%)
- **Best steerability:** GPT-5.5 High (12.03%) — use when the agent must follow exact user direction across many turns
- **Best error recovery:** GPT-5.5 High (#1) and Claude Sonnet 4.6 (#2) for bash/tool recovery

### Long-context Sessions (project history, large codebases, audit trails)
- **Best economics:** Claude Sonnet 4.6 / Opus 4.6 / Opus 4.7 — 1M flat with no per-tier surcharge
- **Avoid for >200K calls:** All Gemini Pro/Flash (input cost doubles); GPT-5.4 (doubles above 272K)

### High-volume Sub-agent Tasks (triage, classification, status roll-up)
- **Best:** Gemini 2.5 Flash ($0.30/$2.50) or GPT-5.4 Mini ($0.40/$1.60)
- **Acceptable quality floor:** Gemini 2.5 Flash ranked #104 overall text — suitable for structured extraction, not nuanced reasoning

### Search-augmented PM (grounded web/doc retrieval)
- **Best:** Claude Opus 4.6 search variant (#1 Search Arena)
- **Runner-up:** GPT-5.5 search (#2), Gemini 3.1 Pro grounding (#6)

---

## Recommended Stack — Enterprise PM / Healthcare IT Context

```
Primary orchestrator:    Claude Sonnet 4.6
  └─ Escalate to:        Claude Opus 4.7 Thinking  (milestone sign-off, confirmed completion tasks)
  └─ Sub-agent (volume): Gemini 2.5 Flash           (triage, classification, status extraction)
  └─ Dev/coding tasks:   GPT-5.5 High               (if steerability / terminal automation needed)

MCP integrations:        Notion · n8n · Google Calendar · Gmail · Figma
Cache strategy:          Cache system prompt + project charter on every Sonnet call
Batch mode:              Use for nightly report generation, non-urgent summarization
```

---

## Flags & Gotchas

- **Gemini thinking tokens:** Billed separately on top of output tokens — factor in for reasoning-heavy calls.
- **GPT-5.5 Pro:** $30/$180/M — only justified for highest-stakes research or legal/medical analysis.
- **Gemini 3.1 Pro:** Still in preview as of June 2026 — GA pricing may differ; test before committing budget.
- **Claude Opus 4.7 new tokenizer:** Up to 35% more tokens generated vs Opus 4.6 for same input — benchmark your workloads before migrating from Opus 4.6.
- **Batch API delivery:** Async, typically within 24 hours — not suitable for real-time PM agent loops.
- **"Lost in the middle" effect:** Accuracy drops 30%+ in the center of long contexts (all models). Keep CLAUDE.md under 200 lines; use `@file` references for full detail docs.

---

## Usage in Claude CLI

```bash
# Pipe as one-shot context
cat llm-comparison-reference.md | claude "recommend model for my FHIR webhook routing task"

# Reference in-session
@llm-comparison-reference.md which model should handle nightly batch EHR summarization?

# In CLAUDE.md — add a pointer, not the full file
## LLM Selection
See @docs/llm-comparison-reference.md for model rankings, pricing, and Arena scores.
Default: Claude Sonnet 4.6. Escalate to Opus 4.7 Thinking for confirmed-completion workflows.
```

---

*Prices verified June 2026. Arena.ai data: 342,134 sessions as of May 30 2026.*  
*Next review: September 2026 or on GPT-6 / Gemini 4 / Claude Opus 5 release.*

---

## API Inventory — Agentic PM Stack

**Total: 18 APIs across 6 categories**  
Last reviewed: June 2026

---

### Category 1 — LLM Providers (3 APIs)

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| Anthropic Claude | `api.anthropic.com` | P1 | Primary orchestrator (Sonnet 4.6); confirmed-completion tasks (Opus 4.7 Thinking); document generation; MCP tool calls | Separate keys per env (dev/prod). Enable prompt caching for system prompts. Batch API for nightly jobs. |
| OpenAI | `api.openai.com` | P1 | Steerability-critical agent loops (GPT-5.5 High); terminal/bash automation; computer use workflows | GPT-5.5 output at $30/M — set hard token budget limits. Watch 272K surcharge on GPT-5.4. |
| Google Gemini | `generativelanguage.googleapis.com` | P2 | High-volume sub-agent tasks (triage, classification, status extraction); Google Workspace-native flows | Use Flash only for volume tasks. ⚠ Avoid calls >200K tokens — cost doubles. Thinking tokens billed separately. |

---

### Category 2 — Observability & Evaluation (3 APIs)

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| DeepEval (or Ragas) | `deepeval` / `ragas` (self-hosted or cloud) | P1 | Eval scoring: task completion, hallucination rate, faithfulness across model runs | DeepEval = open source, general purpose. Ragas = RAG-focused. Pick one as primary eval scorer. |
| Langfuse | `cloud.langfuse.com` | P1 | Trace every LLM call, tool use, and token spend across all three providers in one dashboard | Complements DeepEval — tracing ≠ eval scoring. SDK wraps OpenAI, Anthropic, Gemini. Self-host option available. |
| Postman API | `postman.com` (MCP-connected) | P2 | Test and validate all downstream API integrations; automated API health checks in CI pipeline | Already MCP-connected. Postman Collections serve as living API documentation for the full stack. |

---

### Category 3 — Project Management & Knowledge (3 APIs)

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| Atlassian (Jira + Confluence) | `{site}.atlassian.net/rest/api/3` (Jira) · `/wiki/rest/api` (Confluence) | P1 | Jira: create/update issues, sprint management, status sync from agent actions. Confluence: read/write SOPs, ADRs, release notes | One API key covers both. Use Jira Automation webhooks to trigger agent actions on issue transitions. |
| Notion | `api.notion.com` (MCP-connected) | P1 | Project knowledge base, stakeholder docs, meeting notes, decision logs — agent reads/writes structured databases | Already MCP-connected. Use Notion databases (not just pages) for structured PM data agents can query/update programmatically. |
| GitHub | `api.github.com` | P2 | Read PR status, issues, CI results, release tags for DH Connect / Rhapsody dev context; auto-generate release notes | Fine-grained PAT for private repos. Claude Code uses `gh` CLI natively — install alongside API key for best results. |

---

### Category 4 — Google Workspace (4 APIs)

> **Note:** Split from single "Google Account" entry. Four separate OAuth scopes; manage independently in Google Cloud Console.

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| Gmail API | `gmail.googleapis.com` (MCP-connected) | P1 | Recruiter email triage, stakeholder thread summarization, auto-draft responses | Already MCP-connected. Scope: `gmail.readonly` + `gmail.compose` minimum. Separate OAuth scopes per service — do not bundle into one service account. |
| Google Calendar API | `calendar.googleapis.com` (MCP-connected) | P1 | Schedule PM events, gym/work reminders, meeting blocks; agent checks availability before booking milestones | Already MCP-connected. Use service account for automated scheduling; OAuth for interactive flows. Scope: `calendar.events`. |
| Google Sheets API | `sheets.googleapis.com` | P2 | Job tracker updates (13-field recruiter pipeline), token cost tracking, sprint velocity dashboards | Not in current MCP set — add via Google Drive MCP (already connected) or direct API key. Sheets API v4 for read/write/append. |
| Google Drive API | `drive.googleapis.com` (MCP-connected) | P2 | Read/index project documents, upload agent-generated reports, search Drive for project artifacts | Already MCP-connected — document explicitly. Enables Claude to find uploaded SOPs, PRDs, and resume files from conversation context. |

---

### Category 5 — Automation & Workflow Orchestration (2 APIs)

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| n8n | `blokapati.app.n8n.cloud` (MCP-connected) | P1 | Workflow glue between all APIs — Jira→Notion sync, recruiter email→Sheets pipeline, nightly PM report triggers; LLM nodes call Claude/GPT from workflow steps | Already MCP-connected. Migrate existing Zapier recruiter workflow here. n8n supports native LLM nodes. |
| Zapier | `hooks.zapier.com` | P3 | Legacy bridge for existing Zapier AI Agent (recruiter email → Sheets) | Keep active during n8n migration. Deprecate once recruiter pipeline is rebuilt in n8n — cheaper at scale. |

---

### Category 6 — Diagramming, Design & Infrastructure (3 APIs)

| API | Endpoint | Priority | Role in stack | Key flags |
|---|---|---|---|---|
| Mermaid Chart | `chatgpt.mermaid.ai` (MCP-connected) | P2 | Generate and save workflow diagrams, system architecture, FHIR data flow, sprint state machines from agent-produced Mermaid syntax | Already MCP-connected. REST API supports create/update/export. Powers Mermaid Knowledge Base Generator project (Phase 1 in progress). |
| Figma | `api.figma.com` (MCP-connected) | P3 | Pull design specs for DH Connect UI features; agent reads Figma designs to generate implementation tickets in Jira | Already MCP-connected. Low priority unless DH Connect roadmap involves UI deliverables. |
| Secrets Manager | HashiCorp Vault or AWS Secrets Manager | P1 | Centralized, rotatable storage for all 18 API keys across the stack | ⚠ Healthcare IT context (Alcon/DH Connect): 18 API keys in .env files is a compliance risk. Inject at runtime. Never hardcode in CLAUDE.md or repo. Confirm BAA coverage. |

---

### Not Recommended — Google Antigravity

**Decision: Exclude from stack (June 2026)**

Google Antigravity 2.0 (announced Google I/O 2026) is an agent-first development platform — IDE, CLI (`agy`), SDK, and Managed Agents API tier. Analysis against this stack:

| Factor | Finding |
|---|---|
| Functional overlap | Antigravity's programmatic API surface is the Gemini API with stateful sessions — already covered by the Gemini entry above. No net-new capability. |
| Use case fit | Designed for software development workflows (IDE, parallel coding subagents, Firebase/Android). No PM workflow integration surface. |
| Healthcare IT blocker | Antigravity has no confirmed BAA as of June 2026. Treat as public cloud environment — do not use with PII or regulated project data (Alcon/DH Connect context). |
| Architectural role | GUI-first; not designed for headless CI/CD or programmatic PM agent pipelines. |

**Re-evaluate when:** Google issues a BAA covering Antigravity specifically, AND the Managed Agents API adds native PM tool integrations (Jira, Confluence, etc.) not already available via Gemini API directly.

> Note: If your team uses the Gemini CLI today, migrate to the Antigravity CLI (`agy`) before **June 18, 2026** — that deadline affects individual Google AI Pro/Ultra subscribers only, not enterprise Gemini Code Assist contracts.

---

### API Inventory Summary

| Category | Count | P1 | P2 | P3 | MCP-connected today |
|---|---|---|---|---|---|
| LLM Providers | 3 | 2 | 1 | 0 | 1 (Gemini via Google) |
| Observability & Eval | 3 | 2 | 1 | 0 | 1 (Postman) |
| PM & Knowledge | 3 | 2 | 1 | 0 | 1 (Notion) |
| Google Workspace | 4 | 2 | 2 | 0 | 3 (Gmail, Calendar, Drive) |
| Automation | 2 | 1 | 0 | 1 | 1 (n8n) |
| Diagramming & Infra | 3 | 1 | 1 | 1 | 2 (Mermaid, Figma) |
| **Total** | **18** | **10** | **6** | **2** | **9** |

**P1 APIs to set up first (10):** Claude · OpenAI · DeepEval · Langfuse · Atlassian · Notion · Gmail · Google Calendar · n8n · Secrets Manager

