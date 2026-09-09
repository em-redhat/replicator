---
type: learning
category: reference
tag: process
created: 2026-08-20
source: complytime/roadmap README.md (private repo, fetched via gh CLI)
---

# ComplyTime Intake & Delivery Process — 7-Step Workflow

## Scope

Applies to greenfield or cross-cutting feature requests requiring product discovery, requirements breakdown, and new or major changes. Component-scoped requests (localized bug fixes, self-contained enhancements, minor refactors) use normal GitHub Issue and PR flow.

> When in doubt: if a change impacts external component interfaces, data schemas, or shared dependencies, default to raising an ADR (Step 2).

## Definitions

- **Workstream**: Long-lived subproject with a dedicated Tech Lead (e.g., ComplyTime, Agentic SSDLC). Ongoing, no fixed end date.
- **Initiative**: Time-bound roadmap item within a workstream. Has defined scope, dedicated Technical Owner, moves through the 7-step workflow.
- **The Bridge**: Step 4 — hand-off between Track 1 (design) and Track 2 (execution), where an approved ADR is broken into User Stories.

## The 7 Steps

| # | Step | Track | Owner | Output |
|---|------|-------|-------|--------|
| 1 | Feature Request & PRD | 1 | Product Owner | Merged PRD; Technical Owner named |
| 2 | Technical Design & Architecture | 1 | Technical Owner | ADR / design artifacts |
| 3 | AAC Review & Acceptance | 1 | AAC | Merged ADR (blockers resolved or overridden) |
| 4 | Story Breakdown (The Bridge) | Bridge | PgM + Technical Owner | High-level User Stories + preliminary estimates |
| 5 | Kickoff & Scope Alignment | 2 | PgM + Stakeholders | Locked scope baseline |
| 6 | Story Sizing | 2 | PgM, Tech Lead, Technical Owner | Sized stories + release timeline |
| 7 | Execution, Review & Retrospective | 2 | PgM (Engineering delivers) | Delivered milestone; UAT started |

## Execution Ceremonies (Step 7)

| Ceremony | Cadence | Purpose |
|----------|---------|---------|
| Backlog Grooming | Each sprint, pre-planning | Make near-term stories clear, prioritized, unblocked |
| Capacity & Allocation Sync | Pre-planning (15-20 min / async) | Set capacity and per-project allocation targets |
| Sprint Planning | Each sprint (~60 min) | Developers autonomously pull sized stories |
| Daily Execution Call | Daily (~30 min) | Tactical status and blocker removal |
| Sprint Retrospective | Bi-weekly (~30 min) | Review metrics, log technical debt |
| Milestone Showcase | Per milestone (live demo) | Verify against PRD, start UAT |

## Escalation & Interrupt Management

- **The Gatekeeper**: All urgent requests go to PgM for triage, never directly to engineers
- **Emergency Rubric**: An interrupt enters active release only if it's a production-stopping bug or immediate compliance/legal blocker
- **One In, One Out Rule**: If leadership approves an emergency escalation, equivalent scope is pulled out of the active release and pushed back to Track 1. Stakeholders must sign off on what is delayed.

## Execution Model

Execution is driven by OpenSpec: before any code, engineer runs `/openspec:proposal` to generate proposal, design rationale, and `tasks.md`. Once approved, Unbound Force's `/unleash` drives the autonomous pipeline. Specs stay persistent across sessions and agents; intent is reviewed before code.

## Definition of Done

- Code passes all local and CI automated test suites, security validations, and style lints
- If architectural changes were forced during delivery, a local ADR has been written
- Feature has been validated as functional in its target environment

## Roles

| Role | Responsibility |
|------|---------------|
| Product Owner | Owns PRD and the what/why of an initiative |
| Technical Owner (TO) | Leads technical design; floating per-initiative role |
| Tech Lead | Workstream's dedicated technical lead; sits on AAC |
| Program Manager (PgM) | Pipeline facilitator and gatekeeper |
| AAC | Architecture Advisory Council — socialization and agreement body for designs |
| Engineering Manager | Surfaces developer capacity and competing commitments |
| Steering Committee | Executive stakeholders — strategic priorities and resource allocations |
| Core Execution Team | Engineers delivering the active sprint's committed stories |
