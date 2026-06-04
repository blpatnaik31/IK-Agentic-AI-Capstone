# IK Agentic AI Capstone Projects

**Course:** Applied Agentic AI for PMs/TPMs  
**Duration:** 2 weeks  
**Goal:** Build an AI-powered multi-agent system, evaluate it, and document design decisions.

---

## Projects Overview

| | CalendarMate | SalesGenie | PRD Genie | Mira |
|---|---|---|---|---|
| **Branch** | `project-1-calendarmate` | `project-2-salesgenie` | `project-3-prd-genie` | `project-4-mira` |
| **Company** | ServionIQ (SaaS) | Oak & Ember (Furniture) | NeuronForge (AI Startup) | Nexora (IT Services) |
| **Core Problem** | 2 hrs/day on meeting logistics | 2–3 hrs/day reading inquiry emails | Hours translating transcripts to PRDs | 3–4 hrs creating project plans |
| **Pattern** | Router (varied request types) | Sequential Pipeline | Sequential Pipeline | Router (varied request types) |
| **Key APIs** | Google Calendar + Gmail (OAuth2) | File upload only | File upload only | File/CSV upload, optional Trello API |
| **Setup Complexity** | Most setup | Fastest | Fastest | Moderate |

---

## Project 1: CalendarMate

**Branch:** `project-1-calendarmate`  
**Best for:** PMs/TPMs who spend significant time on meeting management, scheduling, and email triage.

An AI productivity assistant that generates daily briefings from your calendar and email, schedules meetings via natural language, and summarizes your inbox. Connects to live Google APIs via OAuth2.

### Agents (3–5)
- Orchestrator
- Briefing Agent
- Scheduler Agent
- Email Agent
- Follow-Up Agent

### Core Capabilities (required)
- Daily Briefing
- Smart Scheduling
- Email Summarization

### Extended Capabilities (pick 1+)
- Meeting Follow-Up
- Conflict Resolver
- Attendee Research
- Weekly Digest

### Data Grounding
Live API data — calendar events and emails via Google OAuth2.

### Hallucination Risks
- Inventing meetings that don't exist
- Scheduling without checking availability
- Fabricating email content

### Technical Notes
Requires Google OAuth2 credentials. Mock calendar/email data can be substituted if OAuth setup is challenging.

---

## Project 2: SalesGenie

**Branch:** `project-2-salesgenie`  
**Best for:** PMs/TPMs involved in sales operations, customer inquiries, or product catalog management.

An AI sales assistant that reads inbound inquiry emails, classifies leads as Hot/Warm/Cold, recommends products from a catalog, and generates weekly sales summaries. Works entirely with file uploads — no OAuth needed.

### Agents (3–5)
- Ingestion Agent
- Lead Qualifier Agent
- Product Recommender Agent
- Response Drafter Agent
- Aggregator Agent

### Core Capabilities (required)
- Lead Qualification
- Product Recommendations
- Weekly Sales Insights

### Extended Capabilities (pick 1+)
- Automated Follow-Up Drafting
- CRM Auto-Update
- Competitive Positioning

### Data Grounding
CSV product catalog as the grounding source. Walnut Executive Desk is intentionally out of stock (test case T10).

### Hallucination Risks
- Recommending products not in the catalog
- Inventing pricing
- Classifying vague emails as Hot

### Technical Notes
No API setup needed. All inputs are file uploads.

---

## Project 3: PRD Genie

**Branch:** `project-3-prd-genie`  
**Best for:** PMs/TPMs who write PRDs, work with engineering to scope features, or translate meeting discussions into structured documentation.

An AI documentation assistant that ingests meeting transcripts and stakeholder notes, extracts requirements, generates structured PRDs from a template, and breaks them into epics and user stories. Includes 5 sample transcripts (including contradictory and incomplete ones) to test requirement extraction accuracy.

### Agents (3–5)
- Extractor Agent
- PRD Generator Agent
- Story Breakdown Agent
- Gap Analyzer Agent

### Core Capabilities (required)
- Requirement Extraction
- PRD Generation
- Epic/User Story Breakdown

### Extended Capabilities (pick 1+)
- Gap Analysis
- Scope Estimator
- Version Comparison

### Data Grounding
Transcript text as the grounding source. `prd_template.md` defines the expected output structure.

### Hallucination Risks
- Inventing requirements not stated in the transcript
- Filling in TBD items with assumptions
- Generating a PRD from an empty or near-empty input

### Technical Notes
No API setup needed. All inputs are text files.

---

## Project 4: Mira

**Branch:** `project-4-mira`  
**Best for:** PMs/TPMs who manage project timelines, risk assessments, status reports, and milestone tracking.

An AI project intelligence assistant that generates structured project plans from high-level descriptions, produces categorized risk assessments, and compiles weekly status reports from task board data. Uses a complete sample dataset for ABCDE Ltd. AI Adoption Project — a 6-month timeline, risk matrix, and 25-task Kanban board export.

### Agents (3–5)
- Orchestrator Agent
- Planner Agent
- Risk Assessor Agent
- Status Reporter Agent
- Milestone Tracker Agent

### Core Capabilities (required)
- Project Plan Generation
- Risk Assessment
- Weekly Status Report

### Extended Capabilities (pick 1+)
- Milestone Alert System
- Stakeholder Update Generator
- Resource Allocation Advisor
- Competitive Analysis

### Data Grounding
CSV files — timeline, risk matrix, and task board — as grounding sources. Task board has 1 deliberately Blocked task (T024).

### Hallucination Risks
- Inventing milestones not in the timeline
- Fabricating task statuses
- Generating generic risks instead of project-specific ones

### Technical Notes
No API setup needed for CSV uploads. Optional Trello API integration available.

---

## What Every Project Requires

- Multi-agent system design with documented orchestration pattern
- 3 core capabilities (required) + at least 1 extended capability
- Observability/tracing tool (LangWatch or Langfuse) with traces visible
- Baseline test dataset (10–12 inputs) run and documented
- Architecture diagram and 1–2 page writeup
- Cost analysis and 3+ production metrics
- GitHub repository with workflow JSON, README, and screenshots
- Fine-tuning optional but recognized in scoring

---

## How to Choose

**By role:**
| If you... | Choose |
|---|---|
| Manage meetings and calendars daily | CalendarMate |
| Work in sales or deal with customer inquiries | SalesGenie |
| Write PRDs or translate meetings into requirements | PRD Genie |
| Manage project plans, timelines, and status reports | Mira |

**By setup complexity:**
| Setup Level | Projects |
|---|---|
| Fastest (file upload only, no OAuth) | SalesGenie, PRD Genie, Mira |
| Moderate (optional API integration) | Mira (Trello optional) |
| Most setup (Google OAuth2 required) | CalendarMate |
