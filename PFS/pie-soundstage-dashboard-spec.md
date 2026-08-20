# PIE Soundstage Dashboard Specification

## Problem statement
PIE needs a Soundstage-style dashboard that presents operational state, delivery readiness, and actionable follow-up in a single repeatable format.

## Goals
- Provide a single dashboard definition for PIE program health.
- Follow a Soundstage-style information hierarchy: overview, signals, detail, action.
- Keep the deliverable deployment-ready for a future implementation team.

## Non-goals
- Building a live UI in this repository.
- Defining backend services that do not already exist in the project.

## Dashboard structure

### 1. Executive header
- Dashboard name: **PIE Soundstage**
- Program owner
- Last refresh timestamp
- Current phase / rollout state
- Overall status indicator: Green / Yellow / Red

### 2. North-star KPI strip
- Delivery progress
- Open risks
- Active blockers
- SLA / milestone adherence

Each KPI card should contain:
- current value
- target value
- trend direction
- owner

### 3. Operational lanes
- **Delivery lane**: milestone status, completion %, next milestone
- **Quality lane**: escaped issues, validation status, known defects
- **Dependency lane**: upstream/downstream blockers, due dates, owners
- **Decision lane**: pending decisions, decision age, escalation path

### 4. Drill-down tables
- Risks register
- Dependency tracker
- Decision log
- Upcoming actions

## Data model

| Entity | Required fields |
| --- | --- |
| KPI card | id, label, value, target, trend, owner, status |
| Milestone | id, name, due_date, status, completion_percent, owner |
| Risk | id, summary, severity, owner, mitigation, due_date, status |
| Dependency | id, name, type, owner, due_date, blocker_status, next_step |
| Decision | id, topic, owner, age_days, status, next_review |

## Interaction model
- Start on the executive header and KPI strip.
- Move into operational lanes for context by function.
- Use drill-down tables to identify the exact follow-up item and owner.

## Deployment guidance
- Publish the dashboard only when every panel has a named data source and owner.
- Preserve a fixed panel order across releases to keep operator muscle memory intact.
- Default empty states to explicit messages such as `No active blockers` instead of blank panels.
- Review refresh cadence before release so stale data is visible and traceable.

## Acceptance checklist
- [ ] Executive header fields are defined
- [ ] KPI strip uses owner + target + trend on every card
- [ ] Operational lanes map to delivery, quality, dependency, and decision tracking
- [ ] Drill-down tables provide actionable ownership
- [ ] Data sources and refresh expectations are documented before deployment
