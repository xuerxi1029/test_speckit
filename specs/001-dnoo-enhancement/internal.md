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

### Overall Goals

- Close priority functionality gaps versus the legacy GIS.
- Implement newly triggered business process and regulatory requirements.
- Reduce or eliminate manual workarounds and temporary fixes that create operational inefficiency.
- Protect data integrity and system performance by removing workaround-driven processes.
- Ensure GIS remains robust and future-proof while continuing to support ADMS integration.
- Enable strategic network developments (including introduction of the 22kV network).

### Out of Scope (Constraints)

- Fixing legacy data issues not addressed in the original project.
- Enhancements directly triggered by the Enlight (ERP) project.
- Tasks considered as product enhancement or unfinished bugs from the original GIS project.
- Broader system integration beyond GIS and ADMS.

### Deliverables

The enhancement program delivers improvements across two primary workstreams:

#### A. ADMS Enhancements

1. OMS Workflow Integration

Full integration of ATA triggering logic post-Enlight to streamline outage management.

OMS 工作流程集成
在 Enlight 系统之后，全面整合 ATA 的触发逻辑，让停电管理流程更加顺畅、高效。
（OMS – Outage Management System：停电管理系统，用来处理和跟踪停电事件；
Enlight：前端/上游的业务或监控系统；
ATA (Automatic Trouble Analysis)：自动触发机制，用来在发生特定情况时自动启动停电处理流程，减少人工操作。）

2. Voltage Level Expansion

Support for 22kV networks (trial in Q1 2026, full rollout by 2029).

电压等级扩展
支持 22kV 电网运行（计划在 2026 年第一季度试点，目标在 2029 年全面推广），以覆盖更大范围的供电需求。
（22kV：一种常见的中压供电等级，通常用于区域供电或工业用电。）

3. Automation of Switching Plan State Transitions

API-driven updates with OPS to reduce manual conflict checks and improve operational efficiency.

切换计划状态自动化
通过系统接口自动与 OPS 同步切换计划状态，减少人工检查冲突的工作，提高运行效率。
（API – Application Programming Interface，系统接口：用于让不同系统自动交换数据；
OPS – Operations System，运行操作系统：用于管理和执行电网的实际操作；
Switching Plan：电网切换操作计划。）

4. Multi-Stage Outage Support

Enhanced handling of complex outage scenarios across ADMS and GIS.

多阶段停电支持
更好地支持和处理复杂的、多步骤的停电情况，并在不同系统之间保持信息一致。
（ADMS – Advanced Distribution Management System，高级配电管理系统：用于监控和控制配电网运行；
GIS – Geographic Information System，地理信息系统：通过地图方式展示电网、设备和位置关系。）

5. Compliance and Efficiency Improvements

Integration with ORMS for regulatory compliance and optimized workflows.

合规与效率提升
与 ORMS 系统集成，确保操作符合监管要求，同时优化内部工作流程。
（ORMS – Outage Restoration Management System，停电恢复管理系统：用于规范停电恢复流程并满足合规要求。）

6. Safety Document and UAT Enhancements

Updated templates and JIRA-based issue tracking for user acceptance testing.

安全文档与用户验收测试优化
更新安全相关文档模板，并使用 JIRA 系统跟踪用户验收测试中发现的问题，提升测试和整改效率。
（UAT – User Acceptance Testing，用户验收测试：由业务或最终用户确认系统是否符合使用需求；
JIRA：常用的问题和任务跟踪工具。）

7. Advanced Query Engine

Support for Switching Management fields and clash-check logic.

高级查询引擎
提供更强大的查询功能，用于查找切换管理相关信息，并自动检查是否存在操作冲突。
（Query Engine，查询引擎：用于快速搜索和分析系统数据；
Clash-check，冲突检查：用于防止操作安排相互冲突或引发风险。）

#### B. GIS Enhancements

The 2026 Enhancement Project for GIS will deliver a comprehensive set of enhancements across five key areas.

1. Excavation Permit Application Enhancements
- Integration of private lot data, Government Land Licenses (GLL), Government Land Allocations (GLA), Short Term Tenancies (STT), and project limits into GIS.
- Development of a workflow to export relevant landbase information with each permit application.
- Implementation of a mechanism for more frequent or real-time updates of landbase data from the Lands Department.

通俗版说明：（挖掘许可证申请优化）
让挖掘许可证的申请少靠人记、少查资料、资料更准确。

把不同类型的土地资料统一整合进 GIS

GIS（Geographic Information System）：一个用地图方式管理土地、设施和位置资料的系统
包括：

私人地段（private lot）
GLL（Government Land Licenses）：政府发出的临时土地使用许可
GLA（Government Land Allocations）：政府分配的土地使用安排
STT（Short Term Tenancies）：短期租用政府土地
项目施工范围（project limits）

建立一套流程：
👉 每次提交挖掘许可证时，系统会自动把相关土地资料一起导出，不用再人工拼资料。

从 Lands Department（地政总署）更频密、甚至接近实时地更新土地资料，
👉 减少“用旧资料申请”的风险。


2. Circuit Reporting Enhancements
- Implementation of logic to automatically adjust segment length proportionally when electric lines are split or vertices are edited.
- Default assignment of segment length equal to sharp length upon circuit creation, with user override capability.
- Development of circuit analysis report to facilitate a structured and risk‑based approach to 11 kV cable and joint replacement planning.

通俗版说明：（线路与回路报表优化）
让电缆线路的数据自动算对、少出错、方便做风险分析。


当一条电线被拆分，或地图上的转折点（vertices）被修改时，
👉 系统会自动按比例调整每一段的长度，不用人工重算。


新建 circuit（电力回路）时：

系统默认用 sharp length 作为 segment length
使用者仍然可以手动修改


sharp length：按电缆实际铺设路径计算的长度（不是直线距离）
segment length: 一段线路（segment）的长度 (一条电缆或线路，被切成一小段之后，这一小段本身有多长)


建立一份 circuit analysis report（回路分析报告），
👉 用来支持 11 kV 电缆和接头（joint）更换计划，
👉 做到有结构、有风险优先次序，而不是凭经验决定。

3. Common Cable Infrastructure (CCI) Inventory Automation
- Establishment of containment relationships between CCI assets (e.g., cable bridges, tunnels) and the circuits they contain.
- Automation of inventory updates and report generation based on GIS data changes.

（CCI 公共电缆设施资产自动化管理）
通俗版说明：
让系统知道：哪条电缆在哪个通道里，不用人工对表。


在系统中建立 CCI 资产 和 电力回路（circuits） 之间的“包含关系”：

例如：

cable bridge（电缆桥）
tunnel（隧道）
里面实际装了哪些电缆


当 GIS 里的资料有更新时：
👉 库存数据和相关报表会自动更新并重新生成，
👉 减少人工维护资产清单。

4. 22kV Network Configuration
- Configuration of GIS to support 22kV network visualization, including symbology and equipment catalogues.
- Update of network model parameters to accommodate 22kV assets and operations.

（22kV 电网配置支持）
通俗版说明：
让系统“看得懂、画得出、管得到”22kV 电网。


配置 GIS，让它可以正确显示 22kV 网络，包括：

线路图样（symbology）
设备目录（equipment catalogues）


更新 network model（电网模型）的参数，
👉 确保系统在分析和操作上，能正确支持 22kV 设备和运行方式。

5. Automation of High-Impact Manual Workarounds
- Development of functionality to automatically generate Name and Alias fields used by ADMS.
- Identification and implementation of other high-effort manual processes that can be automated within GIS.
- Implementing a centralized session monitoring mechanism for ArcGIS to allow users tracking the status of their sessions after submission and approval.

（高影响人工 workaround 的自动化）
通俗版说明：
把现在最花人力、最容易出错的“人工顶着做”流程自动化。


自动生成 Name 和 Alias fields，供 ADMS 使用

ADMS（Advanced Distribution Management System）：用于配电网络运行、监控和调度的系统
Alias field：给系统用的“别名字段”，让不同系统之间能对得上字段名称


找出其他目前很花人力、但可以自动化的 GIS 操作流程，并逐步实现自动化。

在 ArcGIS 中建立一个统一的 session 监控机制：

session：用户一次提交或操作的系统处理过程
👉 用户在提交和审批之后，可以清楚看到：


自己的处理进度
是否还在跑
有没有出问题
而不是“交了之后只能等”。

##### Detailed Objectives

The GIS enhancement scope is designed with a clear set of objectives aligned to both business needs and regulatory mandates:

a) **Address Newly Triggered Regulatory Requirements**

- Recent changes in regulatory expectations—particularly around excavation permit applications and Common Cable Infrastructure (CCI) monitoring—require enhancements to GIS capabilities.
- The project will ensure GIS can support real-time landbase updates, integrate private lot data, and automate inventory tracking of CCI assets to meet compliance standards.

b) **Improve Operational Efficiency and Data Integrity**

- Manual workarounds adopted during the original project continue to impact productivity and data quality.
- Example: the lack of automated generation of Name and Alias fields used by ADMS requires significant manual effort and increases the risk of human error.
- The enhancement project will automate these processes, reducing operational overhead and improving system reliability.

c) **Support Strategic Network Development Initiatives**

- The company is preparing to introduce a 22kV network.
- While the original GIS project considered this in its data model design, additional configuration is required to fully support the new network (e.g., symbology, new equipment catalogues, and configuration parameter updates).

d) **Replace High-Effort Workarounds with Sustainable Solutions**

- Some requirements were deferred during the original project because they could not be realized using out-of-the-box GIS solutions.
- These were categorized as vendor “enhancements” and require custom development.
- The enhancement project will selectively implement those with the highest operational impact, replacing manual processes with automated, sustainable solutions.

e) **Ensure Continued Alignment with Business and Regulatory Evolution**

- As business processes evolve and regulatory requirements change, GIS must remain adaptable and responsive.
- The enhancement project positions GIS as a dynamic platform capable of continual improvement, rather than a static system frozen at its initial implementation state.

##### High-Level Timeline

| Phase / Workstream | M-2 | M-1 | M | M2 | M3 | M4 | M5 | M6 | M7 | M8 | M9 | M10 | M11 | M12 | M+1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Phase 1: Planning & Design | ■ | ■ | ■ |  |  |  |  |  |  |  |  |  |  |  |  |
| Phase 2: Development & Configuration |  |  |  | ■ | ■ | ■ | ■ | ■ | ■ |  |  |  |  |  |  |
| Phase 3: Testing & Validation (SIT/UAT/Pen Test) |  |  |  |  |  |  | ■ | ■ | ■ | ■ | ■ | ■ |  |  |  |
| Enlight freeze period (TBC) |  |  |  |  | ■ | ■ | ■ | ■ | ■ |  |  |  |  |  |  |
| Phase 4: Pilot Deployment (22kV trial) |  |  |  |  |  |  |  |  |  |  |  |  | ■ | ■ | ■ |
| Full Deployment & Optimization |  |  |  |  |  |  |  |  |  |  |  |  | ■ | ■ | ■ |
| BAU / Scale-up |  |  |  |  |  |  |  |  |  |  |  |  |  |  | ■ |



### Assumptions 

#### As-Is Assumption

Current operations in the DNOO environment rely on the assumption that manual workarounds are sufficient to address system limitations and unresolved issues. These workarounds are embedded in day-to-day processes and are relied upon to maintain business continuity.

#### Key Risks and Illustrative Examples

- **Operational inefficiency**: Staff are required to process supply point and meter associations individually due to the absence of a bulk processing capability. This creates significant recurring manual effort and increases the risk of error.
- **Risk to business continuity and compliance**: Switching Order Management remains a manual process, exposing the organization to potential supply interruptions and operational incidents because automation is not available to reliably support these critical functions.
- **Data integrity and decision-making**: Manual updates to cable segments and duct bank data patching are necessary to maintain data quality, but these interventions can lead to inconsistencies and incomplete records, impacting asset management and regulatory reporting.
- **Employee experience and organizational morale**: Users must perform repetitive, complex tasks such as updating asset attributes and migrating hyperlinks for supply points. This increases frustration and support demand and can negatively affect morale.
- **Delayed digital transformation**: Limited automation means integration and improved service delivery are not fully realized. Examples include the absence of a readable LV schematic and continued manual data patching for regulatory reports.

#### As-Is Conclusion

Continuing to rely on manual workarounds assumes that temporary solutions are sustainable for ongoing operations. In practice, this perpetuates inefficiency, increases risk exposure, and constrains the organization’s ability to achieve strategic objectives. Transitioning to robust, automated solutions through the DNOO enhancement is necessary to address these risks and support future growth.

### Project Governance & Organization

This section summarizes project governance, reporting lines, and role responsibilities based on the Roles & Responsibilities (R&R) table.

#### Organization Chart

```mermaid
flowchart TB

  %% =========================
  %% Governance (from screenshot)
  %% =========================
  PEC_ROLE["Project Executive Committee (PEC)<br/>Scope: GIS & ADMS<br/>Tony Kwok<br/>Manisha (Chair)<br/>Vivian Leung (GIS)<br/>CM Lok (ADMS)"]
  PMO_ROLE["PMO (PAT)<br/>Scope: GIS & ADMS<br/>Mike Ng<br/>Kelvin Chan<br/>CK Chan (GIS)<br/>TBC (ADMS)"]
  PM_ROLE["Project Manager<br/>Scope: GIS & ADMS<br/>Adrian Poon (Digital Project)<br/>Wong Lap Shun (GIS)<br/>Ho Kai On (ADMS)"]

  PEC_ROLE -- Governance - oversight --> PMO_ROLE
  PMO_ROLE -- Governance - direction --> PM_ROLE

  %% =========================
  %% Workstreams (from screenshot)
  %% =========================
  subgraph WORKSTREAMS[" "]
    direction LR
    ADMS_ROLE["ADMS<br/>Scope: ADMS<br/>Business PM: Ho Kai On<br/>Technical Lead: Human Tang (TBC)<br/>Engineer Lead: Phillip Tam; Frank Tong<br/>SME Function/BI: Phillip Tam; Frank Tong<br/>Process Change: Thomas Tam<br/>BA: TBC"]
    GIS_ROLE["GIS<br/>Scope: GIS<br/>Business PM: Wong Lap Shun<br/>Technical Lead: Ceci Chung; Jason Wu (TBC)<br/>Engineer Lead: Ricky Lee Lap Hung<br/>SME Function/BI: Ricky Lee Lap Hung; Harvey Hung<br/>Process Change: Thomas Tam<br/>BA: Karie Chan (SBA)"]
  end

  PM_ROLE -- Delivery - workstream oversight --> ADMS_ROLE
  PM_ROLE -- Delivery - workstream oversight --> GIS_ROLE

  %% =========================
  %% Shared support functions (from screenshot)
  %% =========================
  SUPPORT_HUB["Shared support functions<br/>Scope: GIS & ADMS"]

  subgraph SUPPORT[" "]
    direction LR
    INFRA_ROLE["DNOO Infra<br/>Scope: GIS & ADMS<br/>Patrick Cheung (consultation)"]
    EA_ROLE["Enterprise Architect<br/>Scope: GIS & ADMS<br/>Jimmy Chan (consultation)"]
    SEC_ROLE["Cyber Security (Group Security)<br/>Scope: GIS & ADMS<br/>Dennis Ng (GIS)<br/>Dan Tung (ADMS)<br/>Franky Shiu (GIS & ADMS)"]
    DATA_ROLE["Data Services<br/>Scope: GIS & ADMS<br/>Colin Cheng (TBC)"]
    CUST_ROLE["System Custodian<br/>Scope: GIS & ADMS<br/>Kelvin Chan"]
    OWNER_ROLE["System Owner<br/>Scope: GIS & ADMS<br/>Vivian Leung (GIS)<br/>CM Lok (ADMS)"]
  end

  PM_ROLE -- Collaboration - consultation and support --> SUPPORT_HUB
  SUPPORT_HUB --> INFRA_ROLE
  SUPPORT_HUB --> EA_ROLE
  SUPPORT_HUB --> SEC_ROLE
  SUPPORT_HUB --> DATA_ROLE
  SUPPORT_HUB --> CUST_ROLE
  SUPPORT_HUB --> OWNER_ROLE

  %% =========================
  %% Vendor (from screenshot)
  %% =========================
  V_ROLE["Vendor (SE)<br/>Scope: GIS & ADMS<br/>Jon Hew (PM)<br/>Kenny To (GIS Support)<br/>Alex Tong (Contract/Finance)<br/>SE team in Novi Sad, Serbia"]

  PM_ROLE -. Collaboration - delivery coordination .-> V_ROLE
  EA_ROLE -. Collaboration - implementation and testing .-> V_ROLE

  %% =========================
  %% Responsibilities (from R&R CSV)
  %% =========================
  PEC_RESP["Responsibilities<br/>Provide oversight, guidance, and direction to the DNOO project implementation<br/>Endorse significant changes on the project objectives and milestone<br/>Provide advice on high risk items and mitigation measures<br/>Resolve issue as escalated by Project Assurance Team / Project Execution Committee<br/>Approval of the customization items"]
  PMO_RESP["Responsibilities<br/>Provide vision and guidance to the Enhancement project implementation<br/>Provide project governance to the overall project implementation<br/>Decide on matters of scope, budget and timeframe<br/>Ensure all milestones being met on schedule, budget and quality<br/>Identify, manage and update the overall risk registers<br/>Provide advice on high risk items and mitigation measures<br/>Resolve issue as escalated by Project Assurance Team<br/>Signoff quality plan, risk assessment, functional and technical specification<br/>Assure all the project execution related compliance documents being endorsed<br/>Approve Change Request<br/>Members will attend meetings on a need basis"]
  PM_RESP["Responsibilities<br/>Lead and ensure the overall project met on scope, schedule, budget and quality<br/>Work and co-ordinate with the implementation team for implementation and testing<br/>Identify and manage risks<br/>Update progress and escalate issue of high importance to PAT/PEC<br/>Review and prepare all the project execution related compliance documents being endorsed"]

  ADMS_RESP["Responsibilities<br/>Lead and ensure the respective project deliverables and tasks met on schedule, budget and quality"]
  GIS_RESP["Responsibilities<br/>Update progress and escalate issue of high importance to PAT"]
  INFRA_RESP["Responsibilities<br/>Provide overall technical direction and key guidance to business and vendors"]
  EA_RESP["Responsibilities<br/>Work and co-ordinate with the external vendor for implementation and testing"]
  SEC_RESP2["Responsibilities<br/>Facilitate requirements workshop and deliver the architecture design"]
  DATA_RESP["Responsibilities<br/>Provide user requirement, review and signoff functional specification"]
  CUST_RESP["Responsibilities<br/>Implementation of system/ enhancement work"]
  OWNER_RESP["Responsibilities<br/>Review, conduct & sign off test such as DAT"]

  PEC_ROLE --> PEC_RESP
  PMO_ROLE --> PMO_RESP
  PM_ROLE --> PM_RESP

  ADMS_ROLE --> ADMS_RESP
  GIS_ROLE --> GIS_RESP
  INFRA_ROLE --> INFRA_RESP
  EA_ROLE --> EA_RESP
  SEC_ROLE --> SEC_RESP2
  DATA_ROLE --> DATA_RESP
  CUST_ROLE --> CUST_RESP
  OWNER_ROLE --> OWNER_RESP

  %% =========================
  %% Styling (roles vs responsibilities)
  %% =========================
  classDef resp fill:#F2F4F7,stroke:#D0D5DD,color:#101828;
  classDef roleL1 fill:#1D4ED8,stroke:#1D4ED8,color:#FFFFFF;
  classDef roleL2 fill:#0F766E,stroke:#0F766E,color:#FFFFFF;
  classDef roleL3 fill:#B45309,stroke:#B45309,color:#FFFFFF;
  classDef roleL4 fill:#334155,stroke:#334155,color:#FFFFFF;
  classDef vendor fill:#16A34A,stroke:#16A34A,color:#FFFFFF;

  class PEC_ROLE roleL1;
  class PMO_ROLE roleL2;
  class PM_ROLE roleL3;
  class ADMS_ROLE,GIS_ROLE,SUPPORT_HUB,INFRA_ROLE,EA_ROLE,SEC_ROLE,DATA_ROLE,CUST_ROLE,OWNER_ROLE roleL4;
  class V_ROLE vendor;

  class PEC_RESP,PMO_RESP,PM_RESP,ADMS_RESP,GIS_RESP,INFRA_RESP,EA_RESP,SEC_RESP2,DATA_RESP,CUST_RESP,OWNER_RESP resp;

  %% Visual polish
  style WORKSTREAMS fill:transparent,stroke:transparent
  style SUPPORT fill:transparent,stroke:transparent
```

#### Responsibilities by Role

##### PMO (PAT)

**Scope**: GIS & ADMS

**Name list**: Mike Ng; Kelvin Chan; CK Chan (GIS); TBC (ADMS)

- Provide vision and guidance to the enhancement project implementation.
- Provide project governance to the overall project implementation.
- Decide on matters of scope, budget, and timeframe.
- Ensure milestones are met on schedule, budget, and quality.
- Identify, manage, and update the overall risk registers.
- Provide advice on high-risk items and mitigation measures.
- Align and resolve issues as escalated by each project champion.
- Resolve issue as escalated by Project Assurance Team.
- Signoff quality plan, risk assessment, functional and technical specification.
- Assure all the project execution related compliance documents being endorsed.
- Approve change requests.
- Members attend meetings on a need basis (e.g., critical decisions, procurement stage, design & implementation stage).

##### Project Executive Committee (PEC)

**Scope**: GIS & ADMS

**Name list**: Tony Kwok; Manisha (Chair); Vivian Leung (GIS); CM Lok (ADMS)

- Provide oversight, guidance, and direction to the DNOO project implementation.
- Endorse significant changes to project objectives and milestones.
- Provide advice on high-risk items and mitigation measures.
- Resolve issue as escalated by Project Assurance Team / Project Execution Committee.
- Approve customization items.

##### Project Manager

**Scope**: GIS & ADMS

**Name list**: Adrian Poon (Digital Project); Wong Lap Shun (GIS); Ho Kai On (ADMS)

- Lead and ensure the overall project met on scope, schedule, budget and quality.
- Work and co-ordinate with the implementation team for implementation and testing.
- Identify and manage risks.
- Update progress and escalate issue of high importance to PAT/PEC.
- Review and prepare all the project execution related compliance documents being endorsed.

##### Implementation Team (Overall)

**Scope**: GIS & ADMS

**Name list**: ADMS Team; GIS Team; DNOO Infra; Enterprise Architect; Cyber Security (Group Security); Data Services; System Custodian; System Owner

- Identify & validate change requests.
- Collect and consolidate the feedback from the users.
- Review and initiate the process changes.
- Identify the risks.
- Provide on-going support.

##### ADMS Team

**Scope**: ADMS

**Name list**: Business PM: Ho Kai On; Technical Lead: Human Tang (TBC); Engineer Lead: Phillip Tam; Frank Tong; SME (Function and Business Improvement): Phillip Tam; Frank Tong; Process Change (Change Management): Thomas Tam; BA: TBC

- Lead and ensure the respective project deliverables and tasks met on schedule, budget and quality.

##### GIS Team

**Scope**: GIS

**Name list**: Business PM: Wong Lap Shun; Technical Lead: Ceci Chung; Jason Wu (TBC); Engineer Lead: Ricky Lee Lap Hung; SME (Function and Business Improvement): Ricky Lee Lap Hung; Harvey Hung; Process Change (Change Management): Thomas Tam; BA: Karie Chan (SBA)

- Update progress and escalate issue of high importance to PAT.

##### DNOO Infra

**Scope**: GIS & ADMS

**Name list**: Patrick Cheung (consultation)

- Provide overall technical direction and key guidance to business and vendors.

##### Enterprise Architect

**Scope**: GIS & ADMS

**Name list**: Jimmy Chan (consultation)

- Work and co-ordinate with the external vendor for implementation and testing.

##### Group Security

**Scope**: GIS & ADMS

**Name list**: Dennis Ng (GIS); Dan Tung (ADMS); Franky Shiu (GIS and ADMS)

- Facilitate requirements workshop and deliver the architecture design.

##### Data Services

**Scope**: GIS & ADMS

**Name list**: Colin Cheng (TBC)

- Provide user requirement, review and signoff functional specification.

##### System Custodian

**Scope**: GIS & ADMS

**Name list**: Kelvin Chan

- Implementation of system/ enhancement work.

##### System Owner

**Scope**: GIS & ADMS

**Name list**: Vivian Leung (GIS); CM Lok (ADMS)

- Review, conduct & sign off test such as DAT.

##### Vendor (SE)

**Scope**: GIS & ADMS

**Name list**: Jon Hew (PM); Kenny To (GIS Support); Alex Tong (Contract and Finance); SE team: Novi Sad, Serbia

**Responsibilities**: _Not specified in the pasted org chart screenshot or R&R CSV._

### Risks

The following risks and mitigations are captured for the enhancement program and should be reviewed and updated throughout delivery.

| Item No. | Risk Description | Risk Level | Mitigation |
| --- | --- | --- | --- |
| 1 | Inter-project dependency: Enlight team is planning to use the same testing environment as the Enhancement Project. Our project schedule may need to include buffer on the testing & deployment timeline of Enlight. | High | TBC to discuss with the Enlight team. |
| 2 | Vendor dependencies and resource constraints could push timelines. | High | Define clear milestones and vendor SLAs. Maintain buffer periods in the implementation schedule. Use agile delivery for incremental releases. |
| 3 | Multiple system interfaces (OMS, ERP, etc.) may lead to integration failures or data inconsistencies. | Medium | Conduct early integration testing during development phase. Use standardized APIs and robust error-handling mechanisms. Engage vendors (e.g., SE) for joint validation sessions. |
| 4 | Real-time updates between ADMS and GIS may fail, causing incorrect circuit or asset data. | Medium | Implement automated reconciliation checks. Schedule periodic audits of GIS and ADMS data. Maintain rollback procedures for critical updates. |
| 5 | Enhancements may not fully meet safety or compliance standards. | Low | Involve compliance teams during design phase. Validate workflows against latest regulatory requirements. Update safety document templates and perform compliance UAT. |
| 6 | Operational teams may resist new workflows or lack training. | Low | Develop comprehensive training programs and user guides. Conduct pilot deployments with feedback loops. Provide on-site support during initial rollout. |
| 7 | Performance & scalability risks. | Medium | Conduct load testing before full deployment. Optimize database queries and caching mechanisms. Plan infrastructure upgrades for future scalability. |

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
