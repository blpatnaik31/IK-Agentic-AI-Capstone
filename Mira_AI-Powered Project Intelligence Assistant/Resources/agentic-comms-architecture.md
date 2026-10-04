# Agentic AI Communication Architecture
**Reference Guide for Enterprise Program Management**
*Author: Lokapati Patnaik Bhogela, PMP, CSPO, CSM*
*Version: 1.0 | Domain: Stakeholder Communications | Context: Healthcare IT / Regulated Environments*

---

## 1. Core Design Principles

An Agentic AI communication system must classify, draft, guardrail, and refine every communication before delivery. The four pillars are:

1. **Audience Segmentation** — Who receives this?
2. **Intent Classification** — Why is this being sent?
3. **Regulatory Guardrails** — What constraints apply?
4. **Feedback Loop** — How does the agent improve?

---

## 2. Audience Segmentation Matrix

Every communication is routed through a two-axis classification before drafting.

| Tier | Role Examples | Tone | Length | Format |
|---|---|---|---|---|
| **Executive** | C-Suite, SVP, VP | Bottom-line first, risk-framed | 3–5 bullets max | Email / Executive Summary |
| **Senior Leadership** | Director, Sr. Manager | Context + data, options presented | Short paragraphs | Email / Slide Brief |
| **Delivery Team** | Manager, PM, IC, Tech Lead | Task-oriented, full context | Full detail | Email / Ticket / Slack |
| **External Stakeholder** | Client, Vendor, Partner | Formal, relationship-aware | Moderate | Email / Meeting Notes |
| **Regulatory / Compliance** | QA, FDA Liaison, Auditor | Precise, traceable, passive voice | Exact as required | Formal Document / Memo |

> **Rule:** Audience Tier drives tone, length, format, and channel — before content is drafted.

---

## 3. Communication Intent Classification

The agent detects intent and routes to the appropriate structural template.

| Intent | Signal Words / Triggers | Priority | Owner Action Required? |
|---|---|---|---|
| 🔴 **Escalation** | "blocked", "at risk", "missed SLA", "critical" | Urgent | Yes — named owner + resolution path |
| 🟡 **Status Report** | "update", "week of", "sprint", "milestone" | Scheduled | Optional |
| 🟢 **Decision Request** | "decision needed", "approve", "options", "recommend" | High | Yes — clear ask + deadline |
| 🔵 **FYI / Awareness** | "heads up", "for your awareness", "no action needed" | Low | No |
| ⚪ **Meeting Prep / Briefing** | "prep", "talking points", "agenda", "briefing" | As scheduled | No |
| 📋 **Change Communication** | "change request", "scope change", "go-live", "cutover" | High | Yes — stakeholder acknowledgment |

---

## 4. Structural Templates by Archetype

### 4.1 Executive Status Email
```
Subject: [Project Name] | [🔴/🟡/🟢 RAG Status] | Week of [Date]

One-line health summary (status + trend).

Key risk or decision requiring attention:
- [Risk/Issue]: [Impact]
- [Ask]: [What is needed, from whom, by when]

No attachments unless requested.
```

### 4.2 Operational Update (Delivery Team)
```
Subject: [Project] Sprint [#] Update | [Date]

COMPLETED:
- [Item] — [Owner]

IN PROGRESS:
- [Item] — [Owner] — [% complete or due date]

BLOCKERS / DEPENDENCIES:
- [Blocker] — [Impact] — [Escalation path]

NEXT ACTIONS:
- [Action] | [Owner] | [Due Date]
```

### 4.3 Escalation Notice
```
Subject: [ESCALATION] [Project] — [Issue Summary] — Action Required by [Date]

SITUATION: [1-sentence summary of the issue]
IMPACT: [Schedule / Budget / Scope / Quality impact]
ROOT CAUSE: [Known or suspected]
OPTIONS:
  A) [Option] — [Trade-off]
  B) [Option] — [Trade-off]
RECOMMENDATION: [Preferred path]
DECISION NEEDED FROM: [Name/Role] BY: [Date/Time]
```

### 4.4 Decision Request
```
Subject: [Decision Required] [Topic] — [Project] — Due [Date]

CONTEXT: [2–3 sentences of background]

OPTIONS:
  1. [Option A] — Pros: [x] | Cons: [x] | Risk: [x]
  2. [Option B] — Pros: [x] | Cons: [x] | Risk: [x]

RECOMMENDATION: Option [#] — [One-line rationale]

REQUESTED ACTION: Approve Option [#] or redirect by [Date].
```

### 4.5 Regulatory / Compliance Communication
```
[Formal Header — Document Number, Version, Date]

PURPOSE: This communication is issued to inform [Role/Body] of [subject].

BACKGROUND: [Factual, passive-voice narrative]

FINDINGS / STATUS: [Documented facts only]

REQUIRED ACTION / NEXT STEPS:
  - [Action] | [Owner] | [Target Date]

DOCUMENT CONTROL: [Change log, approvals, distribution list]
```

---

## 5. Regulatory & Compliance Guardrails

> **Critical for Healthcare IT, Medical Devices, and Pharma contexts.**

| Rule | Applies To | Enforcement |
|---|---|---|
| No PHI in subject lines or unencrypted channels | All HIPAA-scope communications | Pre-send scan |
| Passive voice for audit-trail language | FDA / ISO / 21 CFR Part 11 contexts | Template lock |
| Change control language trigger | Any comms touching validated systems | Intent classifier flag |
| Secure channel routing | Any content referencing patient data | Channel check at routing layer |
| Document version control | Regulatory memos, change requests | Header enforcement |
| No informal language | External regulatory bodies | Audience tier lock |

---

## 6. Agentic Workflow Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     INPUT                               │
│   Intent + Audience + Context + Project State           │
└───────────────────────┬─────────────────────────────────┘
                        ↓
              ┌─────────────────┐
              │   CLASSIFIER    │
              │  Audience Tier  │
              │  Intent Type    │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │TEMPLATE SELECTOR│
              │ Structural arch-│
              │ etype selection │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │CONTEXT INJECTOR │
              │ Stakeholder reg │
              │ Project state   │
              │ Relationship Hx │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │ DRAFT GENERATOR │
              │ LLM call with   │
              │ system prompt   │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │ GUARDRAIL LAYER │
              │ Compliance check│
              │ PHI scan        │
              │ Tone check      │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │  REVIEW GATE    │
              │ Human-in-loop   │
              │ or auto-send    │
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │FEEDBACK CAPTURE │
              │ Log edits       │
              │ Outcome / rating│
              └────────┬────────┘
                        ↓
              ┌─────────────────┐
              │REFINEMENT LOOP  │
              │ Update few-shot │
              │ Adjust weights  │
              └─────────────────┘
```

---

## 7. Context Memory Model

The agent must carry the following state across all communications:

### 7.1 Stakeholder Register Fields
```yaml
stakeholder:
  name: string
  role: string
  tier: executive | senior_leadership | delivery | external | regulatory
  communication_preferences: email | slack | verbal | formal_doc
  sensitivities: list[string]          # e.g., ["prefers no surprises", "detail-oriented"]
  last_interaction_date: date
  last_interaction_summary: string
  open_action_items: list[string]
```

### 7.2 Project State Fields
```yaml
project:
  name: string
  current_rag: red | amber | green
  active_sprint_or_phase: string
  open_risks: list[string]
  open_decisions: list[string]
  last_reported_milestones: list[string]
  next_milestones: list[string]
  regulatory_context: list[string]     # e.g., ["HIPAA", "21 CFR Part 11", "ISO 13485"]
```

---

## 8. Feedback & Continuous Refinement Signals

| Signal Type | Source | How Captured | Used For |
|---|---|---|---|
| **Edited outputs** | PM edits draft before send | Diff tracking | Few-shot prompt tuning |
| **Response rate** | Recipient replies or acts | CRM / email tracking | Template effectiveness |
| **Explicit rating** | Thumbs up/down per draft | UI feedback | Prompt weight adjustment |
| **User overrides** | Tone/length changes | Log delta | Audience model refinement |
| **Escalation triggered** | FYI became an escalation | Post-send classification | Intent model correction |

---

## 9. Healthcare IT Specific Archetypes

Pre-built communication types for regulated program management:

| Archetype | Trigger | Template Section |
|---|---|---|
| Sprint Review Summary | End of each sprint | 4.2 Operational Update |
| Risk Escalation to Sponsor | Any red RAG item | 4.3 Escalation Notice |
| Vendor SLA Breach Notice | SLA threshold crossed | 4.3 Escalation Notice + Legal flag |
| Regulatory Milestone Communication | FDA / ISO checkpoint | 4.5 Regulatory Communication |
| Change Request Communication | CR approved / rejected | 4.4 Decision Request + 5. Guardrails |
| Go-Live / Cutover Notice | Release event | 4.6 (custom: multi-audience broadcast) |
| Steering Committee Brief | Monthly / quarterly | 4.1 Executive Status Email |

---

## 10. Dual-Register Output Pattern

> For high-stakes communications, always generate two versions from a single source input.

```
Source Input: Sprint 3 status + risk log
        ↓
┌──────────────────────────┐    ┌──────────────────────────┐
│  EXECUTIVE VERSION       │    │  DELIVERY TEAM VERSION   │
│  Steering Committee      │    │  PM / Tech Lead / Dev    │
│  - 3-bullet RAG summary  │    │  - Full sprint breakdown │
│  - 1 risk requiring attn │    │  - Blocker list + owners │
│  - 1 ask or decision     │    │  - All action items      │
└──────────────────────────┘    └──────────────────────────┘
```

---

## 11. Standards & Framework Alignment

| Standard / Framework | How It Maps to This Architecture |
|---|---|
| **PMBOK 7 — Stakeholder Engagement Domain** | Sections 2, 3, 7 (segmentation, register, feedback) |
| **PMBOK — Communications Management** | Sections 4, 6 (templates, workflow) |
| **PRINCE2 — Communication Mgmt Strategy** | Sections 2, 4 (format, audience, frequency) |
| **ISO 21502** | Section 5 (guardrails, regulatory comms) |
| **21 CFR Part 11 / FDA** | Section 5 (audit trail, passive voice, document control) |
| **HIPAA** | Section 5 (PHI rules, secure channel routing) |
| **RACI Matrix** | Section 7.1 (stakeholder register, action ownership) |
| **RAG Status Reporting** | Sections 3, 4.1 (intent classification, executive template) |

---

## 12. Quick Reference Card

```
BEFORE DRAFTING — answer these 3 questions:
  1. Who is the audience tier?     → Sets tone + length + format
  2. What is the intent?           → Selects template
  3. Does regulatory context apply?→ Activates guardrail layer

EXECUTIVE RULE:  Bottom line first. One ask. No jargon. Under 150 words.
ESCALATION RULE: Situation → Impact → Options → Recommendation → Ask.
COMPLIANCE RULE: Passive voice. No PHI. Version controlled. Traceable.
AGILE RULE:      Completed → In Progress → Blockers → Next Actions.
DUAL-REGISTER:   Always generate exec + delivery team versions for high-stakes.
```

---

*This document is designed for use as a persistent reference in Claude CLI (`/mnt/skills/` or project context injection). Load as system context or few-shot seed for any communication-generation session.*
