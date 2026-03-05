# PM Meeting Question List (BA) — DNOO Enhancement

**Purpose**: A curated set of questions you can raise with the PM to demonstrate (1) command of the current DNOO Enhancement scope (ADMS + GIS), and (2) BA-level focus on outcomes, decision points, dependencies, and delivery risk.

**Ground rule**: These questions intentionally target areas that are *not* explicitly answered in `internal.md` (which is currently high-level and template-based).

---

## BA Accountable “Top 10” (PM can answer; not spelled out in `internal.md`)

These are phrased so you can convert the answers directly into **business requirements**, **functional specs**, and **test/rollout readiness**.

1) **What are the top outcomes we’re optimizing for in 2026 (3–5 KPIs), and what baseline do we use today?**
   - **Why ask**: Turns “improve efficiency / reduce workarounds” into measurable targets you can trace requirements and UAT to.

2) **What is the MVP definition for 2026 (what must be live and usable), and what is explicitly deferred to BAU/next release?**
   - **Why ask**: Lets you write a requirements pack that is shippable and protects scope.

3) **What is the prioritization rule when we have conflicts (compliance/safety vs operational risk vs user efficiency vs strategic 22kV readiness)?**
   - **Why ask**: Gives you a consistent way to rank user stories and handle future change requests.

4) **Which user groups/personas are in scope, and what are the “critical user journeys” we must prove end-to-end in UAT (top 5–8 journeys)?**
   - **Why ask**: BA-owned UAT and acceptance criteria should be journey-based, not feature-by-feature.

5) **What are the acceptance and sign-off gates, and who signs what (business sign-off vs technical sign-off vs compliance/security sign-off)?**
   - **Why ask**: Prevents rework and late-cycle disputes; clarifies accountability for functional specs and test evidence.

6) **What is the precise boundary with Enlight: what inputs/outputs do we depend on, and what is *not* our responsibility even if it blocks us?**
   - **Why ask**: You can document integration assumptions, clarify ownership, and reduce “out-of-scope but required” ambiguity.

7) **What are the “non-negotiable” business rules that must be clarified early (e.g., naming/alias rules, conflict rules, exception handling/overrides), and who is the final decider when stakeholders disagree?**
   - **Why ask**: These rules drive functional specs; unresolved rules are a common cause of SIT/UAT churn.

8) **What is the data ownership model for key records across GIS/ADMS (who is the source of truth, who can amend, and how do we resolve discrepancies)?**
   - **Why ask**: Enables you to specify governance requirements and define test cases around reconciliation/exception handling.

9) **What is the rollout approach (pilot scope, training approach, hypercare duration), and what operational readiness criteria must be met before go-live?**
   - **Why ask**: BA is accountable for bridging to operations; this makes rollout testable and explicit.

10) **What are the top 5 open decisions you want locked in the next 2–4 weeks, and what inputs do you need from BA to close them?**
   - **Why ask**: Shows proactive ownership and converts the meeting into an action plan for requirements workshops and spec drafting.

---

## Outcomes & Scope Control

1) **What is the outcome hierarchy (Program OKRs → workstream outcomes → feature success criteria)?**
   - **Why ask**: Helps align many deliverables into a coherent narrative.

2) **What is “in scope” definitionally for “close priority functionality gaps vs legacy GIS” — which legacy features are the benchmark list?**
   - **Why ask**: “Gaps vs legacy” can expand endlessly unless enumerated.

3) **What is the change control process in practice (who can raise CRs, how effort/value is assessed, and what’s the approval SLA)?**
   - **Why ask**: Prevents late CR backlog from derailing SIT/UAT windows.

4) **What is the agreed prioritization method (MoSCoW, WSJF, risk-based, compliance-first, etc.), and what scoring dimensions are used?**
   - **Why ask**: A defensible method helps you as BA when negotiating priorities.

5) **If we must cut 20% scope, which items are first to drop and why (pre-agreed “sacrificial list”)?**
   - **Why ask**: Forces realistic planning and avoids last-minute chaos.

---

## Regulatory, Audit, and Safety Gates

1) **Which regulations/standards are driving the excavation permit and CCI requirements (specific regulator, clauses, audit expectations)?**
   - **Why ask**: Compliance requirements need traceability, not just intent.

2) **What are the audit artifacts we must produce (e.g., evidence logs, approvals, traceability matrices), and which system is the system-of-record?**
   - **Why ask**: Impacts workflow design and reporting.

3) **For safety documents + UAT enhancements, what is the “definition of done” for safety compliance (templates updated vs workflow enforced vs audit-proof evidence)?**
   - **Why ask**: Avoids a deliverable that looks complete but fails audit.

4) **Is a pen test a hard gate for release, and what is the target remediation window for findings?**
   - **Why ask**: Can materially change release dates.

---

## ADMS Workstream: Deep-Dive Questions

1) **OMS workflow / ATA triggering**: What are the trigger conditions, event sources, and required latency (seconds/minutes)?
   - **Why ask**: “Full integration” is vague; ops impact depends on timing and false positive/negative rates.

2) **Multi-stage outage support**: What is the canonical outage “state model” and who owns it (OMS vs ADMS vs GIS)?
   - **Why ask**: Multi-system state machines are common failure points.

3) **Switching plan state transitions with OPS**: What are the states, transitions, and exception handling paths (partial failures, conflicts, overrides)?
   - **Why ask**: Automation without exceptions creates operational risk.

4) **ORMS integration**: What are the compliance events that must be captured and what is the authoritative timestamp/source for each?
   - **Why ask**: Compliance often hinges on who said what, when.

5) **Advanced query engine**: Who are the primary personas, what are the top 10 query scenarios, and what are performance expectations?
   - **Why ask**: Query tooling can balloon unless constrained to real use-cases.

6) **22kV expansion (ADMS)**: What operational capabilities are needed for the *pilot* vs full rollout (e.g., protection schemes, device types, reporting)?
   - **Why ask**: Prevents over-building for 2029 requirements in a 2026 project.

---

## GIS Workstream: Deep-Dive Questions

1) **Landbase updates from Lands Department**: What refresh cadence is actually required (near real-time vs daily/weekly), and what happens when the feed is unavailable?
   - **Why ask**: Determines architecture, data contracts, and operational SLAs.

2) **Data licensing / usage constraints**: Are there restrictions on storing, exporting, or sharing private lot / GLL / GLA / STT datasets?
   - **Why ask**: Affects export workflow design and compliance.

3) **Excavation permit export workflow**: What is the official “permit application package” definition (format, fields, attachments, versioning), and who consumes it?
   - **Why ask**: Prevents building the wrong export artifact.

4) **Circuit reporting (segment vs sharp length)**: What is the business rule when physical reality, as-built drawings, and GIS geometry disagree?
   - **Why ask**: Edge cases define trust in reporting.

5) **11kV cable/joint replacement planning**: What risk model is used (age, failure history, environment, load), and what decisions will the report drive?
   - **Why ask**: Clarifies whether this is “reporting” or “decision support.”

6) **CCI containment relationships**: What is the required level of granularity (circuit-level vs segment-level), and how will changes be governed?
   - **Why ask**: Wrong granularity creates either unusable detail or insufficient control.

7) **Inventory automation**: What is the reconciliation/exception process when GIS edits produce inventory conflicts?
   - **Why ask**: Automated updates must have a dispute-resolution workflow.

8) **22kV network visualization/symbology**: What are the standards (naming, color/symbol rules, map layers), and who owns the catalogue governance?
   - **Why ask**: Visualization needs a single owner to avoid inconsistent maps.

9) **Name/Alias generation for ADMS**: What are the uniqueness rules, collision handling, and backward compatibility expectations for existing assets?
   - **Why ask**: Naming is a long-lived integration contract.

10) **ArcGIS session monitoring**: What is a “session” in this context (batch job, edit session, workflow transaction), and what status states must be visible to end users?
   - **Why ask**: Prevents building a dashboard that doesn’t match user mental model.

---

## Data, Integration Boundaries, and Ownership

1) **What are the authoritative systems for each key entity (asset, circuit, switching plan, outage event, land parcel), and what is the sync direction?**
   - **Why ask**: Reduces “double-edit” and blame during incidents.

2) **What are the integration contracts (APIs/files/messages) we must not break, and how do we version them?**
   - **Why ask**: Avoids breaking changes during phased rollout.

3) **What is the expected error budget for integrations (acceptable failure rate) and the operational runbook when it’s exceeded?**
   - **Why ask**: Turns “integration risk” into something operable.

4) **Do we need master data cleanup/migration to realize these enhancements, and if yes, who funds/owns it given “legacy data issues” are out of scope?**
   - **Why ask**: Data quality is often the hidden critical path.

---

## Testing Strategy, Cutover, and BAU Readiness

1) **What is the integrated end-to-end test scope that proves value (not just component SIT), and who signs off each journey?**
   - **Why ask**: Aligns UAT to real operational scenarios.

2) **How will we handle parallel run / dual-entry periods (if any), and what is the maximum duration we can tolerate?**
   - **Why ask**: Dual entry is expensive and error-prone.

3) **What is the release strategy (single big-bang vs incremental releases), and what is the gating checklist per release?**
   - **Why ask**: De-risks delivery by shaping deployments.

4) **What BAU support model is planned post go-live (hypercare length, vendor on-call, escalation path, KPIs)?**
   - **Why ask**: Ensures operations doesn’t inherit an unsupported solution.

---

## People, Change Management, and Adoption

1) **Who are the primary user groups and what is the change impact by persona (what stops/starts/continues)?**
   - **Why ask**: Helps plan training and comms, and de-risks resistance.

2) **What is the training strategy (train-the-trainer vs direct), and how will competency be validated?**
   - **Why ask**: Training quality strongly predicts adoption.

3) **How will we capture user feedback during pilot and convert it into prioritized backlog items (with SLA)?**
   - **Why ask**: Prevents pilot feedback from becoming “noise” or scope creep.

---

## Commercial / Vendor Management

1) **What is the delivery model with the vendor (fixed scope vs T&M), and what are the acceptance/payment milestones?**
   - **Why ask**: Commercial structure shapes behavior and delivery risk.

2) **What are the expected vendor SLAs during development and hypercare (response times, defect turnaround, environment support)?**
   - **Why ask**: Makes risk mitigation for “resource constraints” concrete.

3) **What is our approach to knowledge transfer to internal teams (documentation, shadowing, handover criteria)?**
   - **Why ask**: Prevents long-term vendor lock-in.

---

## Suggested meeting close (to look proactive)

- “If we align on **success metrics**, **MVP definition**, and **Enlight boundary** today, I can turn that into a prioritized requirements pack + traceability for SIT/UAT. What are the 2–3 decisions you want locked first?”
