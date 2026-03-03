# Feature Specification: DNOO Enhancement

**Feature Branch**: `001-dnoo-enhancement`  
**Created**: 2026-03-03  
**Status**: Draft  
**Input**: _Paste raw notes / requirements here; I’ll refine wording and structure._

## Overview

### Problem Statement

#### Background

The 2026 Enhancement Project for both the Advanced Distribution Management System (ADMS) and the Geographical Information System (GIS) is proposed as a strategic follow-up to the successful rollout of the new GIS (July 2025) and ADMS (October 2025).

While the original GIS program achieved its core objectives—consolidating multiple legacy systems, streamlining distribution network design-to-commissioning processes, and establishing a single source of truth for network models to support ADMS integration—it was delivered under tight timelines and resource constraints. To meet deadlines, temporary fixes and workaround solutions were adopted. Post-rollout, these have contributed to operational inefficiencies and user dissatisfaction.

#### Rationale / Why Now

Continuous feedback from business users has highlighted:

- Functionality gaps compared to the legacy GIS
- New requirements triggered by evolving business processes and regulatory changes

These are newly triggered needs (not residual tasks from the original GIS rollout). To maintain momentum and keep GIS robust and future-proof, a dedicated enhancement project is required.

#### Strategic Intent

This enhancement initiative is positioned to:

- Address new business and regulatory requirements
- Improve operational efficiency
- Support strategic developments such as the introduction of the 22kV network
- Eliminate high-effort manual workarounds that increase risk to data integrity and system performance

### Goals

<!-- Draft goals based on the background above; refine as scope is confirmed -->

- Close priority functionality gaps versus the legacy GIS.
- Implement newly triggered business process and regulatory requirements.
- Reduce or eliminate manual workarounds and temporary fixes that create operational inefficiency.
- Protect data integrity and system performance by removing workaround-driven processes.
- Ensure GIS remains robust and future-proof while continuing to support ADMS integration.
- Enable strategic network developments (including introduction of the 22kV network).

### Deliverables

The enhancement program delivers improvements across two primary workstreams:

#### A. ADMS Enhancements

1. OMS Workflow Integration
Full integration of ATA triggering logic post-Enlight to streamline outage management.

2. Voltage Level Expansion
Support for 22kV networks (trial in Q1 2026, full rollout by 2029).

3. Automation of Switching Plan State Transitions
API-driven updates with OPS to reduce manual conflict checks and improve operational efficiency.

4. Multi-Stage Outage Support
Enhanced handling of complex outage scenarios across ADMS and GIS.

5. Compliance and Efficiency Improvements
Integration with ORMS for regulatory compliance and optimized workflows.

6. Safety Document and UAT Enhancements
Updated templates and JIRA-based issue tracking for user acceptance testing.

7. Advanced Query Engine
Support for Switching Management fields and clash-check logic.

#### B. GIS Enhancements

The 2026 Enhancement Project for GIS will deliver a comprehensive set of enhancements across five key areas.

1. Excavation Permit Application Enhancements
- Integration of private lot data, Government Land Licenses (GLL), Government Land Allocations (GLA), Short Term Tenancies (STT), and project limits into GIS.
- Development of a workflow to export relevant landbase information with each permit application.
- Implementation of a mechanism for more frequent or real-time updates of landbase data from the Lands Department.

2. Circuit Reporting Enhancements
- Implementation of logic to automatically adjust segment length proportionally when electric lines are split or vertices are edited.
- Default assignment of segment length equal to sharp length upon circuit creation, with user override capability.
- Development of circuit analysis report to facilitate a structured and risk‑based approach to 11 kV cable and joint replacement planning.

3. Common Cable Infrastructure (CCI) Inventory Automation
- Establishment of containment relationships between CCI assets (e.g., cable bridges, tunnels) and the circuits they contain.
- Automation of inventory updates and report generation based on GIS data changes.

4. 22kV Network Configuration
- Configuration of GIS to support 22kV network visualization, including symbology and equipment catalogues.
- Update of network model parameters to accommodate 22kV assets and operations.

5. Automation of High-Impact Manual Workarounds
- Development of functionality to automatically generate Name and Alias fields used by ADMS.
- Identification and implementation of other high-effort manual processes that can be automated within GIS.
- Implementing a centralized session monitoring mechanism for ArcGIS to allow users tracking the status of their sessions after submission and approval.


- [TBD]

### Non-Goals

<!-- Explicitly list what is out of scope -->

### Assumptions & Constraints

<!-- Constraints: timeline, dependencies, policies, platforms, etc. -->

## User Scenarios & Testing *(mandatory)*

<!--
  IMPORTANT: User stories should be PRIORITIZED as user journeys ordered by importance.
  Each user story/journey must be INDEPENDENTLY TESTABLE — meaning if you implement just ONE of them,
  you should still have a viable MVP (Minimum Viable Product) that delivers value.

  Assign priorities (P1, P2, P3, etc.) to each story, where P1 is the most critical.
  Think of each story as a standalone slice of functionality that can be:
  - Developed independently
  - Tested independently
  - Deployed independently
  - Demonstrated to users independently
-->

### User Story 1 — [Brief Title] (Priority: P1)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently and the value it delivers]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]
2. **Given** [initial state], **When** [action], **Then** [expected outcome]

---

### User Story 2 — [Brief Title] (Priority: P2)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]

---

### User Story 3 — [Brief Title] (Priority: P3)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]

### Edge Cases

- What happens when [boundary condition]?
- How does the system handle [error scenario]?

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: System MUST [specific capability]
- **FR-002**: System MUST [specific capability]

*If something is unclear, mark it explicitly:*

- **FR-00X**: System MUST [NEEDS CLARIFICATION: what exactly?]

### Non-Functional Requirements

- **NFR-001**: Performance: [latency/throughput target, if applicable]
- **NFR-002**: Security/Privacy: [requirements]
- **NFR-003**: Reliability: [availability/error budgets, if applicable]
- **NFR-004**: Compliance/Audit: [requirements]

### Key Entities *(include if feature involves data)*

- **[Entity 1]**: [What it represents; key attributes (no implementation)]
- **[Entity 2]**: [Relationships / lifecycle]

## Design Notes (Optional)

### Proposed Approach

<!-- High-level approach; keep implementation details light unless needed -->

### Integrations / Dependencies

<!-- Systems touched, external dependencies, contracts -->

### Rollout & Backward Compatibility

<!-- Feature flags, staged rollout, migration, deprecation plan -->

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: [Measurable metric]
- **SC-002**: [Measurable metric]
- **SC-003**: [Measurable metric]

## Open Questions

- **Q-001**: [Question]
- **Q-002**: [Question]
