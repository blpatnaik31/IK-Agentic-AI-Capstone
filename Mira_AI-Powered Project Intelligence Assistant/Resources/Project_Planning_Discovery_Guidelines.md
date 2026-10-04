# Project Planning & Discovery Guidelines
## Bridging PMI Standards and Agile/Scrum Execution

This document outlines the essential components required to transition from high-level project definition under PMI standards to actionable discovery and planning in Jira using Agile methodologies. 

---

## Part 1: Project Description Requirements (PMP-PMI Standards)

To successfully transition from a project description to a comprehensive Project Management Plan, the initial description (formally the Project Charter and Scope Statement) must contain the following foundational elements.

### 1. Strategic Alignment & Scope
* **Project Purpose and Justification:** The business case or reason the project was initiated. This guides all future trade-off decisions.
* **Measurable Project Objectives:** High-level goals tied to success criteria (e.g., "Reduce system latency by 20% within Q3").
* **High-Level Requirements:** The overarching capabilities or conditions the final product, service, or result must meet.
* **Boundaries and Key Deliverables:** A clear statement of what is explicitly **in scope** and **out of scope**, alongside the major tangible outputs of the project.

### 2. Constraints & Assumptions
* **Summary Milestone Schedule:** Hard deadlines or significant points in time that the detailed schedule will need to anchor around.
* **Preapproved Financial Resources:** The high-level budget constraint or funding limits.
* **Overall Project Risk:** The high-level, macro risks (both threats and opportunities) identified before detailed risk planning begins.
* **High-Level Assumptions:** Things believed to be true for planning purposes (e.g., "The target server environment will be available by Day 1"). 

### 3. Governance & Stakeholders
* **Key Stakeholder List:** An initial roster of the primary individuals or groups affected by or influencing the project.
* **Project Approval Requirements:** What constitutes project success, who decides if it is successful, and who signs off on it.
* **Assigned Project Manager & Authority Level:** Clear documentation of the PM's authority over resources, budget, and personnel.
* **Sponsor Authority:** The name and authority of the person championing and funding the project.

---

## Part 2: JIRA Ticket Requirements for Planning & Discovery (Agile/Scrum)

When organizing sprints and managing backlogs, early planning and discovery phases are captured in Jira using Epics for high-level structure and Spikes for time-boxed research. To meet industry standards and ensure a clear Definition of Ready (DoR), Jira tickets need the following specific details.

### 1. Epics (High-Level Planning)
Epics serve as containers for large, overarching project goals, bridging the gap between the PMI business case and the technical backlog.

* **Executive Summary:** A concise description of the overarching goal and the specific business problem being solved.
* **Business Value:** The measurable ROI or strategic alignment (e.g., cost reduction, automation efficiency).
* **High-Level Acceptance Criteria:** The macro-level conditions that must be true for the entire Epic to be considered complete.
* **Target Release / Fix Version:** The projected quarter or product increment when this value will be delivered.
* **Dependencies & Risks:** Known upstream or downstream blockers and identified project risks (e.g., RAID log items).

### 2. Spikes (Discovery & Research)
Spikes are specialized tickets used exclusively for discovery work, technical investigations, or prototyping. Because discovery can easily expand indefinitely, these tickets require strict boundaries.

* **The Unknown or Hypothesis:** Clearly define exactly what is currently unknown or needs to be proven (e.g., "Determine if the new REST API supports extracting historical trade log data into JSON format").
* **Strict Timebox:** The absolute maximum time the team will spend investigating this issue (e.g., "8 hours" or "2 days"). 
* **Expected Output:** What the team must produce at the end of the timebox to consider the Spike successful (e.g., a technical architecture diagram, a Python proof-of-concept script, or a "go/no-go" decision).

### 3. User Stories (Actionable Planning)
As discovery concludes, Epics are broken down into User Stories. For a story to be pulled into an active sprint, it must be fully defined.

* **Story Narrative:** "As a [User Role], I want to [Action], so that [Benefit/Value]."
* **Detailed Acceptance Criteria:** Specific, testable requirements, often written in BDD format (Given / When / Then).
* **Story Points or Estimation:** The agreed-upon relative effort required to complete the ticket.
* **Visual Attachments:** Wireframes, UI/UX mockups, or system flow diagrams.
* **Designated Components/Labels:** Tags mapping the story to specific system architecture.

### Jira Ticket Requirements Summary

| Ticket Type | Primary Phase | Key Constraint | Mandatory Output |
|---|---|---|---|
| **Epic** | Early Planning | Strategic alignment | Approved business value |
| **Spike** | Discovery | Strict timebox | Research document or decision |
| **Story** | Sprint Planning | Definition of Ready | Testable Acceptance Criteria |
