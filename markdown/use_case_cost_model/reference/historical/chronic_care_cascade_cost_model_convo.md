# Prompt

Run the STAGE 1 PROMPT with this Tech Brief.

# Response

## 1. Pilot summary

### Pilot concept

The PHIG B4 Chronic Care Cascade Pilot would demonstrate a **“collect once, use many” chronic disease data model**. Participating provider networks would transmit a standardized minimum chronic-care dataset through an intermediary—principally an HIE, HDU, or HCCN—which would ingest, normalize, validate, deduplicate, score, and provision the data for multiple authorized uses. Those uses may include CDC chronic disease surveillance, HRSA-aligned reporting, and NCQA- or CMS-aligned digital quality measurement. 

### Problem addressed

The pilot responds to four related problems:

1. STLT public health agencies often lack timely, standardized clinical data for chronic disease surveillance.
2. Providers and networks face duplicative reporting requirements that use overlapping data but different formats, validation rules, and transmission paths.
3. HIE/HDU data completeness and standardization vary, making cross-site comparison and operational use difficult.
4. Advanced analytics require reliable provenance, quality, governance, and auditability that are not consistently available today. 

### Objectives

The core objectives are to:

* Define a minimum chronic-care dataset aligned with USCDI, US Core, and relevant QI-Core concepts.
* Implement standards-based ingestion through an intermediary.
* Establish a reusable data-trust layer covering conformance, completeness, timeliness, provenance, and auditability.
* Produce one or more reusable data products for multiple authorized consumers.
* Execute at least one representative surveillance, reporting, or digital-measure workflow.
* Document repeatable governance, onboarding, implementation, and technical-assistance patterns.
* Optionally test closed-loop chronic intervention referrals where existing infrastructure and governance make that feasible. 

### Intended outcomes

The pilot is expected to produce evidence that:

* A minimum chronic dataset can be obtained through more than one intermediary-enabled pathway.
* The same validated dataset can support multiple downstream consumers.
* Data quality and completeness can be made transparent.
* Integration and reporting burden can be reduced relative to separate pipelines.
* STLT agencies can use the resulting products to identify control gaps, disparities, priority populations, and potential intervention targets.
* Reusable specifications and implementation artifacts can support subsequent national scaling.

### Primary workflows

**Core workflow**

1. Provider networks, health systems, FQHCs, or HCCNs make clinical data available through Bulk FHIR or stable FHIR APIs.
2. An intermediary ingests the data.
3. The intermediary normalizes terminology and values, defines cohorts, deduplicates records within its authorized scope, and performs identity resolution where permitted.
4. The intermediary applies conformance, completeness, timeliness, provenance, and audit controls.
5. Validation reports and remediation feedback are generated.
6. Curated data products or derived outputs are provisioned to authorized CDC, STLT, HRSA-aligned, and quality-measurement consumers.
7. One or more chronic indicators or digital measures are executed from the shared dataset.

**Optional referral workflow**

A referral is initiated for a clinical, social, or access barrier; referral status and outcome signals are returned through existing clinical-to-community infrastructure. Gravity-aligned representations may be used where feasible.

### Operating model

The anticipated operating model is a **federated, intermediary-enabled model** rather than a single centralized national platform. The intermediary performs acquisition, normalization, trust-layer operations, and controlled provisioning. STLT agencies may act as consumers, participants, implementers, or combinations of those roles. CDC and other national stakeholders define requirements and evaluate reuse, while source organizations remain responsible for making data available and addressing quality defects.

The data product is intended to remain separable from the transport mechanism. HIE/HDU, HCCN, vendor-enabled, QHIN-enabled, or other pathways may participate if they can produce conformant outputs under the common trust framework.

### Duration

The brief does not state a definitive duration. It notes that the PHIG timeline is too short for most net-new connectivity builds and that the pilot should accelerate existing efforts. The optional referral extension is positioned as a later or contingent phase.

**Provisional modeling assumption:** 12–18 months total, including approximately:

* 2–4 months for mobilization, design, readiness, and agreements
* 3–6 months for implementation and validation
* 3–6 months for live data exchange and evaluation
* 1–2 months for closeout and scale planning

Duration must remain an editable model input.

### Expected scale

The brief does not specify firm participant counts. It indicates:

* A small number of intermediary models
* More than one intermediary-enabled pathway
* One common measure domain across sites
* Potentially one site-selected extension domain
* Multiple downstream consumers

**Provisional base case:** 2–3 intermediaries, 2–4 provider networks or health systems per intermediary, and 2–4 STLT public health agencies.

### Geographic scope

The pilot is multi-jurisdictional in intent, but participating states, territories, localities, or tribal jurisdictions are not identified. Tribal participation may occur within the main pilot or through a parallel track.

### Data, systems, and services involved

Likely data include:

* Patient demographics
* Encounters
* Diagnoses and conditions
* Blood pressure
* A1c
* BMI and weight
* Medications
* Procedures
* Coverage or payer indicators
* Facility and organization identifiers
* Geography
* Optional SDOH, referral, claims, and dispensing information

Likely technologies and services include:

* FHIR R4 or R4B
* Bulk FHIR
* FHIR REST APIs
* US Core
* USCDI
* QI-Core
* CQL
* Gravity-related specifications
* Master patient index or other matching capability
* Data-quality and conformance tooling
* Identity and access management
* Audit logging
* Secure data-product provisioning

### Anticipated transition

The pilot is intended to transition into:

* Reusable implementation guidance
* Technical-assistance packages for Implementation Centers
* Expansion to additional intermediaries and jurisdictions
* Potential alignment with incentives, federal reporting expectations, and quality-program demand signals
* Possible later use of multi-source linkage, event-driven pipelines, TEFCA-enabled retrieval, and advanced analytics

### Demonstration dimensions

| Demonstration Dimension           | Relevance                       |
| --------------------------------- | ------------------------------- |
| Technical feasibility             | Primary                         |
| Operational feasibility           | Primary                         |
| Organizational readiness          | Primary                         |
| Workflow improvement              | Primary                         |
| Policy and governance feasibility | Primary                         |
| Participant adoption              | Secondary but necessary         |
| Clinical value                    | Indirect                        |
| Public health value               | Primary                         |
| Scalability                       | Primary                         |
| Sustainability                    | Primary, but not fully designed |
| AI readiness                      | Secondary/future-oriented       |

---

# 2. Participating-organization inventory

| Organization Type                                | Role                                                                                               |                       Required or Optional |                              Number Stated | Funding Status                                                | Likely In-Kind Effort                                         | Relationships and Dependencies                                                            |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------- | -----------------------------------------: | -----------------------------------------: | ------------------------------------------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| CDC/OPHDST or pilot sponsor                      | Sponsor, cross-program coordinator, evaluation owner, standards and policy convener                |                                   Required |                      One sponsor structure | Expected sponsor-funded                                       | Leadership and SME effort may be partly absorbed              | Depends on CDC chronic programs, PHIG national partners, ICs, and participant performance |
| CDC chronic disease programs                     | Define surveillance questions, indicators, data requirements, and decision uses                    |                                   Required |                                 Not stated | May be sponsor-funded internally                              | Significant SME participation likely                          | Depend on STLT validation and intermediary products                                       |
| STLT public health agencies                      | Define local questions and actions, participate in governance, validate data products, use outputs |  Required for jurisdictional demonstration |                                 Not stated | Likely subaward or cooperative-agreement funding, but unclear | High risk of uncompensated SME, legal, and informatics effort | Depend on intermediaries, local providers, and CDC requirements                           |
| Tribal public health agencies or tribal partners | Potential participant or parallel track                                                            |                                   Optional |                                 Not stated | Unclear                                                       | Likely                                                        | Requires culturally and legally appropriate engagement and governance                     |
| HIE/HDU                                          | Ingest, normalize, deduplicate, validate, score, provision, support operations                     |               Required for HIE/HDU pathway |              More than one pathway implied | Likely funded through contracts or subawards                  | Some strategic or governance effort may be in kind            | Depends on provider connectivity, data rights, vendors, and STLT governance               |
| HCCN                                             | Aggregate FQHC data, align with HRSA reporting, possibly operate intermediary functions            |             Required only for HCCN pathway |                                 Not stated | Likely funded or supported through existing HRSA mechanisms   | Likely participant coordination effort                        | Depends on FQHC participation, EHR vendors, and HRSA alignment                            |
| FQHCs and community health centers               | Supply source data, validate mappings, remediate data issues, support workflow interpretation      | Required where HCCN/HRSA pathway is tested |                                 Not stated | Funding unclear; stipends or subawards may be needed          | High likelihood                                               | Depend on HCCN, EHR vendor, and operational capacity                                      |
| Health systems and provider organizations        | Supply clinical data and baseline information; participate in validation                           |       Required for clinical source pathway |                                 Not stated | Funding unclear                                               | High likelihood                                               | Depend on interface capabilities and intermediary agreements                              |
| EHR vendors                                      | Enable FHIR access, resolve export limitations, support mapping and testing                        |                                Conditional |                                 Not stated | Vendor fees likely                                            | Limited in-kind support unless strategic partner              | Depend on customer authorization and product maturity                                     |
| Health IT or interoperability vendors            | Provide FHIR, validation, CQL, terminology, API, or data-platform tools                            |                                Conditional |                                 Not stated | Contractor/vendor funded                                      | Possible product contribution                                 | Depend on selected architecture                                                           |
| QHIN or TEFCA-enabled network                    | Optional retrieval or routing pathway                                                              |                            Optional/future |                                 Not stated | Unclear                                                       | Possible                                                      | Depends on permitted-purpose and technical maturity                                       |
| Payers or Medicaid MCOs                          | Optional claims, coverage, dispensing, or continuity information                                   |                            Optional/future |                                 Not stated | Unclear                                                       | Likely                                                        | Requires separate agreements and linkage rules                                            |
| HRSA and related stakeholders                    | Advise on FQHC and HCCN feasibility and reporting alignment                                        |  Important but participation not confirmed |              One federal stakeholder group | Federal staff effort                                          | Likely in kind                                                | Depends on HCCN and FQHC participation                                                    |
| NCQA and quality-measure stakeholders            | Advise on digital measure logic, validation, and portability                                       |                Important but not confirmed |                                 Not stated | Could be contracted or collaborative                          | Possible in-kind collaboration                                | Depends on measure selection and licensing                                                |
| CMS or CMS-aligned programs                      | Possible standards, payer, or quality alignment                                                    |                                   Optional |                                 Not stated | Unclear                                                       | Likely advisory                                               | Depends on selected measures and pathways                                                 |
| CSTE                                             | Co-coordination, STLT alignment, dissemination, surveillance question development                  |                  Expected national partner |                  One national organization | Likely funded through PHIG structure                          | Some effort may be absorbed                                   | Depends on CDC and jurisdiction participation                                             |
| NACDD                                            | Chronic disease subject-matter coordination, peer learning, dissemination                          |                  Expected national partner |                  One national organization | Likely funded through PHIG structure                          | Some effort may be absorbed                                   | Depends on CDC and STLT chronic programs                                                  |
| PHIG national partners                           | Program administration, subawards, coordination, reporting                                         |                 Required within PHIG model | Three nationally, exact pilot role unclear | Sponsor-funded                                                | Limited                                                       | Depend on CDC direction and IC operations                                                 |
| Implementation Centers                           | Readiness assessment, technical assistance, onboarding, remediation support                        |                                   Expected |                                One or more | PHIG-funded                                                   | Possible                                                      | Depend on defined scope, playbook, and participant needs                                  |
| Technical-assistance providers                   | Specialized implementation support                                                                 |                                Conditional |                                 Not stated | Likely funded                                                 | Low                                                           | Depend on IC delivery model                                                               |
| Evaluator                                        | Design and execute cross-site evaluation                                                           |  Required function; organization not named |            One central or distributed team | Sponsor-funded                                                | Low                                                           | Depends on baseline data and participant reporting                                        |
| Legal and privacy advisors                       | DUAs, DSAs, authority, access, minimum necessary, consent                                          |     Required function; ownership not named |     Multiple organizations may use counsel | Mixed sponsor and participant cost                            | High participant in-kind risk                                 | Depends on governance design                                                              |
| Security and compliance teams                    | Security review, access controls, risk assessments, audit expectations                             |                                   Required |                                Distributed | Mixed                                                         | High participant in-kind risk                                 | Depends on hosting and data classifications                                               |
| Standards and terminology SMEs                   | Define profiles, value sets, CQL, mappings, conformance rules                                      |                          Required function |                                 Not stated | Sponsor or contractor funded                                  | Possible federal in kind                                      | Depend on selected measure domain                                                         |
| Cloud service provider                           | Hosting and infrastructure services                                                                |                                Conditional |                                One or more | Vendor expenditure                                            | None                                                          | Depends on intermediary architecture                                                      |
| Community-based organizations                    | Receive or close referrals under optional extension                                                |                                   Optional |                                 Not stated | Funding likely necessary                                      | High in-kind risk                                             | Depends on referral infrastructure and consent                                            |
| MENDS stakeholders                               | Provide lessons, tools, governance patterns, and readiness framing                                 |                    Advisory/reference only |                                 Not stated | Likely in kind or separate funding                            | Likely                                                        | Must not become assumed operational backbone                                              |

---

# 3. Responsibility matrix

| Organization Type             | Explicit Responsibilities                                                              | Implied Responsibilities                                                                                                                                 | Deliverables                                                                              | Inputs Required                                                 | Dependencies                                   | Likely Cost-Bearing Party                                  | Source or Basis                     |
| ----------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------- | ---------------------------------------------- | ---------------------------------------------------------- | ----------------------------------- |
| CDC sponsor/program office    | Set pilot direction; define CDC consumer needs; coordinate national stakeholders       | Program management, budget control, risk management, approval gates, federal security/privacy review                                                     | Charter, requirements, decisions, sponsor reports, evaluation approval                    | Program priorities, funding authority, CDC SMEs                 | PHIG partners, CDC programs, STLTs             | Sponsor                                                    | Explicit plus lifecycle implication |
| CDC chronic programs          | Define surveillance questions and indicators                                           | Validate clinical meaning, approve measure definitions, review outputs, interpret results                                                                | Surveillance requirements, acceptance criteria, utility assessment                        | Program SMEs and current-state workflows                        | STLT programs, data analysts                   | CDC/in kind                                                | Explicit                            |
| PHIG national partner         | Support pilot execution and subawards                                                  | Procurement, fiscal monitoring, recipient reporting, change control                                                                                      | Subawards, financial reports, implementation oversight                                    | CDC scope and funding                                           | ICs and participants                           | Sponsor-funded                                             | Implied by PHIG B4 structure        |
| Implementation Center         | Conduct readiness checks and technical assistance                                      | Develop remediation plans, coach sites, coordinate testing, maintain issue logs                                                                          | Readiness assessments, TA plans, onboarding support, lessons learned                      | Capability checklist and implementation playbook                | Participants and vendors                       | Sponsor-funded                                             | Explicit/strongly implied           |
| STLT public health agency     | Define surveillance questions and actions; participate in governance; validate outputs | Designate users, document current workflow, assess authority, participate in testing, provide decision-utility feedback, establish escalation procedures | Local use-case statement, governance approvals, usability validation, action-use report   | Local program, legal, informatics, and leadership participation | HIE/HDU, providers, CDC                        | Subaward plus in kind                                      | Explicit and inferred               |
| HIE/HDU                       | Ingest, normalize, deduplicate, apply trust layer, provision products                  | Configure infrastructure, maintain environments, manage security, resolve errors, support sources, monitor operations                                    | Operational pipeline, curated dataset, trust reports, audit logs, technical documentation | Source connectivity, specifications, agreements                 | Providers, vendors, STLT governance            | Pilot contract/subaward; possibly existing operating funds | Explicit                            |
| HCCN                          | Aggregate source data and support HRSA alignment                                       | Recruit FQHCs, coordinate vendors, validate patient panels, support remediation and training                                                             | HCCN data feed, site roster, validation responses, HRSA-aligned output                    | FQHC participation and EHR access                               | FQHCs, EHR vendors, HRSA                       | Pilot funding plus HCCN in kind                            | Explicit and inferred               |
| Provider or health system     | Make data available; remediate priority quality problems                               | Approve access, assign technical and clinical SMEs, map local codes, support testing, document workflows, train affected staff                           | Source feed, mapping artifacts, test results, remediation evidence                        | EHR access and staff time                                       | EHR vendor, intermediary                       | Participant, stipend, or subaward                          | Implied                             |
| EHR vendor                    | Support Bulk FHIR or API access                                                        | Product configuration, export troubleshooting, conformance correction, test support                                                                      | Enabled endpoint, technical documentation, defect fixes                                   | Customer authorization                                          | Provider and intermediary                      | Provider or pilot sponsor                                  | Implied                             |
| Terminology/measure team      | Map minimum dataset to standards and measure concepts                                  | Maintain value sets, define CQL, manage versioning, resolve semantic discrepancies                                                                       | Dataset specification, mapping guide, measure logic, test cases                           | Selected domain and consumer requirements                       | CDC, HRSA, NCQA                                | Sponsor/contractor                                         | Explicit                            |
| NCQA/quality stakeholders     | Advise on measure portability and validation                                           | Provide specifications or licensing, review concordance, interpret discrepancies                                                                         | Measure validation memorandum or output                                                   | Selected measures and data                                      | Measure engine and intermediary                | Sponsor or collaborative in kind                           | Explicit but participation unclear  |
| HRSA                          | Advise on reporting realities and HCCN engagement                                      | Confirm whether outputs are acceptable proxies, review burden reduction                                                                                  | HRSA-alignment findings                                                                   | HRSA SMEs                                                       | HCCNs and FQHCs                                | Federal in kind                                            | Explicit                            |
| Legal/privacy teams           | Establish DUAs, DSAs, permitted uses, access tiers, minimum necessary rules            | Authority analysis, retention, redisclosure, data breach terms, consent analysis                                                                         | Executed agreements and legal memoranda                                                   | Data flows, participants, use cases                             | All parties                                    | Distributed participant cost and sponsor templates         | Explicit and implied                |
| Security teams                | Support secure transport, RBAC, audit expectations                                     | Risk assessment, security architecture, account provisioning, incident planning                                                                          | Security plan, access matrix, approval evidence                                           | Architecture and data classification                            | Host and intermediary                          | Distributed                                                | Explicit and implied                |
| Evaluator                     | Measure feasibility, quality, reuse, utility, and time to implement                    | Establish baseline, instrumentation, analysis plan, qualitative interviews, cost-driver capture                                                          | Evaluation plan, interim findings, final report                                           | Performance data and participant interviews                     | All participants                               | Sponsor                                                    | Explicit function                   |
| Data analyst                  | Execute indicators and analyze outputs                                                 | Reconcile source and derived results, stratify outcomes, produce dashboards                                                                              | CDC/STLT/HRSA/quality outputs                                                             | Curated dataset                                                 | Measure logic and governance                   | Sponsor or participant                                     | Explicit/implied                    |
| CSTE/NACDD                    | Co-coordinate and ground STLT benefits                                                 | Support recruitment, communities of practice, dissemination, consensus building                                                                          | Engagement materials, peer-learning products, dissemination                               | CDC direction and site findings                                 | STLTs                                          | PHIG-funded/in kind                                        | Explicit                            |
| CBO/referral platform         | Send and receive referral status under optional add-on                                 | Consent workflow, staff training, status documentation, support                                                                                          | Referral status data and workflow evidence                                                | Existing referral system                                        | Provider, intermediary, community organization | Pilot funding or in kind                                   | Optional/inferred                   |
| MENDS stakeholders            | Provide lessons and reference patterns                                                 | Participate in readiness reviews and documentation                                                                                                       | Readiness addendum                                                                        | MENDS experience                                                | CDC and pilot team                             | In kind or sponsor                                         | Explicit advisory role              |
| Program management contractor | Not expressly assigned                                                                 | Integrated schedule, RAID log, status reporting, meeting facilitation, configuration control, closeout                                                   | Project management plan, schedule, status reports, decision log                           | Sponsor authority and participant plans                         | All workstreams                                | Sponsor                                                    | Necessary implied work              |

---

# 4. Deliverables and milestones

| Deliverable or Milestone                        | Description                                                                                           | Responsible Organization        | Supporting Organizations               | Timing                             | Acceptance Criteria                                                                     | Dependencies                           | Source                         |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------------- | ---------------------------------- | --------------------------------------------------------------------------------------- | -------------------------------------- | ------------------------------ |
| Pilot charter                                   | Confirms purpose, scope, participants, decision rights, schedule, funding, and success measures       | CDC sponsor                     | PHIG partner, CDC programs, STLTs      | Mobilization                       | **Inferred:** approved by sponsor and participating leads                               | Leadership commitment                  | Implied prerequisite           |
| Participant roster                              | Identifies selected intermediaries, STLTs, provider networks, and consumer organizations              | Sponsor/PHIG partner            | ICs, national partners                 | Early planning                     | **Inferred:** readiness criteria met and commitments documented                         | Recruitment and readiness checks       | Implied                        |
| Readiness assessment                            | Evaluates connectivity, FHIR capability, data availability, governance, staffing, and maturity        | IC or evaluator                 | Intermediaries, providers, STLTs       | Pre-implementation                 | **Inferred:** no unresolved critical readiness failure or approved remediation plan     | Capability checklist                   | Explicit operational activity  |
| Surveillance question and action-use package    | Defines questions, users, decision points, interventions, and desired outputs                         | STLT PHA                        | CDC programs, NACDD/CSTE               | Requirements                       | **Inferred:** local program approval and testable link to data elements                 | STLT participation                     | Explicit activity              |
| Consumer requirements matrix                    | Maps CDC, STLT, HRSA-aligned, and quality-consumer needs to the shared dataset                        | Sponsor/standards team          | All consumers                          | Requirements                       | **Inferred:** every required element has owner, definition, and use                     | Consumer commitment                    | Implied                        |
| Minimum dataset specification                   | Defines required and optional data elements and metadata                                              | Standards team                  | CDC, STLTs, HRSA, NCQA, intermediaries | Design                             | Approved minimum scope and version-controlled publication                               | Domain selection                       | Explicit deliverable           |
| FHIR mapping guide                              | Maps dataset to US Core, QI-Core, FHIR paths, terminology, and value sets                             | Interoperability team           | Vendors, intermediaries                | Design                             | Testable mappings, examples, cardinality, vocabulary constraints                        | Dataset specification                  | Explicit                       |
| Conformance test package                        | Automated or repeatable tests for required profiles and fields                                        | Interoperability/test team      | Vendors, ICs                           | Design/testing                     | Agreed pass/fail rules and traceable test results                                       | Mapping guide                          | Explicit                       |
| Governance starter package                      | DUAs, DSAs, permitted uses, access tiers, retention, redisclosure, audit, decision rights             | Legal/governance team           | Sponsor, STLTs, intermediaries         | Before data exchange               | Executed agreements or approved binding alternatives                                    | Final data flows                       | Explicit                       |
| Security and access-control plan                | Documents IAM, RBAC, transport, logging, monitoring, incident response                                | Intermediary/security teams     | Sponsor, STLTs, providers              | Before testing with sensitive data | Security approval from affected parties                                                 | Architecture and agreements            | Inferred                       |
| Technical architecture/design                   | Defines intake, staging, normalization, trust layer, product provisioning, and operational monitoring | Intermediary                    | Sponsor and source teams               | Design                             | **Inferred:** architecture review completed and requirements traced                     | Requirements and environment decisions | Implied                        |
| Source-to-intermediary connectivity             | Enables at least one Bulk FHIR or stable API pathway                                                  | Provider/HCCN and intermediary  | EHR vendors, ICs                       | Build                              | Successful authorized extract containing required resources                             | Agreements and vendor readiness        | Explicit                       |
| Data normalization and deduplication capability | Performs terminology mapping, cohorting, and permissible identity resolution                          | Intermediary                    | Source organizations                   | Build                              | Repeatable processing and documented rules                                              | Data availability                      | Explicit                       |
| Trust-layer implementation                      | Executes conformance, completeness, timeliness, provenance, and audit controls                        | Intermediary                    | Standards and evaluation teams         | Build/testing                      | Required checks operational and reports reproducible                                    | Dataset and validation rules           | Explicit                       |
| Trust scorecard                                 | Presents fit-for-use results and remediation information                                              | Intermediary/evaluator          | Providers, STLTs                       | Testing/operations                 | Scores traceable to data and defects; thresholds approved                               | Trust layer                            | Explicit deliverable           |
| Source remediation cycle                        | Corrects selected high-priority quality issues                                                        | Provider, HCCN, intermediary    | Vendor, IC                             | Testing/operations                 | Agreed issues closed or dispositioned                                                   | Scorecard and support capacity         | Inferred milestone             |
| First successful data product                   | First production-like reusable dataset or derived output                                              | Intermediary                    | Providers, consumers                   | Go-live gate                       | Dataset passes minimum thresholds and is authorized for use                             | Connectivity, trust layer, agreements  | Core milestone                 |
| Multi-consumer demonstration                    | Same underlying dataset produces CDC, HRSA-aligned, and/or quality outputs                            | Intermediary and analytics team | Consumers                              | Pilot operations                   | Proven common lineage and at least two distinct authorized uses; brief aspires to three | First data product                     | Explicit                       |
| Digital measure or indicator execution          | Executes at least one representative chronic measure or indicator                                     | Analytics/measure team          | NCQA/CDC/STLT                          | Pilot operations                   | Reproducible results, defined population, documented discrepancies                      | Curated data and logic                 | Explicit                       |
| Local usability validation                      | STLT users determine whether outputs answer questions and support actions                             | STLT PHA                        | Evaluator                              | Operations                         | Documented utility findings and improvement requests                                    | Stable output                          | Explicit                       |
| Optional referral extension specification       | Defines referral payloads, status values, consent, and workflow                                       | Referral workstream             | Providers, CBOs, Gravity SMEs          | Optional phase                     | Approved minimum dataset and workflow                                                   | Existing infrastructure and governance | Explicit optional deliverable  |
| Optional closed-loop demonstration              | Captures referral status or outcome signals                                                           | Provider/CBO/intermediary       | STLT and evaluator                     | Optional phase                     | At least one end-to-end workflow and analyzable status data                             | Extension specification                | Explicit                       |
| Implementation playbook                         | Documents onboarding, governance, technical implementation, operations, and TA patterns               | Sponsor/IC/evaluator            | All participants                       | Late pilot                         | Usable by a new intermediary or IC without undocumented dependencies                    | Implementation experience              | Explicit                       |
| MENDS-informed readiness addendum               | Documents relevant MENDS governance, query, and readiness lessons                                     | Sponsor/evaluator               | MENDS stakeholders                     | Late pilot                         | Clear boundary between reference learning and pilot infrastructure                      | MENDS engagement                       | Explicit                       |
| Evaluation plan                                 | Defines baselines, measures, methods, data collection, roles, and analysis                            | Evaluator                       | Sponsor and participants               | Before implementation              | Approved measures and feasible data collection                                          | Final scope                            | Necessary inferred deliverable |
| Interim evaluation                              | Identifies implementation progress and required corrective action                                     | Evaluator                       | All parties                            | Mid-pilot                          | Sponsor review and decision on continuation or changes                                  | Operational data                       | Inferred                       |
| Final evaluation report                         | Reports feasibility, trust, reuse, utility, costs/cost drivers, scalability, and limitations          | Evaluator                       | All participants                       | Closeout                           | Evidence traceable to agreed measures                                                   | Completed pilot period                 | Explicit objective             |
| Scale-readiness assessment                      | Assesses applicability to less mature organizations and future domains                                | Evaluator/IC                    | Participants                           | Closeout                           | Risks and prerequisites identified                                                      | Final findings                         | Explicit risk mitigation       |
| Transition and sustainability plan              | Defines operational ownership, recurring costs, support, and expansion options                        | Sponsor and partners            | Intermediaries, STLTs, PHIG partners   | Closeout                           | Named post-pilot owners or explicit termination plan                                    | Cost and performance findings          | Implied                        |
| Pilot closeout                                  | Reconciles finances, data disposition, access, documentation, and lessons                             | PHIG partner/sponsor            | All parties                            | End                                | Deliverables accepted; data handled per agreements; open issues transferred or closed   | All prior work                         | Inferred                       |

---

# 5. Technical and operational model

## 5.1 Systems and platforms

The source establishes functional requirements but not a final architecture. Anticipated components include:

* Provider EHRs and clinical data repositories
* FQHC and HCCN aggregation environments
* HIE/HDU clinical repositories or data platforms
* FHIR servers and Bulk Data endpoints
* API gateway or secure transfer services
* Master patient index or panel-based identity services
* Terminology and value-set services
* Conformance-validation tooling
* Data-quality scoring services
* Provenance and audit stores
* CQL or other measure-execution engine
* Analytics workbench, dashboard, or export environment
* CDC, STLT, HRSA-aligned, and quality-consumer environments

A shared national pilot hub is mentioned conceptually in some passages but is not established as mandatory.

## 5.2 Identity and access management

Explicit requirements include:

* Role-based authorization
* Purpose-limited access
* Auditable access
* Patient-level versus aggregate access tiers
* Minimum necessary sharing
* De-identification where required

Not defined:

* Identity provider
* Authentication protocol
* Whether SMART Backend Services will be used
* Cross-organization federation
* Credential lifecycle
* Break-glass or emergency access
* Privileged-access management

These must be treated as open architecture decisions.

## 5.3 Hosting and environments

The brief does not state whether environments will be hosted by:

* Each intermediary
* A national partner
* CDC
* A commercial cloud platform
* A shared pilot hub

At minimum, later costing should consider:

* Development
* Test or integration
* User acceptance or validation
* Production or production-like pilot
* Potential disaster-recovery environment

## 5.4 Security controls

Likely controls include:

* Encryption in transit and at rest
* RBAC
* Audit logging
* Data minimization
* Environment separation
* Secure API access
* Vulnerability and patch management
* Incident response
* Access review
* Backup and recovery
* Data retention and destruction

The applicable federal or participant security frameworks are not identified.

## 5.5 Validation and error handling

The trust layer is expected to perform:

* Profile and cardinality validation
* Vocabulary and value-set validation
* Required-field checks
* Cohort and measure-data checks
* Completeness scoring
* Timeliness calculations
* Provenance checks
* Deduplication and continuity indicators
* Transformation logging

Necessary but unassigned error-handling functions include:

* Error categorization
* Rejection versus warning rules
* Source notification
* Resubmission or reprocessing
* Defect ownership
* Escalation
* Exception approval
* Monitoring for drift
* Version compatibility management

## 5.6 Support model

A viable pilot will require:

* Participant onboarding support
* Endpoint and credential support
* Mapping assistance
* Validation-report interpretation
* Vendor escalation
* Issue triage
* Change management
* Release communication
* Operational monitoring
* Incident handling

The brief does not identify who will operate a help desk or what service levels will apply.

## 5.7 High-level data-flow table

| Sender or Actor         | Recipient or Actor                | Data or Service Exchanged                                              | Method or Standard                                         | Frequency                     | Volume                  | New or Existing Capability                                  | Technical Work Required                                  | Uncertainty |
| ----------------------- | --------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------- | ----------------------------- | ----------------------- | ----------------------------------------------------------- | -------------------------------------------------------- | ----------- |
| EHR or provider network | HIE/HDU                           | Patient, encounter, condition, observation, medication, procedure data | Bulk FHIR or REST API                                      | Scheduled; cadence not stated | Unknown                 | Existing endpoint preferred; pilot configuration likely new | Authorization, group definition, mapping, export testing | High        |
| FQHC                    | HCCN                              | Clinical and reporting data                                            | Existing network aggregation, FHIR where available         | Unknown                       | Unknown                 | Mostly existing                                             | Dataset expansion, mapping, quality remediation          | Moderate    |
| HCCN                    | HIE/HDU or pilot processing layer | Aggregated or patient-level chronic dataset                            | FHIR/API or agreed exchange                                | Scheduled                     | Unknown                 | May be new                                                  | Integration, patient-panel logic, provenance             | High        |
| HIE/HDU                 | Internal normalization service    | Raw clinical records                                                   | Platform-native                                            | Per ingest cycle              | Unknown                 | Existing capability may be reused                           | Mapping, transformations, deduplication                  | Moderate    |
| HIE/HDU                 | Identity service                  | Identifiers or match request                                           | MPI or panel-based process                                 | Per ingest                    | Unknown                 | Existing                                                    | Match configuration and governance                       | High        |
| HIE/HDU                 | Validation service                | FHIR resources and metadata                                            | FHIR validators, custom rules                              | Per ingest                    | Proportional to records | Likely partly new                                           | Rule implementation, thresholds, reporting               | Moderate    |
| Validation service      | Provider/HCCN                     | Defect and quality report                                              | Dashboard, report, API, or ticket                          | Per cycle or release          | Low-volume reports      | Likely new                                                  | Feedback interface and workflow                          | High        |
| HIE/HDU                 | CDC program                       | Curated dataset or indicator output                                    | Secure API, Bulk FHIR, files, or aggregate product         | Scheduled                     | Unknown                 | New or adapted                                              | Consumer-specific packaging, access control              | High        |
| HIE/HDU                 | STLT PHA                          | Patient-level, limited, or aggregate product                           | Secure API, dashboard, or export                           | Scheduled                     | Unknown                 | New or adapted                                              | Local product design and authorization                   | High        |
| HIE/HDU                 | HRSA-aligned workflow             | Reporting artifact or de-identified dataset                            | Not established                                            | Scheduled                     | Unknown                 | Demonstration capability                                    | De-identification, mapping, packaging                    | High        |
| HIE/HDU                 | Measure engine                    | Curated measure input                                                  | FHIR/QI-Core/CQL inputs                                    | Per measurement cycle         | Unknown                 | New or existing                                             | CQL compatibility, terminology, cohort logic             | Moderate    |
| Measure engine          | NCQA/quality stakeholder          | Digital measure output                                                 | MeasureReport or other agreed artifact                     | Per cycle                     | Low                     | Demonstration                                               | Validation and reconciliation                            | Moderate    |
| HIE/HDU                 | Audit/monitoring service          | Access, transformation, and operational logs                           | Platform-native                                            | Continuous                    | Moderate/high           | Existing plus extensions                                    | Log schema and retention                                 | Moderate    |
| Provider                | Referral recipient                | Referral request                                                       | ServiceRequest/Task/CarePlan patterns or existing platform | Event-driven                  | Unknown                 | Optional existing ecosystem                                 | Workflow integration and consent                         | High        |
| Referral recipient      | Provider/intermediary             | Referral status and outcome                                            | Task/status or platform interface                          | Event-driven                  | Unknown                 | Optional                                                    | Status vocabulary and closure logic                      | High        |
| MENDS stakeholder       | Pilot team                        | Lessons, tools, readiness methods                                      | Documentation and consultation                             | Periodic                      | Not data flow           | Existing knowledge                                          | Analysis only                                            | Low         |

---

# 6. Project-phase breakdown

## Phase 1: Mobilization and planning

**Major activities**

* Establish sponsor governance and project management.
* Confirm the core chronic domain.
* Determine whether referral work is in or out.
* Define candidate participant models.
* Develop schedule, budget controls, risk register, and reporting cadence.
* Establish the engagement and decision process.

**Participants**

CDC sponsor, CDC programs, PHIG national partners, CSTE, NACDD, ICs, evaluator.

**Outputs**

Pilot charter, preliminary schedule, stakeholder map, risk register, decision log.

**Entry criteria**

Sponsor authorization and preliminary funding.

**Exit criteria**

Approved charter, named leadership, defined decision rights, initial scope boundaries.

---

## Phase 2: Requirements and readiness assessment

**Major activities**

* Define STLT surveillance questions and public health actions.
* Select common measure domain and optional extension.
* Inventory existing feeds, endpoints, data, vendors, staffing, and governance.
* Assess intermediary and provider maturity.
* Select pilot participants.

**Participants**

STLTs, intermediaries, providers, HCCNs, CDC, HRSA/quality advisors, ICs.

**Outputs**

Requirements matrix, readiness assessments, participant roster, remediation plans.

**Entry criteria**

Approved pilot charter and selection criteria.

**Exit criteria**

Participants meet minimum readiness or have funded remediation plans.

---

## Phase 3: Governance, legal, privacy, and security preparation

**Major activities**

* Determine legal authority and permitted uses.
* Define patient-level, limited, de-identified, and aggregate access tiers.
* Negotiate DUAs and DSAs.
* Establish retention, redisclosure, breach, and audit terms.
* Complete security design and approvals.
* Define decision rights for dataset and measure changes.

**Participants**

Legal counsel, privacy officers, security teams, STLT leadership, intermediaries, providers, sponsor.

**Outputs**

Executed agreements, access matrix, governance charter, security plan.

**Entry criteria**

Defined actors, data flows, and intended uses.

**Exit criteria**

Authority to exchange test and pilot data; required security approvals.

---

## Phase 4: Architecture and detailed design

**Major activities**

* Finalize dataset specification.
* Map data to FHIR resources and terminology.
* Design identity and deduplication workflow.
* Define trust-layer rules and thresholds.
* Design consumer products.
* Define operational monitoring, error handling, and support.

**Participants**

Interoperability architects, intermediary engineers, providers, measure SMEs, security teams, evaluator.

**Outputs**

Architecture, mapping guide, conformance tests, quality rulebook, test plan.

**Entry criteria**

Requirements and governance substantially stable.

**Exit criteria**

Design review approval and traceability to requirements.

---

## Phase 5: Configuration, development, and integration

**Major activities**

* Configure Bulk FHIR groups or APIs.
* Establish credentials and connectivity.
* Build or configure ingestion.
* Implement normalization and terminology mapping.
* Configure identity and deduplication.
* Implement validation and trust reporting.
* Configure downstream products and measure execution.

**Participants**

Intermediary, providers, HCCN, EHR vendors, technical vendors, ICs.

**Outputs**

Configured environments, working interfaces, initial data loads, operational runbooks.

**Entry criteria**

Design approved and agreements permit technical exchange.

**Exit criteria**

End-to-end technical flow works with test or synthetic data.

---

## Phase 6: Testing and validation

**Major activities**

* Unit, integration, conformance, security, and user-acceptance testing.
* Validate completeness and timeliness calculations.
* Reconcile measure or indicator outputs.
* Conduct source remediation cycles.
* Exercise incident, retry, and escalation procedures.
* Validate provenance and audit records.

**Participants**

All technical participants, STLT users, evaluators, vendors.

**Outputs**

Test results, defect logs, remediation evidence, go-live recommendation.

**Entry criteria**

Working end-to-end flow.

**Exit criteria**

Minimum thresholds satisfied; critical defects closed; authorized go-live.

---

## Phase 7: Onboarding and training

**Major activities**

* Train data-source personnel on quality reports and remediation.
* Train STLT users on data products and limitations.
* Train operations staff on support and escalation.
* Document onboarding steps for repeatability.

**Participants**

ICs, intermediaries, providers, STLTs, trainers.

**Outputs**

Training materials, attendance records, onboarding checklists, support procedures.

**Entry criteria**

Stable pilot release and defined user groups.

**Exit criteria**

Users and operators demonstrate readiness.

---

## Phase 8: Pilot operations

**Major activities**

* Run scheduled ingestion and processing.
* Produce trust reports and data products.
* Execute measures and indicators.
* Monitor reliability, latency, defects, and support tickets.
* Gather decision-utility feedback.
* Iterate high-priority quality improvements.

**Participants**

Intermediaries, providers, STLTs, CDC programs, evaluator, ICs.

**Outputs**

Recurring data products, dashboards or reports, operational metrics, issue logs.

**Entry criteria**

Go-live approval.

**Exit criteria**

Minimum live-operation period completed with sufficient evidence.

---

## Phase 9: Optional referral extension

**Major activities**

* Define referral and status data.
* Confirm consent and minimum-necessary rules.
* Configure existing referral platform or interfaces.
* Test referral initiation and closure.
* Measure completion and drop-off.

**Participants**

Providers, CBOs, referral-platform vendors, intermediary, STLT.

**Outputs**

Referral specification, end-to-end demonstration, evaluation findings.

**Entry criteria**

Existing referral infrastructure and approved governance.

**Exit criteria**

Usable referral status data captured and evaluated.

---

## Phase 10: Evaluation, transition, and closeout

**Major activities**

* Analyze time to implement, quality, reuse, utility, and burden.
* Capture actual participant effort and non-labor costs.
* Assess scalability and limitations.
* Develop playbook and readiness addendum.
* Determine continuation, expansion, or termination.
* Close agreements, accounts, finances, and data handling.

**Participants**

Evaluator, sponsor, all participant types.

**Outputs**

Final evaluation, implementation playbook, scale-readiness assessment, sustainability plan, closeout package.

**Entry criteria**

Pilot operations completed.

**Exit criteria**

Deliverables accepted and post-pilot responsibilities resolved.

---

# 7. Cost-driver register

| Cost Driver                    | Description                                                              | Cost Category                                        | Scaling Unit           |                           Known Quantity | Potential Range                      | Organizations Affected               | Likely Cost Effect | Source or Assumption     |
| ------------------------------ | ------------------------------------------------------------------------ | ---------------------------------------------------- | ---------------------- | ---------------------------------------: | ------------------------------------ | ------------------------------------ | ------------------ | ------------------------ |
| Intermediary count             | Number of HIEs, HDUs, HCCNs, or other pathways implemented               | Step-fixed; per organization; one-time and recurring | Intermediary           |                    More than one implied | 2–4                                  | Sponsor, intermediaries, evaluator   | Very high          | Provisional              |
| STLT count                     | Number of jurisdictions participating                                    | Per organization; variable                           | Jurisdiction           |                               Not stated | 2–5                                  | Sponsor, ICs, STLTs                  | High               | Provisional              |
| Provider-network count         | Number of health systems, FQHC networks, or provider groups              | Variable; per organization                           | Network                |                               Not stated | 4–12                                 | Intermediaries, vendors, providers   | High               | Provisional              |
| Individual site count          | Facilities requiring configuration, validation, or training              | Variable; per site                                   | Site                   |                               Not stated | 10–100+                              | Providers, intermediaries, ICs       | High               | Open                     |
| EHR-vendor count               | Distinct source products requiring testing                               | Step-fixed; per vendor                               | Vendor/product         |                               Not stated | 2–8                                  | Providers and intermediaries         | High               | Open                     |
| Source endpoint count          | Bulk FHIR or API endpoints connected                                     | Per interface; one-time and recurring                | Endpoint               |                               Not stated | 4–20                                 | Intermediaries, providers            | Very high          | Open                     |
| Consumer-output count          | Distinct CDC, STLT, HRSA, or quality products                            | Per use case/output                                  | Output                 |                                 Multiple | 2–5                                  | Intermediaries and analytics teams   | High               | Explicit/parameter       |
| Chronic-domain count           | Common domain plus site-selected extensions                              | Per use case                                         | Domain                 |          One common; optional extensions | 1–4                                  | Standards, analytics, providers      | Moderate/high      | Explicit                 |
| Measure count                  | Number of indicators or digital measures executed                        | Per measure                                          | Measure                |                             At least one | 1–6                                  | Measure team, evaluator              | Moderate/high      | Explicit/parameter       |
| Data-element count             | Required and optional fields in minimum dataset                          | Variable                                             | Element                |                               Not stated | 20–100+                              | Standards, providers, intermediaries | Moderate           | Open                     |
| FHIR-resource count            | Number of resource types and profiles                                    | Variable                                             | Resource/profile       |            Approximately 7–10 identified | 7–15                                 | Technical teams                      | Moderate           | Explicit                 |
| Data volume                    | Patients, encounters, observations, and history processed                | Variable and recurring                               | Records/GB/patient     |                               Not stated | Wide                                 | Intermediary/cloud                   | Moderate to high   | Open                     |
| Refresh cadence                | Monthly, weekly, daily, or near-real-time                                | Recurring; per month                                 | Processing cycle       |                               Not stated | Monthly to daily                     | Intermediary, support                | High               | Open                     |
| Historical lookback            | Amount of longitudinal data loaded                                       | One-time variable                                    | Years/patients         |                               Not stated | 1–5 years                            | Providers, intermediaries            | High               | Open                     |
| Identity-matching complexity   | Panel-based versus enterprise MPI versus privacy-preserving linkage      | One-time and recurring                               | Matching method/source |                 Required within boundary | Low to high                          | Intermediaries, privacy teams        | High               | Explicit but unresolved  |
| De-identification requirements | Consumer-specific data transformation                                    | Per consumer/output                                  | Rule set               | Some HRSA-aligned outputs may require it | 1–4 rule sets                        | Intermediary, privacy/legal          | Moderate/high      | Explicit                 |
| Data-quality-rule count        | Number of conformance, completeness, timeliness, and provenance rules    | Step-fixed                                           | Rule                   |                               Not stated | 25–200+                              | Standards and intermediary           | Moderate/high      | Open                     |
| Source remediation intensity   | Number and severity of defects addressed                                 | Variable                                             | Defect cycle/source    |                               Not stated | 1–5 cycles per source                | Providers, vendors, ICs              | Very high          | Inferred                 |
| Existing connectivity reuse    | Degree to which endpoints and feeds already exist                        | Cost-reducing factor                                 | Percentage reused      |            Existing foundation preferred | 40–100%                              | All technical parties                | Very high          | Explicit principle       |
| Custom development             | New adapters, dashboards, rule engines, or products                      | One-time                                             | Component              |                               Not stated | Minimal to substantial               | Sponsor/intermediary                 | Very high          | Open                     |
| Standards maturity             | Whether required data are available in standardized form                 | Risk/contingency                                     | Domain/source          |                                 Variable | Low–high maturity                    | Providers, vendors                   | High               | Explicit risk            |
| Measure licensing              | Access to proprietary specifications or tools                            | Recurring/one-time                                   | Measure set            |                                  Unknown | None to material                     | Sponsor/measure team                 | Moderate           | Open                     |
| Environment count              | Development, test, validation, production, DR                            | Step-fixed; per environment                          | Environment            |                               Not stated | 3–5 per implementation               | Intermediary/cloud                   | Moderate/high      | Assumption               |
| Hosting model                  | Existing intermediary infrastructure versus new pilot hub                | Fixed and recurring                                  | Platform               |                               Unresolved | Existing-only to new shared platform | Sponsor/intermediary                 | Very high          | Open                     |
| Governance-agreement count     | Number of DUAs/DSAs and amendments                                       | Per agreement                                        | Agreement              |                               Not stated | 5–30+                                | Legal teams                          | High               | Open                     |
| Agreement complexity           | Bilateral versus common/template agreements                              | Schedule and labor driver                            | Agreement model        |                     Common model desired | Low–high                             | All organizations                    | Very high          | Explicit risk            |
| Security review count          | Number of organizational approvals                                       | Per organization/environment                         | Review                 |                               Not stated | 4–20                                 | Security/legal                       | High               | Inferred                 |
| Participant procurement        | Contracting, subaward, or vendor procurement cycles                      | Schedule and fixed labor                             | Procurement action     |                               Not stated | 3–15                                 | Sponsor/PHIG partner/participants    | High               | Inferred                 |
| Readiness variation            | Difference between advanced and less mature sites                        | Variable/contingency                                 | Participant tier       |                               Known risk | Low/base/high tiers                  | ICs and participants                 | Very high          | Explicit                 |
| Technical-assistance intensity | Coaching and hands-on implementation support                             | Variable; per cohort/site                            | TA hours/site          |                               Not stated | Light to intensive                   | ICs                                  | High               | Explicit                 |
| Training cohorts               | Number of technical, operational, and PHA user groups                    | Per cohort                                           | Cohort                 |                               Not stated | 3–15                                 | ICs, participants                    | Moderate           | Inferred                 |
| Help-desk volume               | Support incidents during onboarding and operations                       | Recurring                                            | Ticket/month           |                               Not stated | Low–high                             | Intermediary/IC                      | Moderate           | Open                     |
| Pilot-operation duration       | Length of production-like exchange                                       | Per month                                            | Month                  |                               Not stated | 3–6 months base                      | All parties                          | Very high          | Assumption               |
| Planning duration              | Time spent obtaining decisions and agreements                            | Per month                                            | Month                  |                               Not stated | 2–6 months                           | Sponsor and participants             | High               | Open                     |
| Evaluation design complexity   | Cross-site quantitative and qualitative evaluation                       | Fixed plus per site                                  | Site/measure           |                        Multi-dimensional | Moderate–high                        | Evaluator, participants              | High               | Explicit                 |
| Baseline availability          | Availability of current-state time, cost, quality, and reporting metrics | Cost/risk                                            | Data source            |                                  Unclear | Poor to strong                       | Evaluator and participants           | High               | Open                     |
| Participant labor capture      | Effort required to measure full economic cost                            | Per organization                                     | Participant            |                            Not specified | All participants                     | Evaluator/PM                         | Moderate           | Stage 1 requirement      |
| Reporting cadence              | Frequency of sponsor, PHIG, and stakeholder reporting                    | Recurring                                            | Report/month           |                               Not stated | Monthly/quarterly                    | PM, participants                     | Moderate           | Open                     |
| Travel                         | Site visits, workshops, national meetings                                | Variable                                             | Trip/site              |                               Not stated | 0–3 trips/site                       | Sponsor, ICs, evaluator              | Low/moderate       | Open                     |
| Tribal engagement              | Separate consultation, governance, or technical track                    | Step-fixed                                           | Track/jurisdiction     |                                 Optional | 0–2 tracks                           | Sponsor, tribal partners             | Moderate/high      | Explicit option          |
| Referral extension             | Additional workflow, CBOs, consent, and status data                      | Step-fixed plus per participant                      | Extension/site         |                                 Optional | 0 or 1 extension                     | All referral participants            | Very high          | Explicit option          |
| Payer-data extension           | Claims and dispensing supplements                                        | Per payer/interface                                  | Payer                  |                          Future/optional | 0–3                                  | Payers/intermediaries                | High               | Optional                 |
| Sustainability planning        | Financial, governance, and operational transition                        | Fixed                                                | Plan/model             |                      Required implicitly | One cross-pilot plus site plans      | Sponsor and partners                 | Moderate           | Inferred                 |
| Contingency                    | Unknown vendor, legal, data, and readiness issues                        | Contingency                                          | Percentage/risk event  |                               Not stated | Low/base/high                        | Sponsor and participants             | High               | Required model treatment |

---

# 8. Labor-category and non-labor-cost inventory

## 8.1 Likely sponsor and central-program labor

* Executive sponsor
* Program director
* Pilot program manager
* Deputy or workstream project managers
* Contract and subaward manager
* Financial analyst
* Grants-management specialist
* Procurement specialist
* Program analyst
* Stakeholder-engagement lead
* Communications and dissemination specialist
* Administrative coordinator
* Risk and quality manager

## 8.2 Public health and clinical labor

* Chronic disease epidemiologist
* Public health informatics specialist
* Hypertension SME
* Diabetes SME
* Obesity and nutrition SME
* Asthma SME, where selected
* Clinical quality-measure SME
* FQHC operations SME
* Public health program manager
* STLT surveillance analyst
* Health-equity specialist
* Community referral SME
* Clinical workflow analyst

## 8.3 Technical labor

* Enterprise architect
* Solution architect
* Interoperability architect
* FHIR architect
* FHIR implementation engineer
* Integration engineer
* API engineer
* Bulk FHIR specialist
* Data engineer
* ETL or transformation developer
* Terminology specialist
* Clinical informaticist
* Data-modeler
* Master-patient-index specialist
* Privacy-preserving linkage specialist
* CQL developer
* Measure-engine specialist
* Application developer
* Dashboard developer
* Cloud architect
* Cloud engineer
* Database administrator
* DevOps engineer
* Site-reliability engineer
* Test architect
* QA analyst
* Conformance-test engineer
* Performance-test engineer
* Technical writer

## 8.4 Governance, legal, privacy, and security labor

* Governance lead
* Public health law specialist
* Healthcare attorney
* Contract attorney
* Privacy officer
* Consent specialist
* Data-sharing-agreement specialist
* Security architect
* Security engineer
* Information-system security officer
* Risk assessor
* Compliance analyst
* IAM engineer
* Audit and logging specialist
* Incident-response specialist

## 8.5 Implementation and operations labor

* Participant onboarding manager
* Technical-assistance lead
* Technical-assistance specialist
* Implementation specialist
* Vendor product specialist
* Trainer
* Change-management specialist
* Help-desk analyst
* Tier 2 support engineer
* Tier 3 integration engineer
* Operations manager
* Data-quality analyst
* Release manager
* Service-delivery manager

## 8.6 Evaluation labor

* Evaluation director
* Evaluation-methodologist
* Health-services researcher
* Public health evaluator
* Quantitative analyst
* Qualitative researcher
* Statistician
* Data analyst
* Cost analyst or health economist
* Interviewer or facilitator
* Technical editor
* Dissemination specialist

## 8.7 Participant-contributed labor likely to be overlooked

* STLT program leadership
* STLT legal counsel
* STLT privacy and security staff
* Local epidemiologists
* Provider clinical champions
* Provider interface analysts
* EHR application analysts
* Health-system compliance officers
* FQHC operations staff
* HCCN relationship managers
* HIE/HDU governance committees
* Vendor account and product staff
* CBO referral coordinators
* Executive review and approval time

## 8.8 Likely non-labor costs

### Technology

* Cloud compute, storage, networking, backup, and logging
* FHIR server licenses or subscriptions
* API-management services
* Interface-engine licensing
* Terminology-service licensing
* Data-quality or conformance tools
* CQL or measure-engine licensing
* MPI or record-linkage software
* Privacy-preserving linkage tools
* Dashboard and analytics licenses
* Security and monitoring tools
* Identity-provider or access-management fees
* Ticketing and support-platform costs
* Test-data generation tools
* Software development environments
* Certificates and key-management services
* Data-egress and transaction charges

### Vendor and implementation

* EHR vendor implementation fees
* Endpoint enablement fees
* Interface-development charges
* Custom mapping fees
* Vendor professional services
* Product configuration fees
* Measure licensing or validation fees
* External security testing
* Penetration testing
* Independent verification and validation

### Participant support

* Subawards
* Participant stipends
* Provider implementation grants
* HIE/HDU configuration payments
* CBO participation payments
* Travel reimbursement
* Backfill for clinical or public health staff
* Training-material production

### Program and evaluation

* External evaluation contract
* Survey or interview tools
* Transcription
* Publication and dissemination
* Meeting facilitation
* Conference participation
* Site visits
* Legal services
* Accessibility and 508 remediation
* Independent cost review
* Contingency reserve

No rates, hours, or dollar values should be assigned until Stage 2 benchmarking and Stage 3 WBS development.

---

# 9. Assumptions register

| ID  | Assumption                                                                                    | Category       | Basis                                                            | Effect on Scope or Cost                                           | Confidence | Validation Needed              | Recommended Model Treatment          |
| --- | --------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------- | ---------- | ------------------------------ | ------------------------------------ |
| A01 | The pilot will include 2–3 intermediary organizations                                         | Participation  | More than one pathway is expected, but count is absent           | Drives duplicated implementation, governance, and evaluation work | Moderate   | Sponsor decision               | Editable input                       |
| A02 | Two to four STLT jurisdictions will participate                                               | Participation  | Multi-site evidence is needed                                    | Drives subawards, legal work, TA, and evaluation                  | Low        | Recruitment plan               | Low/base/high range                  |
| A03 | Each intermediary will connect 2–4 provider networks                                          | Participation  | Needed for meaningful source diversity                           | Drives interface and onboarding count                             | Low        | Candidate inventory            | Editable input                       |
| A04 | Existing connectivity will be used wherever possible                                          | Technical      | Explicit pilot principle                                         | Reduces implementation cost and schedule risk                     | High       | Readiness assessment           | Fixed assumption with exception flag |
| A05 | Net-new EHR connectivity is generally out of scope unless narrowly funded                     | Scope          | Timeline described as too short for greenfield builds            | Prevents model from assuming nationwide endpoint creation         | Moderate   | Sponsor confirmation           | Fixed assumption or exclusion        |
| A06 | One common chronic domain will be mandatory across sites                                      | Scope          | Explicit                                                         | Constrains standards and measure work                             | High       | Domain selection               | Fixed assumption                     |
| A07 | Hypertension or glycemic status will be the common domain                                     | Scope          | Examples provided, not decision                                  | Changes data elements, measure logic, and stakeholder mix         | Low        | CDC/STLT decision              | Editable input                       |
| A08 | Each site may add at most one extension domain                                                | Scope          | Explicit option                                                  | Adds marginal mapping and evaluation effort                       | Moderate   | Site proposals                 | Per-use-case variable                |
| A09 | The referral workflow will be excluded from the base estimate                                 | Scope          | Clearly optional and higher risk                                 | Prevents major scope distortion                                   | High       | Sponsor add-on decision        | Separate optional scenario           |
| A10 | Live pilot operations will last at least three months                                         | Schedule       | Needed to observe repeated data cycles; not stated               | Significant recurring labor and hosting impact                    | Moderate   | Evaluation design              | Editable 3–6 month range             |
| A11 | Total project duration will be approximately 12–18 months                                     | Schedule       | PHIG context and required lifecycle                              | Drives PM, governance, and operations cost                        | Low        | Master schedule                | Low/base/high range                  |
| A12 | Each implementation will use at least development, test, and production-like environments     | Technical      | Normal implementation practice                                   | Adds cloud, deployment, and support cost                          | Moderate   | Architecture                   | Editable input                       |
| A13 | Existing intermediary platforms will host core processing                                     | Technical      | Intermediary is described as operational platform                | Avoids creating a central platform by default                     | Moderate   | Hosting decision               | Base-case assumption                 |
| A14 | A central shared pilot platform may still be needed for cross-site evaluation or products     | Technical      | Pilot hub language and multi-consumer needs are ambiguous        | Could introduce major fixed cost                                  | Low        | Architecture decision          | Alternative scenario                 |
| A15 | Bulk FHIR will be preferred, but REST APIs may be used                                        | Technical      | Explicit                                                         | Endpoint type materially changes integration effort               | High       | Site readiness                 | Per-interface parameter              |
| A16 | Data refresh will be at least monthly and may be weekly or daily                              | Operational    | Chronic surveillance does not necessarily require real time      | Drives recurring processing and support                           | Low        | Consumer requirements          | Editable input                       |
| A17 | An initial historical load of 1–3 years will be required                                      | Technical      | Longitudinal cascade analysis requires history                   | Increases data volume and quality work                            | Low        | Measure definitions            | Low/base/high range                  |
| A18 | Identity resolution will occur within the intermediary’s authorized boundary                  | Governance     | Explicit                                                         | Requires MPI or panel logic but limits cross-entity linkage scope | High       | Governance design              | Fixed assumption                     |
| A19 | Some consumer outputs will require de-identification or aggregation                           | Privacy        | Explicit example                                                 | Adds consumer-specific transformation and validation              | High       | Consumer agreements            | Per-output variable                  |
| A20 | Each participant will require separate legal and security review even when templates are used | Legal/security | Typical cross-organization practice                              | Major distributed labor cost                                      | Moderate   | Agreement strategy             | Per-organization variable            |
| A21 | Model DUA/DSA templates will be centrally developed                                           | Governance     | Needed for scale and referenced conceptually                     | Creates central fixed cost but reduces marginal cost              | Moderate   | Sponsor decision               | Fixed plus per-agreement variable    |
| A22 | NCQA participation and access to measure specifications are not guaranteed                    | Participation  | Advisory role is described, not confirmed                        | May change licensing and validation cost                          | High       | Partner agreement              | Unresolved decision                  |
| A23 | HRSA will advise but will not operate the pilot platform                                      | Participation  | Brief describes advisory role                                    | Limits assumed HRSA implementation cost                           | Moderate   | HRSA commitment                | Base-case fixed assumption           |
| A24 | STLTs will receive some subaward funding                                                      | Funding        | PHA-specific deliverables are expected, but mechanism is unclear | Affects sponsor-versus-in-kind allocation                         | Low        | PHIG funding design            | Editable funding allocation          |
| A25 | Providers will otherwise contribute substantial in-kind effort                                | Funding        | No provider funding mechanism is stated                          | Important to full economic cost                                   | High       | Participation agreements       | Track separately as in kind          |
| A26 | HIEs/HDUs will charge for configuration, mapping, and operations                              | Funding        | Cost pass-through risk is explicitly identified                  | Major sponsor or participant cost                                 | High       | Partner proposals              | Per-intermediary range               |
| A27 | Source remediation will be limited to high-priority defects                                   | Scope          | Pilot cannot resolve all source quality issues                   | Constrains open-ended vendor and provider labor                   | Moderate   | Quality plan                   | Fixed rule plus capped cycles        |
| A28 | Two remediation cycles per source are included in the base case                               | Operational    | Reasonable minimum for demonstrating improvement                 | Influences provider/vendor effort                                 | Low        | Test plan                      | Editable input                       |
| A29 | The trust scorecard will be implemented at the intermediary level                             | Technical      | Source comments indicate HIE/HDU is most likely owner            | Concentrates tooling cost at intermediaries                       | Moderate   | Ownership decision             | Base-case assumption                 |
| A30 | STLTs will validate scorecard usefulness rather than directly manage source remediation       | Operational    | Source commentary suggests intermediary-led remediation          | Reduces PHA technical burden but not oversight effort             | Moderate   | Operating model                | Base-case assumption                 |
| A31 | Evaluation will include both quantitative metrics and qualitative utility assessment          | Evaluation     | Decision/action utility cannot be measured technically alone     | Adds interviews and analysis                                      | High       | Evaluation plan                | Fixed assumption                     |
| A32 | Evaluation will capture actual participant labor and non-labor cost data                      | Evaluation     | Needed for full economic cost and future modeling                | Adds burden but improves defensibility                            | Moderate   | Sponsor approval               | Fixed assumption                     |
| A33 | Existing baselines will be incomplete                                                         | Evaluation     | Current burden and quality metrics are rarely standardized       | Requires reconstruction or proxy methods                          | Moderate   | Baseline assessment            | Contingency risk                     |
| A34 | Public health utility will be assessed separately for each jurisdiction                       | Evaluation     | Local decision points differ                                     | Adds per-site evaluation work                                     | High       | Evaluation plan                | Per-jurisdiction variable            |
| A35 | Formal model comparison among intermediary archetypes is out of scope                         | Scope          | Explicitly stated for Phase 1                                    | Avoids statistically powered comparative evaluation               | High       | Sponsor confirmation           | Fixed assumption                     |
| A36 | MENDS will not supply the operational patient-level dataset                                   | Scope          | Explicit                                                         | Avoids misallocating platform work to MENDS                       | High       | None                           | Fixed exclusion                      |
| A37 | MENDS stakeholders will provide limited advisory support                                      | Participation  | Explicit learning track                                          | Adds modest consultation effort                                   | Moderate   | Engagement plan                | Fixed advisory allowance             |
| A38 | Tribal participation will be a separately priced option unless confirmed early                | Participation  | Main versus parallel track unresolved                            | Avoids underestimating engagement and governance                  | Moderate   | Sponsor decision               | Optional scenario                    |
| A39 | Payer and claims data are excluded from the base case                                         | Scope          | Future/optional extension                                        | Avoids additional interfaces and agreements                       | High       | Scope decision                 | Exclusion/optional module            |
| A40 | Sustainability planning is required even if operations terminate after the pilot              | Sustainability | Pilot is intended to inform scaling                              | Adds financial and governance analysis                            | High       | Closeout requirements          | Fixed assumption                     |
| A41 | Recurrent operations after the pilot are not sponsor commitments unless separately authorized | Funding        | No transition funding is described                               | Prevents unsupported recurring-cost assumption                    | Moderate   | Sponsor decision               | Explicit boundary                    |
| A42 | Participant procurement and agreements may consume 3–6 months                                 | Schedule       | Major known pilot risk                                           | Could dominate critical path and PM cost                          | Moderate   | Procurement strategy           | Low/base/high range                  |
| A43 | Quality thresholds will be established during design rather than assumed now                  | Evaluation     | Brief specifies dimensions, not thresholds                       | Necessary before acceptance testing                               | High       | Standards and program decision | Unresolved decision                  |
| A44 | A common provenance and transformation model will be required                                 | Technical      | Cross-consumer trust requires it                                 | Adds design and implementation effort                             | High       | Architecture                   | Fixed assumption                     |
| A45 | Consumer-specific output packaging will be required even from a common dataset                | Technical      | CDC, HRSA, and quality uses differ                               | Creates variable downstream cost                                  | High       | Consumer specifications        | Per-output variable                  |

---

# 10. Prioritized material questions

## Critical before estimating

| Question                                                                                | Why It Matters                                                            | Provisional Assumption                                                              |
| --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| How many intermediaries will participate, and of what types?                            | Largest driver of duplicated implementation and governance cost           | Base case: 3 intermediaries                                                         |
| How many STLT jurisdictions, provider networks, and individual facilities are expected? | Determines onboarding, interface, subaward, legal, and evaluation scale   | Base: 3 STLTs, 6 provider networks                                                  |
| What is the definitive project duration and required live-operation period?             | Drives PM, support, hosting, and evaluation                               | 15 months total; 4 months live operations                                           |
| Which chronic domain and measures will be mandatory?                                    | Determines data requirements, SME mix, licensing, and validation          | One hypertension or diabetes domain; 1–2 measures                                   |
| Is the optional referral extension part of the funded pilot?                            | Could add an independent workstream and new organization types            | Exclude from base; model separately                                                 |
| Will a new shared pilot hub be built, or will each intermediary host all processing?    | A central platform could be the largest fixed technical cost              | Existing intermediary hosting in base case                                          |
| What existing FHIR endpoints and source connections are actually available?             | Determines whether the project is configuration or greenfield integration | At least 70% of source pathways already connected                                   |
| Who will receive direct funding—STLTs, intermediaries, HCCNs, providers, vendors, CBOs? | Required to distinguish sponsor cost from total economic cost             | Fund STLTs/intermediaries; track provider effort in kind                            |
| What data-access level will each consumer receive?                                      | Changes privacy, security, de-identification, and architecture            | STLTs may receive line-level; national uses primarily de-identified or aggregate    |
| Are HRSA and NCQA formal pilot participants or advisory stakeholders?                   | Changes measure licensing, validation, deliverables, and governance       | Advisory in base case                                                               |
| What security framework and approval process applies?                                   | Security review can materially affect schedule and cost                   | Intermediary controls plus participant review; no CDC ATO assumed unless CDC-hosted |
| What are the required acceptance thresholds?                                            | Necessary to determine testing and remediation scope                      | Defined during design; cap at two remediation cycles                                |

## Important but can be parameterized

| Question                                                                             | Why It Matters                                                   | Provisional Assumption                                      |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------- | ----------------------------------------------------------- |
| How many EHR products and endpoint configurations are involved?                      | More products increase variability and vendor costs              | 4 distinct vendor configurations                            |
| What is the refresh cadence?                                                         | Drives operations and cloud costs                                | Weekly                                                      |
| What historical lookback is required?                                                | Drives extraction size and data-quality work                     | Two years                                                   |
| How many consumer products are required?                                             | Each output requires mapping, security, and validation           | Three outputs                                               |
| How many data elements and conformance rules will be mandatory?                      | Drives specification, testing, and remediation                   | 40–60 elements; 75–125 rules                                |
| Will identity matching use existing MPI services or require new linkage development? | New linkage would materially increase technical and privacy cost | Existing MPI or patient-panel logic                         |
| How many legal agreements are expected, and can common templates be used?            | Legal labor and schedule are highly sensitive to agreement count | Central templates plus local execution                      |
| What level of technical assistance will participants need?                           | IC cost varies substantially by maturity                         | Tiered light/moderate/intensive model                       |
| Are dashboards required, or are files/reports sufficient?                            | Dashboard development and operation can be material              | One reusable trust dashboard; consumer outputs may be files |
| Will cost and burden reduction be formally measured?                                 | Requires time tracking and baseline data collection              | Yes, directional full-economic-cost assessment              |
| Is travel expected?                                                                  | Adds direct cost and staff time                                  | Mostly virtual; one site visit per intermediary             |

## Useful refinements

* Which terminology service and validator will be used?
* Is MeasureReport required as an output?
* Will CMS-aligned measures be formally validated?
* Which quality thresholds are universal versus use-case-specific?
* Will the pilot include performance or load testing?
* Will disaster recovery be tested?
* What publication and dissemination products are required?
* Are 508 accessibility, records-management, or federal publication reviews required?
* Will implementation artifacts be publicly released or limited to partners?
* How will changes to US Core, QI-Core, and value sets be managed during the project?

## Low-impact questions

* Exact meeting cadence
* Branding of the implementation playbook
* Whether training is synchronous or asynchronous
* Whether stakeholder interviews are individual or group-based
* Exact dashboard visualization platform, assuming no material license difference

---

# 11. Project-specific research taxonomy

## A. Core project concepts

* Chronic care cascade surveillance
* Electronic clinical data for chronic disease surveillance
* Collect once, use many
* Dual-use clinical dataset
* Multi-consumer data reuse
* HIE/HDU-enabled public health surveillance
* HCCN and FQHC data aggregation
* Bulk FHIR clinical-data export
* FHIR-based chronic disease reporting
* Digital quality measurement
* Hypertension control
* Glycemic status and diabetes control
* Chronic disease data-quality scoring
* Fit-for-use clinical data
* Data completeness and provenance
* Intermediary trust layer
* Public health data-product provisioning
* Provider data-quality feedback
* STLT surveillance modernization
* Cross-agency reporting burden reduction
* Closed-loop chronic intervention referral
* Gravity-aligned referral and SDOH exchange
* Multi-jurisdiction pilot evaluation
* Intermediary readiness assessment

## B. Named entities and formal terminology

| Term      | Expansion or Meaning                                                                                                             |
| --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| PHIG B4   | Public Health Infrastructure Grant, Component B, Strategy 4                                                                      |
| CDC       | Centers for Disease Control and Prevention                                                                                       |
| OPHDST    | Office of Public Health Data, Surveillance, and Technology                                                                       |
| STLT      | State, tribal, local, and territorial                                                                                            |
| PHA       | Public health agency                                                                                                             |
| HIE       | Health information exchange                                                                                                      |
| HDU       | Health data utility                                                                                                              |
| HCCN      | Health Center Controlled Network                                                                                                 |
| FQHC      | Federally Qualified Health Center                                                                                                |
| HRSA      | Health Resources and Services Administration                                                                                     |
| NCQA      | National Committee for Quality Assurance                                                                                         |
| CMS       | Centers for Medicare & Medicaid Services                                                                                         |
| CSTE      | Council of State and Territorial Epidemiologists                                                                                 |
| NACDD     | National Association of Chronic Disease Directors                                                                                |
| MENDS     | Multi-State EHR-Based Network for Disease Surveillance                                                                           |
| USCDI     | United States Core Data for Interoperability                                                                                     |
| US Core   | HL7 FHIR US Core Implementation Guide                                                                                            |
| QI-Core   | Quality Improvement Core Implementation Guide                                                                                    |
| CQL       | Clinical Quality Language                                                                                                        |
| FHIR      | Fast Healthcare Interoperability Resources                                                                                       |
| Bulk FHIR | HL7 FHIR Bulk Data Access                                                                                                        |
| Gravity   | Gravity Project standards for SDOH data and referrals                                                                            |
| PIQI      | Public-health-oriented interoperability or data-quality framework referenced in adjacent pilot work; exact use must be validated |
| TEFCA     | Trusted Exchange Framework and Common Agreement                                                                                  |
| DUA       | Data use agreement                                                                                                               |
| DSA       | Data sharing agreement                                                                                                           |
| RBAC      | Role-based access control                                                                                                        |
| MPI       | Master patient index                                                                                                             |
| dQM       | Digital quality measure                                                                                                          |
| EHR       | Electronic health record                                                                                                         |
| CBO       | Community-based organization                                                                                                     |
| SDOH      | Social determinants of health                                                                                                    |

## C. Synonyms and adjacent terminology

| Pilot Term                  | Synonyms or Related Terms                                                                                                  | Notes on Usage                                                                         |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Chronic care cascade        | Continuum of care, care cascade, diagnosis-to-control cascade, chronic disease management pathway                          | Academic and program literature may use different cascade definitions                  |
| Chronic surveillance        | Chronic disease surveillance, population health surveillance, EHR-based surveillance, noncommunicable disease surveillance | “Population health” may retrieve payer or provider analytics rather than public health |
| Dual-use dataset            | Multi-purpose dataset, reusable data asset, common data layer, shared clinical dataset                                     | Useful in vendor and federal strategy sources                                          |
| Collect once, use many      | Capture once, use many; collect once, apply to many; data once, multiple uses                                              | Search all variants                                                                    |
| HDU                         | Health data utility, state health data utility, HIE-to-HDU transformation                                                  | Some sources use HDU loosely                                                           |
| HIE intermediary            | Health information network, clinical data exchange, statewide HIE, regional health information organization                | Older procurements may use RHIO                                                        |
| HCCN                        | Health Center Controlled Network, FQHC network, safety-net data network                                                    | HRSA records often use HCCN                                                            |
| Bulk FHIR                   | FHIR Bulk Data, `$export`, population-level FHIR, Group export, NDJSON export                                              | Technical solicitations may cite “Flat FHIR”                                           |
| Digital quality measurement | dQM, digital HEDIS, electronic clinical quality measure, eCQM, FHIR-based quality reporting                                | Separate FHIR-native from legacy QRDA searches                                         |
| Data trust layer            | Data-quality framework, fit-for-use assessment, data validation layer, conformance and completeness scoring                | “Trust framework” can also retrieve governance-only documents                          |
| Completeness scoring        | Data-quality scorecard, source data quality, field completeness, profile conformance                                       | Useful for HIE and registry analogues                                                  |
| Identity resolution         | Patient matching, record linkage, MPI, entity resolution, privacy-preserving record linkage                                | Add health/public health qualifiers                                                    |
| Data product                | Curated dataset, analytic dataset, surveillance extract, derived indicator, reusable output                                | Common in data-platform procurements                                                   |
| Provider feedback           | Data-quality feedback loop, source-facing scorecard, submitter validation report                                           | Analogous to registry and quality-reporting feedback                                   |
| Closed-loop referral        | Referral loop closure, social care referral, community resource referral, bidirectional referral                           | Search with Gravity, 211, Unite Us, findhelp                                           |
| Technical assistance        | Implementation support, onboarding assistance, capacity building, practice facilitation                                    | Grant records may not use “technical assistance”                                       |
| Public health utility       | Decision utility, actionability, surveillance usefulness, programmatic value                                               | Relevant to evaluation studies                                                         |
| Reporting burden reduction  | Administrative burden, duplicate reporting, interface consolidation, manual abstraction reduction                          | Useful for benefit and cost-driver evidence                                            |
| Intermediary readiness      | Capability assessment, maturity model, onboarding readiness, participation criteria                                        | Useful for IC and HIE studies                                                          |

## D. Analogue project families

### Whole-project analogues

1. Multi-state EHR-based chronic disease surveillance networks
2. HIE/HDU-enabled chronic disease surveillance pilots
3. Statewide clinical-data repositories supporting public health and quality measurement
4. FQHC/HCCN clinical-data aggregation and reporting modernization
5. Collect-once/multi-use clinical-data pilots
6. FHIR-based digital-quality and public-health reuse demonstrations
7. PHIG or CDC-funded intermediary pilots
8. Population-health infrastructure combining public health, Medicaid, and provider uses
9. Multi-jurisdiction public health data modernization cooperative agreements
10. HIE-based hypertension or diabetes surveillance programs

### Component-level analogues

1. Bulk FHIR implementation and onboarding
2. HIE interface development and maintenance
3. FHIR conformance-testing programs
4. Clinical-data quality scorecards
5. Source-facing remediation programs
6. QI-Core/CQL digital-measure implementation
7. MPI and record-linkage implementations
8. De-identification and privacy-preserving linkage
9. Public health DUA/DSA development
10. HIE-to-public-health data-product provisioning
11. HCCN/FQHC reporting and analytics programs
12. Technical-assistance programs for STLT interoperability
13. Closed-loop referral implementations
14. Public health pilot evaluations
15. Cloud-hosted clinical-data platforms
16. Participant readiness assessments
17. Provider incentive or subaward programs
18. Cross-agency governance initiatives

## E. Cost-component search categories

* Federal pilot program management
* PHIG subaward administration
* STLT participant staffing
* HIE/HDU implementation and configuration
* HCCN/FQHC onboarding
* Bulk FHIR endpoint enablement
* EHR vendor professional services
* FHIR mapping and profile development
* CQL and digital-measure implementation
* Clinical terminology and value-set services
* Conformance and data-quality tooling
* MPI and record linkage
* De-identification
* DUA/DSA and public health legal analysis
* Security architecture and assessment
* Cloud hosting and data storage
* Consumer-specific data products
* Source-remediation support
* Technical assistance
* Training and change management
* Help desk and recurring operations
* Evaluation and economic-cost measurement
* Participant stipends and subawards
* Site visits and travel
* Sustainability and scale planning
* Optional closed-loop referral implementation

## F. Recommended search strings

### 1. Whole-project analogue searches

1. `"chronic disease surveillance" HIE implementation cost`
2. `"EHR-based chronic disease surveillance" grant budget`
3. `"health data utility" chronic disease pilot contract`
4. `"health information exchange" hypertension surveillance project cost`
5. `"health information exchange" diabetes surveillance cooperative agreement`
6. `"collect once use many" healthcare data pilot budget`
7. `"clinical data" public health surveillance quality measurement pilot`
8. `"multi-state EHR-based network" chronic disease funding`
9. `"HDU" "public health surveillance" award`
10. `"population health" HIE public health quality measurement contract`

### 2. Organization-specific searches

11. `CDC chronic disease HIE cooperative agreement budget`
12. `PHIG B4 implementation center subaward chronic disease`
13. `HRSA HCCN FHIR implementation award budget`
14. `FQHC network clinical data aggregation contract cost`
15. `state health department HIE chronic surveillance RFP`
16. `Medicaid HIE hypertension quality reporting contract`
17. `health data utility provider onboarding pricing`
18. `HIE public health data quality scorecard statement of work`

### 3. Technical-component searches

19. `"Bulk FHIR" implementation contract cost`
20. `"FHIR Bulk Data" health information exchange RFP`
21. `"QI-Core" CQL implementation pricing`
22. `"digital quality measure" FHIR implementation award`
23. `"FHIR conformance testing" healthcare contract`
24. `"clinical data quality" HIE dashboard implementation`
25. `"master patient index" HIE implementation cost`
26. `"privacy preserving record linkage" public health contract`
27. `"FHIR terminology service" government contract pricing`
28. `"data de-identification" health information exchange contract`

### 4. Cost and procurement searches

29. `site:.gov HIE "statement of work" FHIR public health`
30. `site:.gov "health data utility" contract award`
31. `site:.gov chronic disease surveillance RFP EHR data`
32. `site:.gov HCCN data analytics grant budget`
33. `site:.us "health information exchange" public health contract`
34. `site:sam.gov FHIR public health surveillance solicitation`
35. `site:usaspending.gov health information exchange CDC`
36. `"interoperability implementation" "labor hours" FHIR`
37. `"HIE interface" implementation fee public contract`
38. `"provider onboarding" health information exchange cost`

### 5. Evaluation and operations searches

39. `"public health data modernization" evaluation contract`
40. `"EHR surveillance" implementation evaluation cost`
41. `"HIE" operating cost per interface`
42. `"health information exchange" maintenance cost public health`
43. `"data quality remediation" EHR implementation study`
44. `"technical assistance" public health interoperability cooperative agreement`
45. `"chronic disease surveillance" implementation report HIE`
46. `"digital quality measurement" pilot evaluation report`
47. `"closed loop referral" implementation cost health system`
48. `"collect once" reporting burden reduction evaluation healthcare`

## G. Source-targeting strategy

| Source Type                                         | Likely Cost Information                                                                 |
| --------------------------------------------------- | --------------------------------------------------------------------------------------- |
| USAspending.gov                                     | Federal award totals, recipients, periods of performance, modifications                 |
| SAM.gov                                             | Statements of work, labor categories, deliverables, contract type, evaluation structure |
| CDC grant and cooperative-agreement notices         | Sponsor funding, recipient responsibilities, allowable costs                            |
| HRSA grant databases and HCCN notices               | FQHC/HCCN aggregation, TA, analytics, and network costs                                 |
| State procurement portals                           | HIE/HDU implementation, interface, hosting, and support pricing                         |
| State legislative budgets                           | Public appropriations, matching funds, sustainability costs                             |
| Public HIE/HDU board materials                      | Operating budgets, vendor contracts, staffing, cost per connection                      |
| Medicaid agency contracts                           | HIE connectivity, quality reporting, and provider incentive costs                       |
| APD and Medicaid enterprise planning documents      | Integration, certification, and operations cost components                              |
| Cooperative-agreement progress reports              | Staffing, participant support, implementation barriers                                  |
| Inspector general and audit reports                 | Cost overruns, unsupported assumptions, operating-cost weaknesses                       |
| Federal and state rate cards                        | Labor rates and vendor service categories for later stages                              |
| Vendor public contracts                             | License, implementation, maintenance, interface, and transaction fees                   |
| Peer-reviewed implementation studies                | Labor intensity, timelines, workflow burden, and qualitative cost drivers               |
| Conference presentations and implementation reports | Participant counts, architecture, staffing, and lessons                                 |
| Foundation grants                                   | Pilot-scale project values and evaluation costs                                         |
| Public university subaward records                  | Evaluation and technical-assistance pricing                                             |
| CSTE and NACDD awards                               | STLT engagement, learning-community, and chronic surveillance costs                     |
| HL7 and Connectathon records                        | Testing effort and participant resource needs, usually without full project costs       |
| Federal cloud pricing calculators and schedules     | Infrastructure benchmarks after architecture and volumes are defined                    |

## H. Negative and exclusion terms

| Ambiguous Search Term | Likely Irrelevant Results                        | Recommended Qualifier or Exclusion                                                                           |
| --------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| Chronic care cascade  | HIV care cascade literature                      | Add `hypertension OR diabetes`; exclude `HIV` where needed                                                   |
| HDU                   | Hardware distribution unit, high dependency unit | Add `"health data utility"` and `healthcare`                                                                 |
| HIE cost              | Health insurance exchange costs                  | Add `"health information exchange"`; exclude `"insurance marketplace"`                                       |
| FHIR bulk             | General programming tutorials                    | Add `contract`, `implementation`, `health system`, or `HIE`                                                  |
| Quality measure       | Non-healthcare quality management                | Add `clinical`, `NCQA`, `CQL`, or `FHIR`                                                                     |
| Data utility          | Utility-company or general data-product results  | Add `health`, `public health`, or `clinical`                                                                 |
| Trust layer           | Blockchain and zero-trust marketing              | Add `clinical data quality`, `FHIR`, or `HIE`; exclude `crypto`                                              |
| Cascade model         | Statistical or machine-learning cascade models   | Add `chronic disease`, `care`, or `surveillance`                                                             |
| Referral platform     | Recruitment or affiliate referral software       | Add `healthcare`, `social care`, or `closed loop`                                                            |
| MPI                   | Message Passing Interface computing results      | Add `"master patient index"`                                                                                 |
| CQL                   | Database query language or unrelated acronyms    | Add `"Clinical Quality Language"`                                                                            |
| HCCN                  | Unrelated organization acronyms                  | Add `HRSA` or `"Health Center Controlled Network"`                                                           |
| Public health data    | COVID-only emergency procurements                | Exclude `COVID` when seeking durable chronic analogues, but retain selected COVID results for platform costs |
| Surveillance          | Security-camera and law-enforcement systems      | Add `health`, `disease`, `EHR`; exclude `video`                                                              |

## I. Priority research sequence

1. **Search for whole-project public award values** involving HIE/HDU chronic surveillance, EHR-based surveillance, HCCNs, or multi-purpose clinical-data platforms.
2. **Search state procurements and public HIE contracts** for implementation, connection, hosting, and support pricing.
3. **Search HRSA/HCCN and FQHC projects** for participant-level aggregation, onboarding, and reporting costs.
4. **Search Bulk FHIR and digital-quality implementations** for technical component and staffing benchmarks.
5. **Search data-quality, MPI, de-identification, and conformance components** where whole-project analogues do not isolate costs.
6. **Search technical-assistance and participant-support awards** to estimate IC and STLT support intensity.
7. **Search evaluation contracts and implementation studies** for baseline collection, qualitative research, and final reporting.
8. **Search recurring HIE/HDU operating budgets** for hosting, support, maintenance, and interface costs.
9. **Search closed-loop referral projects separately** only if the optional extension is activated.
10. **Capture cost drivers even when dollar figures are unavailable**, including participant counts, timelines, interfaces, staffing, and remediation cycles.

---

# 12. Initial observations about the likely cost structure

## Largest fixed costs

The largest fixed costs are likely to be:

1. Central pilot design, program management, and evaluation methodology
2. Minimum dataset, FHIR mapping, terminology, measure logic, and conformance-rule development
3. Governance, legal templates, security architecture, and common operating policies
4. Trust-layer design and reusable validation tooling
5. Implementation playbook and scale-readiness products
6. Any decision to build a shared national pilot platform rather than use intermediary-hosted capabilities

## Largest variable costs

The largest variable costs are likely to be:

1. Intermediary implementation and configuration
2. Provider and HCCN onboarding
3. Endpoint and interface work
4. Source-specific mapping and data remediation
5. Legal and security review by each participant
6. Technical assistance
7. Consumer-specific output configuration
8. Recurring operations and support
9. Optional referral implementation

## Costs most sensitive to scale

* Number of intermediaries
* Number of source systems and EHR products
* Number of provider organizations and facilities
* Number of legal agreements
* Number of consumer outputs
* Number of chronic domains and measures
* Number of quality-remediation cycles
* Number of live-operation months

The number of patients or records may affect cloud costs, but organizational and interface complexity will probably be more important than raw data volume at pilot scale.

## Costs most sensitive to schedule

* Program management
* Participant staffing
* Legal and governance facilitation
* Cloud and software subscriptions
* Operations and help desk
* Evaluation staff
* Vendor retainers or minimum commitments

Delays in agreements, participant selection, or endpoint access could increase total cost without increasing delivered scope.

## Costs most likely to be underestimated

* STLT legal, privacy, informatics, and program SME effort
* Provider and FQHC application-analyst time
* EHR-vendor troubleshooting
* Source-data remediation
* Identity matching and deduplication
* Consumer-specific de-identification
* Baseline reconstruction for evaluation
* Documentation and approval effort
* Support after initial go-live
* Sustainability planning
* Procurement and subaward administration

## Costs most likely to be contributed in kind

* CDC and HRSA SME participation
* STLT program and legal review
* Provider clinical champions
* HIE/HDU governance participation
* EHR-vendor account-management support
* NCQA advisory participation, if treated as collaboration
* CSTE and NACDD subject-matter input
* MENDS consultation
* Executive and steering-committee time

These costs should be recorded separately from sponsor expenditures so that the later model captures **total economic cost**, not merely the pilot budget.

## Costs most difficult to benchmark publicly

* Participant-specific data remediation
* HIE/HDU internal configuration effort
* EHR-vendor enablement charges
* Legal and privacy effort distributed across organizations
* In-kind public health labor
* Identity-resolution configuration
* Consumer-specific data-product development
* Measure reconciliation and discrepancy analysis
* Operational support for a small pilot
* Cost of advancing from pilot to routine production

Public records are more likely to disclose total awards, hosting contracts, interface charges, and broad labor categories than these internal effort components.

## Overall cost-shape hypothesis

The pilot will likely have a **high initial fixed design and governance layer**, followed by **step-fixed implementation costs for each intermediary**, and then **variable onboarding and remediation costs for each source organization or endpoint**. Recurring pilot operations may be smaller than implementation costs but remain highly schedule-sensitive.

The most defensible future model should therefore be organized around:

[
\text{Total Economic Cost}
==========================

\text{Central Fixed Cost}
+
(\text{Intermediary Count} \times \text{Intermediary Cost})
+
(\text{Source Count} \times \text{Onboarding Cost})
+
(\text{Interface Count} \times \text{Integration Cost})
+
(\text{Consumer Outputs} \times \text{Product Cost})
+
\text{Recurring Operations}
+
\text{Evaluation}
+
\text{In-Kind Labor}
+
\text{Contingency}
]

The base model should separately display:

* Sponsor-paid costs
* Subaward costs
* Vendor and contractor costs
* Participant-reimbursed costs
* Participant in-kind costs
* One-time implementation costs
* Recurring operational costs
* Optional extension costs

This analysis applies the supplied Stage 1 instructions  to the Chronic Care Cascade technical brief. 

---

# Prompt

I've attached an updated assumptions table (see "Updated Assumptions.docx") that replaces the table at the beginning of 10 in the response to STAGE 1. Run the STAGE 2 PROMPT.

---

# Response

See "Cost Model Benchmarks for the Chronic Care Cascade Pilot v2.docx".

# Prompt 

This research is a great help. We're targeting $3M per pilot and 3 to 4 pilots. Where can we adjust to keep the pilot cost closer to our target?

The $3 million target is achievable, but only if each pilot is structured as a **thin-slice implementation on a shared program backbone**. The Stage 2 research effectively priced each pilot as though it independently carried much of the program infrastructure. That is not the right allocation model for a portfolio of three or four related HDU pilots.

Your updated assumptions already reduce the largest cost driver from three intermediaries to **one intermediary, one STLT jurisdiction, six provider networks, 12 months, and four months of live operations**.  The remaining adjustment is to separate:

1. **Portfolio-level capabilities built once**
2. **Intermediary capabilities reused across pilots**
3. **Use-case-specific work charged to each pilot**

## Recommended portfolio model

### Build once across all pilots

The following should not be independently funded at full cost in every pilot:

* Program governance and PMO
* Common participant-readiness framework
* Model DUA/DSA language
* Common security and privacy requirements
* Shared FHIR and USCDI conformance framework
* Common provenance and audit model
* Trust-scorecard platform or framework
* Common validation tooling
* Shared technical-assistance methods
* Evaluation framework and data-collection instruments
* Common implementation-playbook structure
* Portfolio-level stakeholder engagement and dissemination

These are largely the same across chronic disease, maternal-child linkage, cancer, asthma, opioids, or other “collect once, use many” pilots. The Wave 2 framework already anticipates common standards, intermediary, governance, privacy, security, and data-quality pillars across the use cases. 

A reasonable portfolio structure would be:

| Funding Layer                | Three-Pilot Portfolio | Four-Pilot Portfolio |
| ---------------------------- | --------------------: | -------------------: |
| Shared program backbone      |           $2.5M–$3.5M |          $3.0M–$4.0M |
| Pilot implementation funding |      $2.2M–$2.6M each |     $2.0M–$2.4M each |
| Portfolio contingency        |           $0.5M–$1.0M |        $0.75M–$1.25M |
| Approximate total            |          $9.6M–$12.3M |      $11.75M–$14.85M |

If the stated budget is a firm **$3 million per pilot**, shared costs can be allocated pro rata while still keeping the accounting at approximately $3 million each.

---

# Where to reduce the Chronic Care Cascade pilot

## 1. Treat the intermediary as an existing platform, not an implementation project

The most important scope boundary should be:

> The pilot funds configuration and incremental capability required for the selected use case; it does not fund construction, replacement, or major modernization of the intermediary platform.

Require the selected HIE/HDU or HCCN to already possess:

* Working provider connectivity
* Patient matching or panel attribution
* Secure data storage and processing
* API or Bulk FHIR capability
* Existing IAM and audit logging
* Production operations and support processes
* A viable analytics or data-product environment

The pilot should pay for the **delta**, such as:

* Adding the selected chronic dataset
* Configuring validation rules
* Producing the pilot data product
* Supporting limited testing and remediation
* Generating the selected measures and outputs

This could reduce the effective intermediary allocation from the Stage 2 proxy of $1.5M–$3.5M to approximately **$600,000–$1.0 million**.

## 2. Require all six provider networks to be substantially connected already

Your updated assumption says at least 50% of source pathways are already connected.  To stay near $3 million, I would strengthen that requirement:

* All six provider networks must already send relevant data to the intermediary.
* At least four must have usable FHIR or structured clinical-data access.
* No more than two may require material endpoint enablement.
* No net-new EHR product development.
* No custom interface for an individual practice or facility.
* Vendor work must be limited to configuration, testing, and correction of documented defects.

This changes the unit of participation from six separate integrations to **one intermediary dataset assembled from six existing sources**.

## 3. Select one condition domain and one primary measure

The brief currently allows hypertension and/or glycemic status, with possible extensions such as obesity, BMI, asthma, or SDOH.  For a $3 million pilot:

* Choose **hypertension or diabetes**, not both.
* Select one primary cascade or control measure.
* Permit one secondary indicator only when it uses essentially the same data elements.
* Do not allow site-selected extension domains in the base pilot.
* Defer asthma, obesity, nutrition, SDOH, and referral signals to later phases.

A strong thin slice would be:

> Hypertension control using demographics, encounter context, diagnosis, blood-pressure observations, medication context, organization, geography, provenance, and timestamps.

This limits:

* Dataset specification work
* Value-set work
* CQL or measure development
* Testing cases
* Data-quality rules
* Clinical SME involvement
* Source remediation

## 4. Limit the common dataset to approximately 15–25 elements

The CDC–NCQA pilot ideation work proposed selecting a small data-element set before selecting the use cases in order to prevent measure sprawl.  Apply that approach directly.

A minimum chronic dataset should contain only information necessary to:

1. Define the cohort
2. Calculate the selected indicator
3. Stratify the result
4. Attribute the source
5. Assess timeliness and completeness

Do not include optional data merely because it may be useful later.

## 5. Demonstrate two consumers, not three fully operational outputs

The brief currently contemplates CDC surveillance, HRSA-aligned reporting, and digital quality measurement from the same dataset.  The $3 million version should require:

* One operational STLT/CDC surveillance product
* One representative quality or HRSA-aligned reuse demonstration

The second consumer does not need a full production implementation. It may be:

* A generated reporting artifact
* A measure-execution result
* A validated transformation
* A controlled demonstration using the same data product

This still proves “collect once, use many” without funding three production delivery paths.

## 6. Use files or existing analytics tools instead of building new dashboards

Avoid making custom dashboards a required deliverable. A dashboard can easily become a separate product-development effort.

Prefer:

* Existing intermediary analytics tooling
* Existing STLT BI tools
* Standard exports
* Measure reports
* Validation reports
* Simple reference visualizations

The required output should be the **conformant, reusable data product**, not a polished bespoke user interface.

## 7. Make the trust layer minimum viable

The full trust concept could become expansive. For this pilot, limit it to:

* FHIR/profile conformance
* Required-field completeness
* Timeliness
* Source provenance
* Transformation traceability
* A small number of clinical plausibility checks
* Auditable access

Defer:

* Sophisticated composite scoring
* Predictive quality models
* AI-based anomaly detection
* Advanced drift detection
* Extensive provider benchmarking
* Public comparative scorecards
* New enterprise terminology services

The initial scorecard can be a standardized report generated by existing tools rather than a newly developed application.

## 8. Cap remediation explicitly

The updated assumptions already cap the pilot at two remediation cycles.  Retain that limit and clarify that:

* The pilot identifies all material defects.
* It prioritizes a small number of defects that prevent the core use case.
* Each source receives no more than two funded remediation cycles.
* Unresolved defects are documented as readiness findings.
* The pilot is not responsible for correcting underlying EHR documentation or product deficiencies.

This protects the pilot from becoming a broad data-cleanup program.

## 9. Keep HRSA and NCQA advisory

The updated assumptions treat HRSA and NCQA as advisory rather than funded operational participants.  That is appropriate.

They should:

* Review requirements
* Validate alignment
* Participate at defined design and review points
* Assess the resulting artifact

They should not require:

* Separate interfaces
* Separate production environments
* Dedicated operational support
* Independent governance structures
* Multiple rounds of custom measure development

## 10. Exclude all optional extensions from the base award

The following should be explicitly outside the $3 million base:

* Closed-loop referral
* CBO connectivity
* Gravity implementation
* Claims or payer interfaces
* Pharmacy dispensing feeds
* TEFCA retrieval
* New MPI implementation
* Privacy-preserving record linkage product development
* AI analytics
* Event-driven subscriptions
* Environmental data linkage
* Additional chronic conditions
* Custom dashboards
* New national data platform
* Production transition beyond the pilot period

The Chronic Care Cascade brief already treats referrals, claims, event-driven pipelines, and TEFCA-enabled patterns as optional or future capabilities. 

---

# Recommended $3 million pilot budget structure

| Workstream                                |         Target | Scope Boundary                                                               |
| ----------------------------------------- | -------------: | ---------------------------------------------------------------------------- |
| Pilot management and governance           |       $300,000 | Pilot-specific management only; portfolio PMO funded centrally               |
| STLT subaward and participation           |       $350,000 | Surveillance requirements, governance, validation, action-utility assessment |
| Intermediary configuration                |       $800,000 | Incremental configuration on existing infrastructure                         |
| Provider-network onboarding and support   |       $450,000 | Six existing network connections; average $75,000 each                       |
| Standards, mapping, and measure package   |       $250,000 | One condition, one primary measure, minimal dataset                          |
| Validation and trust-layer configuration  |       $250,000 | Existing tooling plus limited rule development                               |
| Testing and two remediation cycles        |       $250,000 | Capped testing and correction                                                |
| Four months of pilot operations           |       $200,000 | Existing operational environment; incremental support only                   |
| Pilot-specific evaluation                 |       $100,000 | Portfolio evaluator performs common methods centrally                        |
| Implementation documentation and closeout |        $50,000 | Pilot-specific inputs to common playbook                                     |
| Contingency                               |       $200,000 | Approximately 7%                                                             |
| **Total**                                 | **$3,000,000** |                                                                              |

This allocation assumes the portfolio separately funds:

* Common evaluation methodology
* Common DUA and governance templates
* Shared conformance tools
* Shared trust-framework design
* Portfolio PMO
* Common technical-assistance materials
* Cross-pilot synthesis
* Portfolio-scale dissemination

## Economic cost versus sponsor budget

The $3 million figure should be presented as the **sponsor-funded pilot budget**, not necessarily the full economic cost. Providers, the STLT, CDC SMEs, HRSA, NCQA, and intermediary leadership will probably contribute uncompensated or internally funded effort.

I would therefore track two numbers:

* **Sponsor-funded pilot cost:** approximately $3.0 million
* **Total economic cost:** perhaps $3.5M–$4.2M after participant in-kind effort

That distinction keeps the budget target credible without implying that all participant work is free.

---

# Portfolio efficiencies across three or four pilots

The greatest savings occur when the pilots use the same:

* One or two intermediaries
* Basic legal framework
* Security and access model
* FHIR intake pattern
* Validation tooling
* Trust-report format
* Provenance model
* Evaluation framework
* Technical-assistance team
* Program management structure
* Testing cadence
* Implementation-playbook template

A particularly efficient design would select **one intermediary capable of supporting two related pilots**. For example:

* Chronic care cascade and childhood asthma could reuse clinical and encounter data.
* Cancer and eCR modernization could reuse reporting, validation, and routing capabilities.
* Opioid surveillance and syndromic surveillance could reuse event-oriented encounter data.

The asthma concept, for example, is already framed as a limited event-centered dataset and a 90–120-day demonstration, which is much more compatible with a $3 million ceiling than a broad multi-domain platform build. 

## Recommended non-negotiables

To maintain the target, I would put these directly into participant selection and award language:

1. One intermediary and one STLT per pilot.
2. One condition domain.
3. One primary measure or analytic workflow.
4. At least 50% existing connectivity, preferably substantially more.
5. No more than two materially new endpoint configurations.
6. Existing hosting, IAM, MPI, audit, and operational support.
7. Two downstream uses, only one of which must be fully operational.
8. No custom dashboard requirement.
9. No more than two remediation cycles.
10. Four months of live operations.
11. Optional extensions separately funded.
12. Portfolio-level assets developed once and reused.

The main principle is: **do not shrink every activity evenly.** Preserve the core proof—one acquisition, one trust process, multiple uses—and remove breadth, custom development, and duplicate infrastructure. That produces a credible pilot rather than an underfunded implementation program.

---

# Prompt

Let's proceed with these assumptions: 
- One intermediary and one STLT per pilot. 
- One condition domain per pilot. 
- One primary measure or analytic workflow. 
- At least 75% existing connectivity. 
- No more than two materially new endpoint configurations. 
- Existing hosting, IAM, MPI, audit, and operational support. 
- Two downstream uses, only one of which must be fully operational. 
- No custom dashboard requirement. 
- No more than two remediation cycles. 
- Four months of live operations. 
- Optional extensions separately funded. 
- Portfolio-level assets developed once and reused. 

Using those assumptions, please run the STAGE 3 PROMPT.

The WBS below applies the Stage 3 instructions  to the Chronic Care Cascade pilot, using the original technical brief as the scope baseline  and replacing the earlier scaling assumptions with the decisions in your latest message and updated assumptions register. 

# Response

# 1. WBS design summary

## Organizing logic

The WBS is organized first by the organization that performs or owns the work, then by lifecycle phase, work package, and estimable activity.

The model distinguishes:

* **Portfolio-shared work:** developed once across three or four pilots.
* **Pilot-specific shared work:** supports all participants within this pilot.
* **Organization-specific work:** performed by the STLT, intermediary, provider networks, vendors, evaluator, or sponsor.
* **In-kind work:** necessary participant effort that may not be funded.
* **Optional work:** excluded from the $3 million base pilot and estimated separately.

## Scope interpretation used

The base pilot assumes:

* One intermediary
* One STLT jurisdiction
* Six provider networks
* One chronic condition domain
* One primary measure or analytic workflow
* At least 75% existing connectivity
* No more than two materially new endpoint configurations
* Existing hosting, IAM, MPI, audit, and operational support
* Two downstream uses, only one fully operational
* No custom dashboard development
* Two remediation cycles maximum
* Four months of live operations
* Optional extensions separately funded
* Portfolio-level assets developed once and reused

The base WBS therefore treats the pilot as **configuration, validation, controlled onboarding, and evaluation of an existing intermediary environment**, not as construction of a new HDU platform.

## Organization types represented

1. Federal sponsor/program office
2. Portfolio PMO/prime contractor
3. STLT public health agency
4. HIE/HDU intermediary
5. Provider networks
6. EHR or health IT vendors
7. Downstream consumer/program
8. Independent evaluator
9. Portfolio-level shared-services team
10. Cloud/platform providers, primarily through existing intermediary services

## Sponsor cost versus total economic cost

The sponsor-funded model may include:

* Prime-contractor labor
* STLT and intermediary awards
* Limited provider support
* Vendor configuration for up to two endpoints
* Pilot-specific evaluation
* Incremental operations
* Travel, facilitation, and dissemination

The total economic cost also includes:

* Provider clinical and IT participation
* STLT legal, privacy, security, and program leadership time
* Intermediary executive and operational contributions
* Downstream-consumer SME review
* EHR-vendor coordination not separately invoiced
* Internal opportunity cost

## Areas relying heavily on inference

Public benchmarks are generally strongest for:

* Overall interoperability implementation
* Interface onboarding
* HIE/HDU operations
* Program management
* Evaluation
* Technical assistance

Evidence is weaker for:

* Pilot-specific governance labor
* Provider validation effort
* Incremental chronic measure reuse
* Trust-scorecard configuration
* In-kind participant effort
* Allocation of existing intermediary infrastructure to one pilot

Those packages should be estimated bottom-up in Stage 4.

---

# 2. Organization code legend

| Code | Organization Type                                         | Role in Pilot                                                                      |
| ---- | --------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| SPN  | Federal sponsor/program office                            | Funds and governs the pilot; approves scope, milestones, and outputs               |
| PMO  | Portfolio PMO or prime contractor                         | Manages the pilot and coordinates cross-organizational execution                   |
| SHR  | Portfolio shared-services team                            | Develops reusable governance, security, architecture, evaluation, and TA assets    |
| STLT | State, tribal, local, or territorial public health agency | Defines public-health use, validates outputs, governs jurisdictional participation |
| HDU  | HIE/HDU intermediary                                      | Ingests, normalizes, validates, links, operates, and distributes the data product  |
| PRV  | Provider network                                          | Supplies source data, validates mappings and outputs, supports remediation         |
| VND  | EHR or health IT vendor                                   | Configures or corrects endpoint-specific exchange where required                   |
| DSC  | Downstream consumer                                       | Uses or validates the second reuse pathway                                         |
| EVL  | Independent evaluator                                     | Designs and executes pilot evaluation and analysis                                 |
| CLD  | Cloud/platform provider                                   | Supplies existing hosted infrastructure through the intermediary                   |

---

# 3. Master organization-specific WBS

The master table is presented at the work-package and major activity level. Activities with different scaling rules are separated.

| WBS ID     | Org. | Phase          | Work Package / Activity                     | Description and Output                                                                | A / R / Support             | Cost Bearing            | Funded / In Kind          | Completion Criteria                            | Scaling                              | Labor Categories                                                         | Non-Labor                               | Estimating Method               | Evidence / Confidence | Risk |
| ---------- | ---- | -------------- | ------------------------------------------- | ------------------------------------------------------------------------------------- | --------------------------- | ----------------------- | ------------------------- | ---------------------------------------------- | ------------------------------------ | ------------------------------------------------------------------------ | --------------------------------------- | ------------------------------- | --------------------- | ---- |
| SPN.01.01  | SPN  | Mobilization   | Approve pilot charter                       | Confirm condition, measure, participants, boundaries, funding, decision rights        | A: SPN; R: SPN/PMO          | Sponsor                 | Funded + in kind          | Signed charter and decision log                | Fixed per pilot                      | Program director, executive sponsor, policy SME                          | None                                    | Bottom-up labor                 | Scope-based; high     |      |
| SPN.01.02  | SPN  | Mobilization   | Establish oversight cadence                 | Create executive, program, and technical governance schedule                          | A: SPN; R: PMO              | Sponsor                 | Funded                    | Cadence, membership, escalation rules approved | Fixed + recurring                    | Program director, PM, coordinator                                        | Meeting support                         | Bottom-up                       | Moderate              |      |
| SPN.02.01  | SPN  | Requirements   | Confirm federal requirements                | Define minimum surveillance output and acceptance expectations                        | A: SPN; R: federal SMEs     | Sponsor                 | Mostly in kind            | Requirement set approved                       | Use-case-specific                    | Public health SME, clinical SME, analyst                                 | None                                    | Bottom-up                       | Moderate              |      |
| SPN.14.01  | SPN  | Evaluation     | Approve evaluation questions                | Confirm decision-utility and scaling questions                                        | A: SPN; R: EVL              | Sponsor                 | Funded/in kind            | Evaluation plan approved                       | Per evaluation cycle                 | Evaluator, program SME                                                   | None                                    | Bottom-up                       | Moderate              |      |
| SPN.15.01  | SPN  | Reporting      | Review final products                       | Review findings, limitations, and recommendations                                     | A: SPN; R: PMO/EVL          | Sponsor                 | In kind                   | Formal acceptance                              | Fixed                                | Executive sponsor, program director, SMEs                                | None                                    | Bottom-up                       | High                  |      |
| PMO.01.01  | PMO  | Mobilization   | Detailed project plan                       | Develop integrated schedule, WBS, risk register, RACI, communications plan            | A: SPN; R: PMO              | Sponsor                 | Funded                    | Baseline plan approved                         | Fixed per pilot                      | PM, coordinator, program director                                        | PM tools                                | Bottom-up                       | High                  |      |
| PMO.01.02  | PMO  | Mobilization   | Participant confirmation                    | Confirm one STLT, one HDU, six provider networks, downstream consumer                 | A: SPN; R: PMO              | Sponsor                 | Funded                    | Participation letters or agreements            | Per organization                     | PM, stakeholder lead                                                     | Travel/meeting                          | Parametric per participant      | Moderate              |      |
| PMO.03.01  | PMO  | Governance     | Pilot governance administration             | Prepare meetings, decisions, issues, actions, and escalations                         | A: SPN; R: PMO              | Sponsor                 | Funded                    | Governance records current                     | Monthly recurring                    | PM, coordinator                                                          | Meeting tools                           | Monthly run rate                | Moderate              |      |
| PMO.07.01  | PMO  | Implementation | Integrated delivery coordination            | Coordinate dependencies among HDU, STLT, providers, vendors, evaluator                | A: PMO; R: PMO              | Sponsor                 | Funded                    | Milestones met; blockers resolved              | Monthly + participant-specific       | PM, BA, architect                                                        | Travel                                  | Monthly run rate                | Moderate              |      |
| PMO.11.01  | PMO  | Launch         | Go-live readiness coordination              | Consolidate evidence and conduct go/no-go review                                      | A: SPN; R: PMO              | Sponsor                 | Funded                    | Go-live approval package                       | Fixed                                | PM, QA lead, architect                                                   | None                                    | Bottom-up                       | High                  |      |
| PMO.12.01  | PMO  | Operations     | Operational management                      | Coordinate four months of operations, incidents, changes, and reporting               | A: PMO; R: PMO              | Sponsor                 | Funded                    | Four operational cycles completed              | Per month                            | PM, coordinator, analyst                                                 | None                                    | Monthly run rate                | High                  |      |
| PMO.16.01  | PMO  | Transition     | Sustainability planning                     | Develop continuation, scale, and funding options                                      | A: SPN; R: PMO              | Sponsor                 | Funded                    | Sustainability memorandum                      | Fixed                                | Program director, financial analyst, architect                           | None                                    | Bottom-up                       | Moderate              |      |
| PMO.17.01  | PMO  | Closeout       | Administrative closeout                     | Close risks, archive artifacts, reconcile deliverables and lessons                    | A: SPN; R: PMO              | Sponsor                 | Funded                    | Closeout checklist complete                    | Fixed                                | PM, coordinator, technical writer                                        | Repository                              | Bottom-up                       | High                  |      |
| SHR.03.01  | SHR  | Governance     | Common governance package                   | Adapt portfolio charter, RACI, decision framework, escalation process                 | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Pilot-specific adaptation approved             | Shared fixed + per pilot adaptation  | Governance specialist, PM                                                | None                                    | Shared allocation               | High                  |      |
| SHR.04.01  | SHR  | Legal          | Model DUA/participation templates           | Provide reusable template and pilot adaptation guidance                               | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Template package available                     | Shared fixed                         | Legal counsel, privacy specialist                                        | External legal services                 | Shared fixed                    | Moderate              |      |
| SHR.05.01  | SHR  | Security       | Common security requirements                | Define baseline controls, evidence checklist, access, logging, incident expectations  | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Security checklist accepted                    | Shared fixed                         | Security architect, privacy specialist                                   | Security tools already existing         | Shared fixed                    | Moderate              |      |
| SHR.06.01  | SHR  | Architecture   | Reference architecture                      | Provide reusable acquisition, normalization, validation, distribution pattern         | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Reference design published                     | Shared fixed                         | Solution architect, data architect                                       | Diagram tools                           | Shared fixed                    | High                  |      |
| SHR.08.01  | SHR  | Data           | Common conformance framework                | Provide reusable FHIR, USCDI, provenance, and data-quality methods                    | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Framework versioned and approved               | Shared fixed                         | Interoperability architect, terminology SME, QA                          | Test tools                              | Shared fixed                    | Moderate              |      |
| SHR.10.01  | SHR  | Training       | Common training materials                   | Prepare reusable participant onboarding, testing, and operations materials            | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Materials available                            | Shared fixed                         | Training lead, technical writer                                          | LMS/materials                           | Shared fixed                    | Moderate              |      |
| SHR.14.01  | SHR  | Evaluation     | Common evaluation framework                 | Develop common measures, instruments, data definitions, and analysis plan             | A: Portfolio; R: SHR/EVL    | Portfolio               | Shared funded             | Framework approved across pilots               | Shared fixed                         | Evaluator, statistician, public health SME                               | Survey tools                            | Shared fixed                    | High                  |      |
| SHR.15.01  | SHR  | Reporting      | Common playbook structure                   | Develop reusable implementation and scale-playbook templates                          | A: Portfolio; R: SHR        | Portfolio               | Shared funded             | Template approved                              | Shared fixed                         | Technical writer, communications specialist                              | Publication tools                       | Shared fixed                    | High                  |      |
| STLT.01.01 | STLT | Mobilization   | Designate jurisdiction team                 | Name program, informatics, legal, privacy, security, and executive participants       | A: STLT; R: STLT            | STLT                    | In kind or award-funded   | Team and decision rights documented            | Fixed per STLT                       | Executive sponsor, PM, public health SME                                 | None                                    | Bottom-up                       | High                  |      |
| STLT.02.01 | STLT | Requirements   | Define surveillance workflow                | Document current use, target use, users, decisions, and required output               | A: STLT; R: STLT/PMO        | STLT award              | Funded + in kind          | Workflow and requirement package accepted      | Per workflow                         | Public health SME, epidemiologist, BA                                    | Workshops                               | Bottom-up                       | Moderate              |      |
| STLT.02.02 | STLT | Readiness      | Jurisdiction readiness assessment           | Assess authority, data access, technical capability, staffing, and dependencies       | A: STLT; R: PMO/STLT        | Sponsor/STLT            | Funded                    | Readiness findings and action plan             | Per STLT                             | BA, governance specialist, security SME                                  | None                                    | Bounded component analogue      | Moderate              |      |
| STLT.03.01 | STLT | Governance     | Jurisdiction governance approval            | Review purpose, access, retention, escalation, and feedback procedures                | A: STLT; R: STLT            | STLT                    | Mostly in kind            | Governance authorization                       | Fixed                                | Executive sponsor, governance lead, counsel                              | None                                    | Bottom-up                       | Low-moderate          |      |
| STLT.04.01 | STLT | Legal          | Review and execute agreements               | Review DUA, participation, redisclosure, and data recipient terms                     | A: STLT; R: STLT legal      | STLT                    | Funded/in kind            | Agreements executed                            | Per agreement                        | Legal counsel, privacy specialist                                        | External counsel allowance              | Bottom-up/allowance             | Low                   |      |
| STLT.05.01 | STLT | Security       | Jurisdiction security review                | Review intermediary controls and approve access mechanism                             | A: STLT; R: STLT security   | STLT                    | In kind                   | Security approval or documented exceptions     | Per review                           | Security architect, privacy specialist                                   | None                                    | Bottom-up                       | Low                   |      |
| STLT.08.01 | STLT | Data           | Validate measure and cohort definitions     | Review clinical and public-health interpretation                                      | A: STLT; R: STLT SMEs       | STLT                    | In kind                   | Written validation                             | Use-case-specific                    | Epidemiologist, clinical SME, analyst                                    | None                                    | Bottom-up                       | Moderate              |      |
| STLT.09.01 | STLT | Testing        | User acceptance testing                     | Review test output, completeness, timeliness, stratification, and utility             | A: STLT; R: STLT            | STLT award              | Funded/in kind            | UAT sign-off or disposition                    | Per test cycle, maximum 2            | Epidemiologist, analyst, QA reviewer                                     | None                                    | Bottom-up                       | Moderate              |      |
| STLT.10.01 | STLT | Training       | Train jurisdiction users                    | Train users on access, interpretation, quality caveats, escalation                    | A: STLT; R: PMO/HDU         | Sponsor/STLT            | Funded                    | Users complete training                        | Per user group                       | Trainer, analyst, public health SME                                      | Materials                               | Per cohort                      | Moderate              |      |
| STLT.12.01 | STLT | Operations     | Use operational output                      | Review each reporting cycle and document decisions or utility                         | A: STLT; R: STLT            | STLT                    | In kind/award-funded      | Four months of use records                     | Per month/reporting cycle            | Epidemiologist, analyst                                                  | None                                    | Monthly run rate                | Low-moderate          |      |
| STLT.13.01 | STLT | Monitoring     | Provide structured utility feedback         | Submit usability, timeliness, and actionability feedback                              | A: STLT; R: STLT            | STLT                    | In kind                   | Feedback submitted each cycle                  | Per cycle                            | Public health SME, analyst                                               | Survey tool                             | Per reporting cycle             | Moderate              |      |
| STLT.14.01 | STLT | Evaluation     | Supply evaluation data                      | Provide burden, workflow, use, and outcome evidence                                   | A: EVL; R: STLT             | STLT                    | In kind                   | Required evaluation dataset complete           | Per evaluation cycle                 | Analyst, PM, epidemiologist                                              | None                                    | Bottom-up                       | Moderate              |      |
| STLT.16.01 | STLT | Transition     | Jurisdiction continuation decision          | Assess whether to continue, expand, modify, or stop                                   | A: STLT; R: STLT            | STLT                    | In kind                   | Formal recommendation                          | Fixed                                | Executive sponsor, program lead, analyst                                 | None                                    | Bottom-up                       | High                  |      |
| HDU.01.01  | HDU  | Mobilization   | Establish intermediary delivery team        | Assign technical, operational, governance, and product leads                          | A: HDU; R: HDU              | HDU award               | Funded                    | Team and capacity confirmed                    | Fixed                                | Delivery manager, architect, operations lead                             | None                                    | Bottom-up                       | High                  |      |
| HDU.02.01  | HDU  | Readiness      | Inventory existing connectivity             | Verify six provider networks and relevant data pathways                               | A: HDU; R: HDU              | HDU award               | Funded                    | Source inventory and 75% threshold confirmed   | Per provider network/data source     | BA, integration engineer, data engineer                                  | Inventory tools                         | Parametric                      | High                  |      |
| HDU.02.02  | HDU  | Readiness      | Gap and delta assessment                    | Identify missing fields, incompatible endpoints, and two allowable new configurations | A: HDU; R: HDU              | HDU award               | Funded                    | Delta backlog approved                         | Per data source/interface            | Architect, integration engineer, terminology SME                         | Test tools                              | Per source/interface            | High                  |      |
| HDU.03.01  | HDU  | Governance     | Operational governance procedures           | Define access approvals, issue escalation, data correction, and audit procedures      | A: HDU; R: HDU              | HDU award               | Funded                    | Procedures approved                            | Fixed per pilot                      | Governance lead, operations lead, privacy SME                            | None                                    | Bottom-up                       | Moderate              |      |
| HDU.04.01  | HDU  | Legal          | Execute provider and STLT data arrangements | Adapt existing agreements or execute pilot addenda                                    | A: HDU; R: HDU legal        | HDU/STLT                | Funded/in kind            | Required agreements complete                   | Per agreement/participant            | Legal counsel, privacy specialist                                        | External legal                          | Bottom-up/allowance             | Low                   |      |
| HDU.05.01  | HDU  | Security       | Configure pilot access                      | Configure RBAC, accounts, logging, and data-recipient permissions                     | A: HDU; R: HDU              | HDU award               | Funded                    | Access tests pass                              | Per user group/recipient/environment | Security engineer, IAM admin                                             | Existing IAM/logging                    | Bottom-up                       | Moderate              |      |
| HDU.05.02  | HDU  | Security       | Security evidence package                   | Assemble existing controls, diagrams, logs, incident process, and exceptions          | A: HDU; R: HDU              | HDU award               | Funded                    | Participant reviews complete                   | Fixed per pilot                      | Security architect, technical writer                                     | Existing tools                          | Bottom-up                       | Moderate              |      |
| HDU.06.01  | HDU  | Architecture   | Pilot solution design                       | Adapt reference architecture to intermediary environment                              | A: HDU; R: HDU/SHR          | HDU award               | Funded                    | Design approved                                | Fixed use-case-specific              | Solution architect, data architect, interoperability architect           | Diagram/repository tools                | Bottom-up                       | High                  |      |
| HDU.06.02  | HDU  | Architecture   | Data-product and distribution design        | Define operational product and second reuse demonstration                             | A: HDU; R: HDU              | HDU award               | Funded                    | Product specification approved                 | Per downstream use                   | Data architect, analyst, public health SME                               | None                                    | Per use/recipient               | Moderate              |      |
| HDU.07.01  | HDU  | Integration    | Configure existing source pathways          | Configure filters, extraction, schedules, routing, and source metadata                | A: HDU; R: HDU              | HDU award               | Funded                    | Four or more existing pathways configured      | Per existing source pathway          | Integration engineer, data engineer                                      | Existing interface platform             | Parametric per pathway          | Moderate-high         |      |
| HDU.07.02  | HDU  | Integration    | Configure new endpoints                     | Implement no more than two materially new endpoint configurations                     | A: HDU; R: HDU/VND          | HDU/vendor              | Funded                    | New endpoints exchange test data               | Per new endpoint, max 2              | Integration engineer, vendor specialist, QA                              | Vendor charges/interface fees           | Vendor quote + bounded analogue | Moderate              |      |
| HDU.07.03  | HDU  | Integration    | Configure operational output                | Produce fully operational STLT/public-health output                                   | A: HDU; R: HDU              | HDU award               | Funded                    | Output delivered in agreed schedule and format | Per operational output               | Data engineer, application developer, analyst                            | Existing analytics/export tooling       | Bottom-up                       | Moderate              |      |
| HDU.07.04  | HDU  | Integration    | Configure second-use demonstration          | Generate representative artifact or measure result without full production support    | A: HDU; R: HDU/DSC          | HDU award               | Funded                    | Demonstration validated                        | Per secondary use                    | Data engineer, measure SME, analyst                                      | Existing measure engine where available | Bottom-up                       | Moderate              |      |
| HDU.08.01  | HDU  | Data           | Minimum dataset mapping                     | Map approximately 15–25 elements to source data and standard representations          | A: HDU; R: HDU              | HDU award               | Funded                    | Mapping workbook and lineage approved          | Per data element × source type       | Data analyst, terminology specialist, data engineer                      | Terminology resources                   | Parametric                      | Moderate              |      |
| HDU.08.02  | HDU  | Data           | Cohort and measure logic                    | Implement one condition and one primary workflow/measure                              | A: HDU; R: HDU; C: STLT/SPN | HDU award               | Funded                    | Logic passes test cases                        | Per use case/measure                 | Clinical SME, public health SME, data engineer, CQL specialist if needed | Measure licensing only if applicable    | Bottom-up/vendor quote          | Moderate              |      |
| HDU.08.03  | HDU  | Data           | Data-quality rule configuration             | Configure conformance, completeness, timeliness, provenance, and plausibility checks  | A: HDU; R: HDU              | HDU award               | Funded                    | Rules executed and documented                  | Per rule/data element                | QA analyst, data engineer, terminology SME                               | Existing validation tools               | Bottom-up                       | Moderate              |      |
| HDU.08.04  | HDU  | Data           | Data-quality report                         | Produce standard quality report; no custom dashboard                                  | A: HDU; R: HDU              | HDU award               | Funded                    | Report generated per cycle                     | Per reporting cycle                  | Data analyst, QA analyst                                                 | Existing reporting tool                 | Recurring run rate              | High                  |      |
| HDU.09.01  | HDU  | Testing        | Unit and integration testing                | Test mappings, transformations, routing, access, and outputs                          | A: HDU; R: HDU              | HDU award               | Funded                    | Test evidence complete                         | Per pathway/output                   | Test engineer, integration engineer, data engineer                       | Test environment/tools                  | Bottom-up                       | High                  |      |
| HDU.09.02  | HDU  | Testing        | End-to-end validation                       | Conduct source-to-output testing across participating pathways                        | A: HDU; R: HDU/PRV/STLT     | HDU award               | Funded                    | E2E scenarios pass or are dispositioned        | Per scenario/source                  | QA lead, provider analyst, STLT analyst                                  | None                                    | Parametric                      | Moderate              |      |
| HDU.09.03  | HDU  | Testing        | Remediation cycle 1                         | Correct priority defects preventing acceptance                                        | A: HDU; R: HDU/VND/PRV      | Relevant party          | Funded/in kind            | Critical defects resolved or documented        | Per defect/interface                 | Engineers, QA, vendor specialist                                         | Vendor charges                          | Risk-adjusted allowance         | Low-moderate          |      |
| HDU.09.04  | HDU  | Testing        | Remediation cycle 2                         | Complete final capped remediation cycle                                               | A: HDU; R: HDU/VND/PRV      | Relevant party          | Funded/in kind            | Final disposition; no further funded cycle     | Per defect/interface                 | Same as above                                                            | Vendor charges                          | Risk-adjusted allowance         | Low                   |      |
| HDU.10.01  | HDU  | Onboarding     | Provider technical onboarding               | Confirm contacts, source inventory, testing schedule, and escalation path             | A: HDU; R: HDU              | HDU award               | Funded                    | Six onboarding checklists complete             | Per provider network                 | Onboarding lead, BA, integration engineer                                | Meeting costs                           | Parametric per network          | Moderate              |      |
| HDU.10.02  | HDU  | Training       | Provider and STLT technical training        | Explain exchange, testing, quality reports, and incident procedures                   | A: HDU; R: HDU/PMO          | HDU award               | Funded                    | Training completed                             | Per cohort                           | Trainer, QA analyst, operations engineer                                 | Materials                               | Per cohort                      | Moderate              |      |
| HDU.11.01  | HDU  | Launch         | Production readiness review                 | Validate monitoring, support, rollback, data schedule, and approvals                  | A: HDU; R: HDU              | HDU award               | Funded                    | Readiness checklist signed                     | Fixed                                | Operations lead, security engineer, QA lead                              | None                                    | Bottom-up                       | High                  |      |
| HDU.11.02  | HDU  | Launch         | Go-live and stabilization                   | Activate production and provide initial stabilization                                 | A: HDU; R: HDU              | HDU award               | Funded                    | Stable production operation                    | Per go-live                          | Operations engineer, integration engineer, PM                            | Existing operations platform            | Bottom-up                       | High                  |      |
| HDU.12.01  | HDU  | Operations     | Four-month production operation             | Run ingestion, processing, quality checks, and distribution                           | A: HDU; R: HDU              | HDU award               | Funded                    | Four monthly operational periods complete      | Per month                            | Operations engineer, data engineer, analyst                              | Incremental cloud/storage/logging       | Recurring run rate              | High                  |      |
| HDU.12.02  | HDU  | Operations     | Incident and ticket support                 | Triage and resolve pilot-specific operational issues                                  | A: HDU; R: HDU              | HDU award               | Funded                    | Tickets resolved within agreed service targets | Per ticket/month                     | Help desk, operations engineer, integration engineer                     | Ticketing tools                         | Monthly allowance + per ticket  | Moderate              |      |
| HDU.13.01  | HDU  | Monitoring     | Performance reporting                       | Report latency, completeness, failures, uptime, and reuse                             | A: HDU; R: HDU              | HDU award               | Funded                    | Monthly report delivered                       | Per month                            | Analyst, operations engineer                                             | Reporting tools                         | Monthly run rate                | High                  |      |
| HDU.14.01  | HDU  | Evaluation     | Produce evaluation extracts                 | Deliver operational and technical evidence to evaluator                               | A: EVL; R: HDU              | HDU award               | Funded                    | Evaluation files accepted                      | Per evaluation cycle                 | Data analyst, data engineer                                              | Secure transfer                         | Bottom-up                       | Moderate              |      |
| HDU.16.01  | HDU  | Transition     | Scale and operations assessment             | Estimate cost and effort to continue or add sites/use cases                           | A: HDU; R: HDU              | HDU award               | Funded                    | Scale assessment delivered                     | Fixed                                | Architect, operations lead, financial analyst                            | None                                    | Bottom-up                       | Moderate              |      |
| HDU.17.01  | HDU  | Closeout       | Pilot technical closeout                    | Archive configurations, document exceptions, confirm retention and access             | A: HDU; R: HDU              | HDU award               | Funded                    | Closeout checklist complete                    | Fixed                                | Operations lead, security analyst, technical writer                      | Storage/archiving                       | Bottom-up                       | High                  |      |
| PRV.01.01  | PRV  | Mobilization   | Designate provider team                     | Name clinical, IT, security, legal, and operational contacts                          | A: PRV; R: PRV              | Provider                | In kind                   | Team confirmed                                 | Per provider network                 | Provider PM, clinical SME, interface analyst                             | None                                    | In-kind bottom-up               | High                  |      |
| PRV.02.01  | PRV  | Readiness      | Source and workflow inventory               | Document systems, endpoints, data fields, vendors, and operational workflow           | A: PRV; R: PRV              | Provider                | In kind or stipend-funded | Inventory accepted                             | Per provider network/system          | Interface analyst, BA, clinical SME                                      | None                                    | Per participant                 | Moderate              |      |
| PRV.04.01  | PRV  | Legal          | Provider agreement review                   | Review participation, permitted use, minimum necessary, and liability                 | A: PRV; R: PRV legal        | Provider                | In kind                   | Agreement signed                               | Per provider                         | Counsel, privacy specialist                                              | External counsel if needed              | In-kind allowance               | Low                   |      |
| PRV.05.01  | PRV  | Security       | Provider security review                    | Review endpoint, credentials, data handling, and incident procedures                  | A: PRV; R: PRV security     | Provider                | In kind                   | Approval complete                              | Per provider                         | Security analyst, IAM admin                                              | None                                    | In-kind bottom-up               | Low                   |      |
| PRV.07.01  | PRV  | Integration    | Existing endpoint support                   | Supply credentials, metadata, schedules, and technical coordination                   | A: PRV; R: PRV              | Provider                | In kind/stipend           | Existing connection ready                      | Per existing endpoint                | Interface analyst, vendor specialist                                     | Existing vendor service                 | In-kind parametric              | Moderate              |      |
| PRV.07.02  | PRV  | Integration    | New endpoint enablement support             | Support one of up to two new configurations                                           | A: PRV; R: PRV/VND          | Provider/vendor         | Funded/in kind            | Endpoint passes connectivity test              | Per new endpoint                     | Interface analyst, IAM admin, vendor specialist                          | Vendor fee                              | Vendor quote                    | Moderate              |      |
| PRV.08.01  | PRV  | Data           | Source-data validation                      | Validate field interpretation, units, codes, provenance, and known gaps               | A: PRV; R: PRV              | Provider                | In kind                   | Mapping sign-off                               | Per data source/mapping cycle        | Clinical SME, data analyst, interface analyst                            | None                                    | In-kind bottom-up               | Low-moderate          |      |
| PRV.09.01  | PRV  | Testing        | Test-data preparation                       | Produce or authorize representative test data                                         | A: PRV; R: PRV              | Provider                | In kind                   | Test data accepted                             | Per provider/test cycle              | Interface analyst, privacy specialist                                    | Test environment                        | Bottom-up                       | Moderate              |      |
| PRV.09.02  | PRV  | Testing        | Defect review and correction                | Investigate provider-side issues within two cycles                                    | A: PRV; R: PRV/VND          | Provider/vendor         | In kind/funded            | Assigned defects dispositioned                 | Per defect/cycle                     | Interface analyst, vendor specialist, clinical SME                       | Vendor fee                              | Risk allowance                  | Low                   |      |
| PRV.11.01  | PRV  | Launch         | Provider go-live authorization              | Confirm production schedule and escalation contacts                                   | A: PRV; R: PRV              | Provider                | In kind                   | Authorization issued                           | Per provider                         | Provider PM, IT manager                                                  | None                                    | Bottom-up                       | High                  |      |
| PRV.12.01  | PRV  | Operations     | Operational source support                  | Respond to source failures, data-quality questions, and drift                         | A: PRV; R: PRV              | Provider                | In kind                   | Support provided for four months               | Per month/provider                   | Interface analyst, data analyst                                          | None                                    | Monthly in-kind run rate        | Low                   |      |
| PRV.14.01  | PRV  | Evaluation     | Burden and workflow evidence                | Provide time, burden, defects, and workflow feedback                                  | A: EVL; R: PRV              | Provider                | In kind                   | Evaluation response complete                   | Per provider/evaluation cycle        | PM, clinical SME, IT analyst                                             | Survey                                  | In-kind bottom-up               | Moderate              |      |
| VND.02.01  | VND  | Readiness      | Endpoint capability confirmation            | Confirm supported APIs, exports, versions, and constraints                            | A: PRV/HDU; R: VND          | Provider/vendor         | In kind or vendor-funded  | Capability statement received                  | Per vendor/system                    | Vendor product specialist                                                | None                                    | Vendor quote/allowance          | Moderate              |      |
| VND.07.01  | VND  | Integration    | Endpoint configuration                      | Configure or enable no more than two new endpoints                                    | A: PRV; R: VND              | Sponsor/provider        | Funded                    | Test data exchanged                            | Per endpoint                         | Vendor product specialist, interface developer                           | License/interface fee                   | Vendor quote                    | High                  |      |
| VND.09.01  | VND  | Testing        | Vendor defect remediation                   | Correct product/configuration defects within capped cycles                            | A: PRV; R: VND              | Provider/vendor/sponsor | Funded or included        | Defects resolved or documented                 | Per defect/cycle                     | Vendor developer, QA                                                     | Vendor support                          | Vendor quote/allowance          | Low-moderate          |      |
| DSC.02.01  | DSC  | Requirements   | Define secondary reuse acceptance           | Identify minimum artifact or measure result needed to demonstrate reuse               | A: DSC; R: DSC/PMO          | Downstream program      | Mostly in kind            | Requirements approved                          | Per downstream use                   | Program SME, measure SME, analyst                                        | None                                    | Bottom-up                       | Moderate              |      |
| DSC.08.01  | DSC  | Data           | Review secondary-use logic                  | Validate mapping and expected output                                                  | A: DSC; R: DSC              | Downstream program      | In kind                   | Written validation                             | Per use                              | Measure SME, analyst                                                     | Potential licensing                     | Bottom-up                       | Moderate              |      |
| DSC.09.01  | DSC  | Testing        | Validate demonstration output               | Review sample result and document fitness for purpose                                 | A: DSC; R: DSC              | Downstream program      | In kind                   | Acceptance or limitations documented           | Per demonstration                    | Analyst, SME                                                             | None                                    | Bottom-up                       | Moderate              |      |
| EVL.01.01  | EVL  | Mobilization   | Pilot evaluation work plan                  | Adapt portfolio framework to condition and workflow                                   | A: SPN; R: EVL              | Sponsor                 | Funded                    | Evaluation work plan approved                  | Fixed per pilot                      | Evaluator, statistician, SME                                             | None                                    | Bottom-up                       | High                  |      |
| EVL.02.01  | EVL  | Baseline       | Baseline data collection                    | Collect current timeliness, burden, quality, and workflow evidence                    | A: EVL; R: EVL/participants | Sponsor                 | Funded                    | Baseline dataset complete                      | Per participant/source               | Evaluator, analyst                                                       | Survey tools                            | Parametric + bottom-up          | Moderate              |      |
| EVL.13.01  | EVL  | Monitoring     | Evaluation monitoring                       | Track implementation fidelity and evidence completeness                               | A: EVL; R: EVL              | Sponsor                 | Funded                    | Monitoring records current                     | Monthly                              | Evaluator, analyst                                                       | None                                    | Monthly run rate                | Moderate              |      |
| EVL.14.01  | EVL  | Evaluation     | Technical and operational analysis          | Analyze quality, timeliness, burden, utility, and reuse                               | A: EVL; R: EVL              | Sponsor                 | Funded                    | Analysis reproducible                          | Per metric/evaluation cycle          | Evaluator, statistician, data analyst                                    | Analytical tools                        | Bottom-up                       | High                  |      |
| EVL.14.02  | EVL  | Evaluation     | Economic and implementation analysis        | Analyze sponsor cost, in-kind effort, and scale implications                          | A: EVL; R: EVL              | Sponsor                 | Funded                    | Cost and implementation findings complete      | Fixed + per organization             | Economist/financial analyst, evaluator                                   | None                                    | Bottom-up                       | Moderate              |      |
| EVL.15.01  | EVL  | Reporting      | Pilot evaluation report                     | Produce findings, limitations, recommendations, and evidence tables                   | A: SPN; R: EVL              | Sponsor                 | Funded                    | Report accepted                                | Fixed                                | Evaluator, technical writer, statistician                                | Publication support                     | Bottom-up                       | High                  |      |
| EVL.15.02  | EVL  | Dissemination  | Briefing and reusable findings              | Prepare executive briefing and inputs to portfolio synthesis                          | A: SPN; R: EVL/PMO          | Sponsor                 | Funded                    | Briefing delivered                             | Fixed                                | Communications specialist, evaluator                                     | Meeting/travel                          | Bottom-up                       | High                  |      |

---

# 4. Organization-level WBS summaries

## Federal sponsor

**Primary responsibilities:** scope control, funding, approvals, escalation, acceptance, and policy direction.

**Major cost drivers:** leadership and SME participation, governance cadence, review cycles.

**Likely treatment:** mostly pilot-specific fixed cost and federal in-kind labor.

**Evidence strength:** moderate for program oversight, weak for exact hours.

## Portfolio PMO

**Primary responsibilities:** integrated planning, coordination, risk, reporting, go-live, sustainability, and closeout.

**Fixed work:** project planning, chartering, closeout.

**Recurring work:** governance administration and four months of operational coordination.

**Evidence strength:** relatively strong through general program-management analogues, but pilot complexity requires bottom-up staffing.

## Portfolio shared-services team

**Primary responsibilities:** common governance, legal templates, security baseline, reference architecture, conformance framework, training materials, evaluation framework, and playbook.

**Cost treatment:** central portfolio cost. Do not rebuild or charge full development cost to each pilot.

**Pilot allocation:** only incremental adaptation should appear in the individual pilot cost.

## STLT public health agency

**Primary responsibilities:** define public-health use, authorize participation, validate the measure and data product, conduct UAT, use the output, and provide decision-utility feedback.

**Main cost drivers:** legal review, governance, public health SME effort, user acceptance, four months of operational use.

**Likely in-kind work:** executive participation, epidemiologist time, legal/security review, evaluation submissions.

## HIE/HDU intermediary

**Primary responsibilities:** connectivity inventory, design, configuration, mapping, validation, quality reporting, testing, go-live, production operation, and evaluation evidence.

**Main cost drivers:** number of source pathways, number of new endpoints, data quality, mapping complexity, defect volume, and operational support.

**Fixed work:** pilot design, security package, use-case logic, operational procedures.

**Variable work:** per provider network, per data source, per endpoint, per defect, and per output.

**Recurring work:** four months of operations, monitoring, quality reporting, and support.

## Provider networks

**Primary responsibilities:** technical inventory, agreements, source validation, test data, defect review, go-live approval, operational support, and evaluation.

**Main cost drivers:** number of systems, vendor diversity, data quality, and internal approval processes.

**Likely treatment:** mostly in kind, potentially supplemented with capped stipends.

## EHR/health IT vendors

**Primary responsibilities:** confirm endpoint support, configure up to two new endpoints, and correct vendor-specific defects.

**Main cost drivers:** vendor fee structures, product version, licensing, customization, and support terms.

**Estimating approach:** obtain direct quotes. Public analogues are insufficient for precise endpoint-specific pricing.

## Downstream consumer

**Primary responsibilities:** define and validate the secondary reuse demonstration.

**Boundary:** only a demonstration is required. A separate production integration is excluded.

**Cost treatment:** mainly in-kind SME and analyst effort.

## Evaluator

**Primary responsibilities:** baseline, monitoring, analysis, economic assessment, reporting, and dissemination.

**Fixed work:** work plan, report, and briefing.

**Variable work:** data collection per participant and analysis per metric/source.

**Evidence strength:** moderate to strong for evaluation structure; bottom-up labor remains appropriate.

---

# 5. WBS-to-source traceability

| WBS IDs         | Work Package                                           | Scope Basis                                                           | Evidence Use                                            | Confidence    | Adjustment / Limitation                                                                           |
| --------------- | ------------------------------------------------------ | --------------------------------------------------------------------- | ------------------------------------------------------- | ------------- | ------------------------------------------------------------------------------------------------- |
| HDU.02–HDU.12   | Intermediary implementation and operations             | Original chronic pilot and Stage 1 architecture                       | Supports scope, sequencing, and major cost drivers      | Moderate      | Public analogues often include broader platform work; use only incremental implementation portion |
| PRV.02–PRV.12   | Provider onboarding and source support                 | Stage 1 responsibility matrix                                         | Supports required participant activities                | Moderate      | In-kind labor rarely disclosed publicly                                                           |
| STLT.02–STLT.16 | Jurisdiction workflow, governance, validation, and use | Original pilot emphasis on STLT utility                               | Supports organization responsibilities                  | Moderate      | Labor intensity requires bottom-up estimate                                                       |
| VND.07–VND.09   | New endpoint configuration                             | Stage 2 interface and vendor component research                       | Supports vendor quote requirement and interface scaling | Moderate      | Costs vary materially by vendor and contract                                                      |
| EVL.01–EVL.15   | Evaluation                                             | Stage 2 evaluation analogues and original pilot evaluation objectives | Supports evaluation phases, staffing, and outputs       | Moderate-high | Allocate common design to portfolio; retain pilot analysis separately                             |
| SHR.03–SHR.15   | Portfolio reusable assets                              | Agreed portfolio assumptions                                          | Supports shared-cost classification                     | High          | Allocation policy is a sponsor decision                                                           |
| HDU.08.01–08.04 | Mapping, measure logic, and trust reporting            | Technical brief and Stage 1 model                                     | Supports scope and deliverables                         | Moderate      | Limited public unit-cost evidence                                                                 |
| HDU.09.03–09.04 | Two remediation cycles                                 | Explicit current assumption                                           | Supports capped risk structure                          | High          | Defect quantity remains uncertain                                                                 |
| HDU.12.01       | Four-month operation                                   | Explicit current assumption                                           | Supports recurring duration                             | High          | Incremental hosting must be separated from existing platform cost                                 |
| DSC.02–DSC.09   | Secondary reuse demonstration                          | Explicit current assumption                                           | Supports bounded second use                             | High          | Must not become a second production implementation                                                |

The Stage 2 analogue evidence should be used primarily to constrain unit-cost ranges and labor-intensity assumptions, not to redefine the WBS. That follows the governing Stage 3 requirement. 

---

# 6. Estimating-method table

| WBS / Package                 | Method                  | Formula Structure                                                                | Scaling Unit       | Inputs Needed                   | Low/Base/High Treatment               |
| ----------------------------- | ----------------------- | -------------------------------------------------------------------------------- | ------------------ | ------------------------------- | ------------------------------------- |
| PMO recurring management      | Recurring run rate      | Monthly team hours × project months                                              | Month              | Staffing mix, 12-month duration | Vary staffing intensity               |
| Participant confirmation      | Parametric              | Organizations × hours per organization                                           | Organization       | 9–10 organizations              | Vary recruitment difficulty           |
| STLT workflow definition      | Bottom-up               | Workshops × labor by category                                                    | Workflow           | Number and length of sessions   | Vary workflow complexity              |
| Legal reviews                 | Bottom-up + allowance   | Fixed review hours + agreements × hours/agreement                                | Agreement          | Agreement count, counsel rates  | Vary novelty and review cycles        |
| HDU connectivity inventory    | Parametric              | Provider networks × hours/network + systems × hours/system                       | Provider/system    | Six networks, system count      | Vary source diversity                 |
| Existing source configuration | Parametric              | Existing pathways × hours/pathway                                                | Pathway            | At least 75% connected          | Vary configuration delta              |
| New endpoint configuration    | Vendor quote            | Endpoints × quoted implementation fee                                            | Endpoint           | Maximum two                     | Quote-specific                        |
| Dataset mapping               | Parametric              | Data elements × source types × hours/element-source                              | Mapping pair       | 15–25 elements, source types    | Vary data quality and standardization |
| Measure/workflow logic        | Bottom-up               | Fixed design + test cases × hours/test case                                      | Measure/use case   | One measure                     | Vary logic complexity                 |
| Data-quality rules            | Bottom-up/parametric    | Rules × hours/rule + sources × validation effort                                 | Rule/source        | Rule count and source count     | Vary rule novelty                     |
| Testing                       | Bottom-up               | Scenarios × hours/scenario + interfaces × hours/interface                        | Scenario/interface | Test inventory                  | Vary rigor                            |
| Remediation                   | Risk-adjusted allowance | Defects × hours/defect × cycles                                                  | Defect/cycle       | Defect assumption, two cycles   | Major sensitivity item                |
| Provider onboarding           | Parametric              | Six networks × hours/network                                                     | Provider network   | Six                             | Vary maturity                         |
| Training                      | Parametric              | Cohorts × preparation + delivery hours                                           | Cohort             | User groups                     | Vary audience size                    |
| Four-month operations         | Recurring run rate      | Monthly labor + incremental infrastructure × 4                                   | Month              | Support model, cloud delta      | Vary incident volume                  |
| Evaluation                    | Bottom-up               | Fixed plan/report + participants × collection effort + metrics × analysis effort | Participant/metric | Participant and metric counts   | Vary rigor                            |
| In-kind participant work      | Total economic cost     | Hours by organization × loaded internal proxy rate                               | Organization/hour  | Reported hours                  | Show separately                       |
| Shared portfolio work         | Shared fixed            | Portfolio cost retained centrally or allocated per pilot                         | Portfolio/pilot    | Number of pilots                | Show central and allocated views      |

---

# 7. Labor-category matrix

| WBS Area           | Lead Labor                    | Supporting Labor                                    | Participant Labor               | Vendor Labor                | Reviewer / Approver         |
| ------------------ | ----------------------------- | --------------------------------------------------- | ------------------------------- | --------------------------- | --------------------------- |
| Program governance | Program director              | PM, coordinator, governance specialist              | Executive sponsors              | None                        | Federal sponsor             |
| STLT workflow      | Public health SME             | BA, epidemiologist, informatics SME                 | STLT program staff              | None                        | STLT leadership             |
| Legal/privacy      | Legal counsel                 | Privacy specialist, governance lead                 | Participant counsel             | External counsel            | Authorized signatories      |
| Security           | Security architect            | Security engineer, IAM administrator                | Participant security staff      | Security product specialist | STLT/HDU security authority |
| Architecture       | Solution architect            | Data architect, interoperability architect          | STLT/HDU technical SMEs         | Vendor architect            | Sponsor technical lead      |
| Connectivity       | Integration engineer          | BA, data engineer                                   | Provider interface analyst      | Vendor specialist           | HDU architect               |
| Data mapping       | Data analyst                  | Terminology specialist, clinical SME, data engineer | Provider clinical/IT staff      | Vendor analyst              | STLT/HDU data lead          |
| Measure logic      | Clinical or public-health SME | Data engineer, CQL specialist, analyst              | STLT SMEs                       | Measure vendor if needed    | Sponsor/downstream consumer |
| Testing            | Test engineer                 | QA analyst, integration engineer, data engineer     | Provider/STLT testers           | Vendor QA                   | HDU QA lead                 |
| Training           | Training lead                 | Technical writer, analyst                           | Participant staff               | Vendor trainer if needed    | PMO                         |
| Operations         | Operations engineer           | Help desk, integration engineer, data analyst       | Provider and STLT support staff | Vendor support              | HDU operations lead         |
| Evaluation         | Evaluator                     | Statistician, data analyst, economist               | Participant data suppliers      | None                        | Sponsor                     |

---

# 8. Non-labor-cost matrix

| WBS ID / Area | Non-Labor Item                           | Cost Bearer      | Fixed / Variable     | Unit                    | Recurrence                 | Method                      |
| ------------- | ---------------------------------------- | ---------------- | -------------------- | ----------------------- | -------------------------- | --------------------------- |
| PMO.01–17     | Travel and facilitated meetings          | Sponsor          | Variable             | Trip/event              | One time/periodic          | Allowance                   |
| SHR.04.01     | External legal review                    | Portfolio        | Fixed/variable       | Legal package/hour      | One time                   | Public rate or quote        |
| SHR.08.01     | Conformance/testing tools                | Portfolio        | Fixed                | Tool/license            | Annual or project          | Existing contract/quote     |
| HDU.05        | IAM, logging, security tools             | HDU              | Existing/incremental | User/environment        | Recurring                  | Incremental run rate only   |
| HDU.07.02     | New endpoint fees                        | Sponsor/provider | Variable             | Endpoint                | One time + possible annual | Vendor quote                |
| HDU.08.02     | Measure or terminology licensing         | Sponsor/HDU      | Optional             | License                 | Annual/project             | Quote                       |
| HDU.09        | Test environment                         | HDU              | Variable             | Environment/month       | Implementation period      | Incremental cloud estimate  |
| HDU.12        | Compute, storage, monitoring, networking | HDU              | Usage-based          | Month/volume            | Four months                | Incremental run rate        |
| HDU.12.02     | Help-desk/ticketing tools                | HDU              | Existing             | Month                   | Four months                | Included unless incremental |
| PRV.07        | Provider vendor fees                     | Provider/sponsor | Variable             | Endpoint/vendor         | One time                   | Vendor quote                |
| EVL.02        | Survey or data-collection tools          | Sponsor          | Fixed                | Project                 | One time                   | Existing tool or allowance  |
| EVL.15        | Publication and dissemination            | Sponsor          | Fixed/variable       | Deliverable/event       | Closeout                   | Allowance                   |
| All           | Participant stipends or subawards        | Sponsor          | Step-fixed           | Organization            | Project                    | Policy decision             |
| All           | Contingency                              | Sponsor          | Variable             | Percentage or risk item | Project                    | Risk register-based         |

Existing infrastructure should not be priced as though newly purchased. Only incremental pilot usage should be included in sponsor cost. Existing platform value may be described as contributed infrastructure in the total economic-cost narrative.

---

# 9. Shared-cost allocation recommendations

| Shared Cost                    | Related WBS | Recommended Treatment                                         | Allocation Basis           | Alternative                     | Rationale                                                  |
| ------------------------------ | ----------- | ------------------------------------------------------------- | -------------------------- | ------------------------------- | ---------------------------------------------------------- |
| Portfolio governance framework | SHR.03.01   | Retain as central portfolio cost                              | None                       | Equal per pilot                 | Supports all pilots and is not driven by participant count |
| Model DUA templates            | SHR.04.01   | Central cost; charge only adaptation to pilot                 | Pilot-specific legal hours | Equal allocation                | Avoids recreating common legal work                        |
| Security baseline              | SHR.05.01   | Central cost                                                  | None                       | Per pilot adaptation            | Baseline is reusable                                       |
| Reference architecture         | SHR.06.01   | Central cost                                                  | None                       | Equal per pilot                 | Common asset                                               |
| Common conformance framework   | SHR.08.01   | Central cost                                                  | None                       | Allocate by use-case complexity | Reusable across pilots                                     |
| Training materials             | SHR.10.01   | Central development; pilot delivery charged locally           | Training cohorts           | Equal allocation                | Separates creation from use                                |
| Evaluation framework           | SHR.14.01   | Central development; pilot data collection and analysis local | Per pilot/participant      | Equal allocation                | Prevents double counting                                   |
| Common playbook template       | SHR.15.01   | Central cost                                                  | None                       | Equal allocation                | Pilot-specific findings only charged locally               |
| Portfolio PMO                  | Cross-pilot | Report separately                                             | By actual labor use        | Equal per pilot                 | Equal allocation may distort complex pilots                |
| Shared technical experts       | Cross-pilot | Allocate by recorded labor usage                              | Labor hours                | Equal per pilot                 | Most defensible allocation                                 |

For portfolio reporting, present both:

1. Direct pilot cost
2. Pilot cost plus allocated portfolio-shared cost

---

# 10. In-kind cost register

| Organization        | In-Kind Activity                                | WBS        | Labor Category                       | Unit                  | Model Treatment                     | Risk if Omitted                              |
| ------------------- | ----------------------------------------------- | ---------- | ------------------------------------ | --------------------- | ----------------------------------- | -------------------------------------------- |
| Sponsor             | Executive governance and SME review             | SPN.*      | Executive sponsor, public health SME | Hours/pilot           | Monetize separately or report hours | Understates federal effort                   |
| STLT                | Program leadership and workflow definition      | STLT.01–03 | Program lead, epidemiologist         | Hours                 | In-kind cost                        | Understates implementation burden            |
| STLT                | Legal/privacy/security review                   | STLT.04–05 | Counsel, privacy, security           | Hours/agreement       | In-kind sensitivity case            | May be critical-path work                    |
| STLT                | Operational use and feedback                    | STLT.12–14 | Analyst, epidemiologist              | Hours/month           | In-kind recurring                   | Understates operational sustainability       |
| Provider            | Technical and workflow inventory                | PRV.01–02  | PM, interface analyst, clinical SME  | Hours/network         | In-kind                             | Makes provider participation appear costless |
| Provider            | Legal/security review                           | PRV.04–05  | Counsel, privacy, security           | Hours/provider        | In-kind sensitivity case            | Material hidden burden                       |
| Provider            | Validation and testing                          | PRV.08–09  | Clinical SME, analyst, IT staff      | Hours/cycle           | Monetize separately                 | Major source of hidden cost                  |
| Provider            | Production support                              | PRV.12     | Interface analyst, data analyst      | Hours/month           | In-kind recurring                   | Understates operating cost                   |
| Vendor              | Included account/support effort                 | VND.*      | Vendor specialist                    | Hours                 | Disclose if included                | May mask fees in broader contracts           |
| Downstream consumer | Requirements and validation                     | DSC.*      | Program SME, measure SME             | Hours/use             | In-kind                             | Understates reuse cost                       |
| HDU                 | Existing infrastructure and executive oversight | HDU.*      | Executive, operations staff          | Allocated value/hours | Report separately                   | May overstate apparent cost efficiency       |

---

# 11. Double-counting review

| Potential Overlap                                                | WBS Elements                    | Risk            | Boundary Rule                                                                                   |
| ---------------------------------------------------------------- | ------------------------------- | --------------- | ----------------------------------------------------------------------------------------------- |
| Portfolio PMO versus pilot PMO                                   | SHR/shared PMO and PMO.*        | High            | Portfolio PMO handles cross-pilot governance; pilot PMO handles pilot execution only            |
| Common governance versus STLT governance                         | SHR.03 and STLT.03              | Moderate        | Shared team creates templates; STLT applies and approves them                                   |
| Model legal documents versus participant legal review            | SHR.04, STLT.04, HDU.04, PRV.04 | High            | Template development is central; review, negotiation, and execution are participant-specific    |
| Reference architecture versus pilot design                       | SHR.06 and HDU.06               | Moderate        | Shared team defines pattern; HDU adapts it to its environment                                   |
| Connectivity inventory versus onboarding                         | HDU.02 and HDU.10               | Moderate        | Inventory determines current state; onboarding manages participant execution                    |
| Existing-pathway configuration versus new endpoint configuration | HDU.07.01 and HDU.07.02         | High            | Each endpoint classified once as existing/configuration-only or materially new                  |
| Mapping versus measure logic                                     | HDU.08.01 and HDU.08.02         | Moderate        | Mapping addresses source-to-standard elements; logic addresses cohort/measure computation       |
| Data-quality rules versus testing                                | HDU.08.03 and HDU.09            | Moderate        | Rule creation/configuration is data work; execution and acceptance are testing                  |
| Testing versus remediation                                       | HDU.09.01–02 and 09.03–04       | High            | Testing identifies defects; remediation corrects them                                           |
| Provider onboarding versus provider technical labor              | HDU.10 and PRV.*                | Moderate        | HDU onboarding labor is funded delivery work; provider response labor is participant cost       |
| Stabilization versus four-month operations                       | HDU.11.02 and 12.01             | Moderate        | Stabilization covers initial go-live window; recurring operations begin after stabilization     |
| Operational monitoring versus evaluation                         | HDU.13 and EVL.13–14            | High            | HDU produces operational metrics; evaluator independently analyzes them                         |
| Vendor fees versus internal interface labor                      | HDU.07.02, PRV.07.02, VND.07.01 | High            | Record vendor invoice once and exclude any included implementation labor from internal estimate |
| Quality reports versus custom dashboards                         | HDU.08.04                       | High scope risk | Only standard reports/exports are included; custom UI is excluded                               |
| Secondary reuse demonstration versus production interface        | HDU.07.04 and DSC.*             | High scope risk | Demonstration ends at validated artifact/result; no production operations or new interface      |

---

# 12. Complexity and risk-adjustment register

| Workstream         | Factor                        | Low                         | Base                                  | High                                        | Effect                                | Stage 4 Treatment                                 |
| ------------------ | ----------------------------- | --------------------------- | ------------------------------------- | ------------------------------------------- | ------------------------------------- | ------------------------------------------------- |
| Connectivity       | Existing connection quality   | All six usable              | 75% usable, two require material work | Existing connections incomplete or unusable | Integration and schedule              | Adjust existing/new endpoint quantities           |
| Provider diversity | Number of EHR vendors         | One or two                  | Two to four                           | Five or six                                 | Mapping, testing, vendor coordination | Complexity factor on per-provider effort          |
| Data quality       | Required element availability | Mostly complete             | Several known gaps                    | Core elements absent/inconsistent           | Mapping and remediation               | Increase rule, testing, and remediation allowance |
| Measure logic      | Complexity                    | Simple percentage/threshold | Standard digital measure              | Complex attribution or exclusions           | SME and engineering effort            | Qualitative multiplier                            |
| Legal              | Agreement novelty             | Existing agreement/addendum | Moderate revisions                    | New multi-party agreement                   | Critical path and counsel cost        | Risk-adjusted hours                               |
| Security           | Existing approval alignment   | Accepted controls           | Additional evidence required          | New assessment or material gaps             | Schedule and engineering              | Separate security allowance                       |
| New endpoints      | Count                         | 0                           | 1–2                                   | More than 2                                 | Vendor and integration cost           | Scope gate; >2 excluded or separately funded      |
| Testing            | Scenario rigor                | Limited standard scenarios  | Full source-to-output testing         | Parallel baseline and extensive edge cases  | QA effort                             | Scenario quantity                                 |
| Remediation        | Defect count                  | Few minor defects           | Moderate priority defects             | Core source defects                         | Cost and schedule                     | Two-cycle capped allowance                        |
| Operations         | Ticket volume                 | Stable                      | Moderate incidents                    | Frequent source failures                    | Support labor                         | Monthly support range                             |
| Secondary use      | Demonstration complexity      | Static artifact             | Computed measure/result               | New production recipient                    | Integration cost                      | High case should trigger scope exclusion          |
| Evaluation         | Rigor                         | Descriptive                 | Mixed technical and utility analysis  | Outcome or causal evaluation                | Evaluator effort                      | Separate evaluation scenarios                     |
| Geography          | Distribution                  | Local participants          | Statewide                             | Multi-state                                 | Travel, coordination, governance      | Base limited to one STLT                          |
| Infrastructure     | Existing capacity             | No incremental capacity     | Minor incremental use                 | Material expansion required                 | Cloud/platform cost                   | High case separately funded                       |

---

# 13. Model-input register

| ID  | Input                             | Definition                                 | Unit               | Applies To           | Fixed / Variable | Suggested Base                  | Evidence Basis         | Validation Needed     |
| --- | --------------------------------- | ------------------------------------------ | ------------------ | -------------------- | ---------------- | ------------------------------- | ---------------------- | --------------------- |
| Q01 | Number of pilots                  | Portfolio pilots                           | Pilots             | Shared allocation    | Variable         | 3–4                             | User decision          | Final portfolio       |
| Q02 | Intermediaries per pilot          | Participating HIE/HDU                      | Organization       | HDU work             | Step-fixed       | 1                               | User decision          | Confirm               |
| Q03 | STLTs per pilot                   | Jurisdiction participants                  | Organization       | STLT work            | Step-fixed       | 1                               | User decision          | Confirm               |
| Q04 | Provider networks                 | Contributing provider organizations        | Network            | Onboarding           | Variable         | 6                               | Updated assumption     | Confirm roster        |
| Q05 | Existing connectivity percentage  | Sources already connected                  | Percentage         | Integration          | Variable         | ≥75%                            | User decision          | Technical inventory   |
| Q06 | Existing pathways                 | Configuration-only source connections      | Pathway            | HDU.07.01            | Variable         | Derived from Q04/Q05            | Assumption             | Validate              |
| Q07 | New endpoint count                | Materially new configurations              | Endpoint           | HDU/VND              | Variable         | 0–2                             | User decision          | Validate              |
| Q08 | EHR/vendor count                  | Distinct technologies                      | Vendor             | Mapping/testing      | Variable         | TBD                             | Not known              | Readiness assessment  |
| Q09 | Condition domains                 | Distinct clinical domains                  | Domain             | Data/SME             | Fixed            | 1                               | User decision          | Select domain         |
| Q10 | Primary measures/workflows        | Required operational measure               | Measure            | Logic/testing        | Fixed            | 1                               | User decision          | Select measure        |
| Q11 | Data elements                     | Minimum dataset size                       | Element            | Mapping              | Variable         | Approximately 15–25 provisional | Thin-slice inference   | Final specification   |
| Q12 | Source types                      | FHIR, ADT, files, etc.                     | Source type        | Mapping              | Variable         | TBD                             | Technical brief        | Inventory             |
| Q13 | Operational outputs               | Fully operational recipient products       | Output             | Integration          | Fixed            | 1                               | User decision          | Define                |
| Q14 | Secondary demonstrations          | Non-production reuse demonstrations        | Use                | Integration          | Fixed            | 1                               | User decision          | Define                |
| Q15 | Environments                      | Development, test, production              | Environment        | Technical work       | Variable         | Existing environments           | User decision          | HDU confirmation      |
| Q16 | Test scenarios                    | End-to-end scenarios                       | Scenario           | Testing              | Variable         | TBD                             | Test plan              | Define                |
| Q17 | Remediation cycles                | Maximum funded cycles                      | Cycle              | Testing              | Fixed            | 2                               | User decision          | Confirm in agreements |
| Q18 | Expected defects                  | Priority defects per source/interface      | Defect             | Remediation          | Variable         | TBD                             | No strong evidence     | Pilot risk assumption |
| Q19 | Live-operation duration           | Production pilot period                    | Month              | Operations           | Fixed            | 4                               | User decision          | Confirm               |
| Q20 | Total project duration            | Mobilization through closeout              | Month              | PMO                  | Fixed            | 12                              | Updated assumption     | Confirm               |
| Q21 | Reporting frequency               | Operational output cadence                 | Cycle/month        | Operations           | Variable         | TBD                             | Workflow-dependent     | STLT decision         |
| Q22 | User groups                       | Distinct training audiences                | Group              | Training             | Variable         | TBD                             | Participation model    | Confirm               |
| Q23 | Agreements                        | Number of legal instruments                | Agreement          | Legal                | Variable         | TBD                             | Governance model       | Counsel review        |
| Q24 | Participant stipends              | Funding per provider or STLT participant   | Organization       | Sponsor cost         | Step-fixed       | TBD                             | Policy decision        | Sponsor               |
| Q25 | Vendor fees                       | Endpoint implementation/license charges    | Endpoint/vendor    | Vendor cost          | Variable         | Quote required                  | Vendor-specific        | Quote                 |
| Q26 | Incremental cloud cost            | Added compute/storage/logging              | Month              | Operations           | Variable         | TBD                             | Existing platform      | HDU estimate          |
| Q27 | PMO staffing                      | Labor mix and utilization                  | FTE/month or hours | PMO                  | Fixed/recurring  | TBD                             | Bottom-up              | Staffing plan         |
| Q28 | HDU staffing                      | Labor by work package                      | Hours/category     | HDU                  | Fixed/variable   | TBD                             | Bottom-up              | HDU estimate          |
| Q29 | STLT funded labor                 | Reimbursed jurisdiction effort             | Hours/category     | STLT                 | Variable         | TBD                             | Policy decision        | Award design          |
| Q30 | Provider in-kind hours            | Internal participant effort                | Hours/network      | Economic cost        | Variable         | TBD                             | Weak public evidence   | Time reporting        |
| Q31 | Evaluation metrics                | Technical, burden, utility, reuse measures | Metric             | EVL                  | Variable         | TBD                             | Common framework       | Final plan            |
| Q32 | Evaluation participants           | Organizations supplying evidence           | Organization       | EVL                  | Variable         | All material participants       | Scope                  | Confirm               |
| Q33 | Travel events                     | In-person meetings or site visits          | Trip/event         | PMO/EVL              | Variable         | TBD                             | Delivery approach      | Sponsor               |
| Q34 | Portfolio shared cost             | Central reusable asset cost                | Dollars            | Portfolio allocation | Fixed            | TBD                             | Portfolio design       | Stage 4               |
| Q35 | Allocation method                 | Treatment of shared cost                   | Method             | Reporting            | Policy           | Actual labor/equal/central      | Stage 3 recommendation | Sponsor               |
| Q36 | Contingency method                | Risk allowance approach                    | Percent/risk item  | Sponsor cost         | Variable         | Risk-based                      | Best practice          | Stage 4               |
| Q37 | Loaded labor rates                | Fully burdened rates by category           | Dollars/hour       | All labor            | Variable         | TBD                             | Contract/rate source   | Stage 4               |
| Q38 | In-kind valuation rate            | Proxy internal loaded rates                | Dollars/hour       | Economic cost        | Variable         | TBD                             | Labor proxy            | Stage 4               |
| Q39 | Existing infrastructure treatment | Whether contributed platform is monetized  | Policy             | Economic cost        | Policy           | Report separately               | Scope assumption       | Sponsor               |
| Q40 | Optional extensions               | Separate add-on work packages              | Extension          | Sensitivity          | Optional         | Excluded                        | User decision          | Define separately     |

---

# 14. Decisions and unresolved questions

| ID  | Issue                          | Provisional Treatment                                     | Effect on WBS                             | Effect on Cost Model     | Priority | Validation Source        |
| --- | ------------------------------ | --------------------------------------------------------- | ----------------------------------------- | ------------------------ | -------- | ------------------------ |
| D01 | Condition selection            | One domain                                                | Limits dataset and SMEs                   | Major cost constraint    | High     | Sponsor/STLT             |
| D02 | Primary measure/workflow       | One operational workflow                                  | Limits logic and testing                  | Major cost constraint    | High     | Sponsor/STLT             |
| D03 | Operational downstream use     | STLT/public-health output                                 | Defines production path                   | Major                    | High     | Pilot charter            |
| D04 | Secondary use                  | Demonstration only                                        | Excludes full interface and operations    | Prevents scope expansion | High     | Downstream consumer      |
| D05 | Provider roster                | Six networks                                              | Establishes onboarding quantity           | Major                    | High     | HDU inventory            |
| D06 | Existing connectivity          | Minimum 75%                                               | Limits greenfield integration             | Major                    | High     | Readiness assessment     |
| D07 | New endpoint count             | Maximum two                                               | Creates hard scope gate                   | Major                    | High     | Technical inventory      |
| D08 | Dataset size                   | Approximately 15–25 elements pending design               | Controls mapping and quality rules        | Moderate-major           | High     | Requirements process     |
| D09 | Existing infrastructure        | Reuse hosting, IAM, MPI, audit, and operations            | Excludes platform build                   | Major                    | High     | HDU evidence             |
| D10 | Legal instrument model         | Prefer existing agreements/addenda                        | Reduces negotiation                       | Potential critical path  | High     | Counsel                  |
| D11 | Provider funding               | Track in kind; consider capped stipends                   | Creates sponsor/economic-cost distinction | Moderate                 | High     | Award policy             |
| D12 | STLT funding                   | Direct award or subaward assumed                          | Determines reimbursed labor               | Moderate                 | High     | Funding design           |
| D13 | HRSA/NCQA role                 | Advisory or secondary validator                           | No production integration                 | Controls downstream cost | Medium   | Partner confirmation     |
| D14 | Measure licensing              | Avoid where possible; quote separately if required        | Adds non-labor line                       | Moderate                 | Medium   | Measure owner            |
| D15 | Reporting cadence              | Pending                                                   | Affects operations and quality reporting  | Moderate                 | Medium   | STLT workflow            |
| D16 | Evaluation rigor               | Implementation, technical, burden, and utility evaluation | Excludes long-term outcomes evaluation    | Moderate                 | High     | Evaluation plan          |
| D17 | Portfolio-cost allocation      | Retain centrally and show allocated view separately       | Adds dual reporting                       | Moderate                 | High     | Sponsor                  |
| D18 | High-case connectivity failure | Treat as scope change or optional extension               | Avoids uncapped integration               | Major                    | High     | Readiness gate           |
| D19 | Defects after two cycles       | Document and close, unless separately funded              | Caps remediation work                     | Major                    | High     | Participation agreements |
| D20 | Custom dashboards              | Excluded                                                  | Use reports and existing tools            | Avoids application build | High     | Charter                  |

---

# 15. Stage 4 readiness assessment

## Overall readiness

The WBS is ready to be converted into a pro forma cost model. It contains:

* Defined organization ownership
* Fixed, variable, recurring, and in-kind classification
* Scaling units
* Sponsor-versus-economic-cost distinctions
* Shared-cost treatment
* Non-labor inputs
* Cost-estimating methods
* Complexity factors
* Double-counting boundaries

## Work packages with comparatively strong benchmark support

* Program management
* Participant onboarding
* Interface and endpoint configuration
* General integration testing
* Four-month operational support
* Evaluation and reporting
* Training and technical assistance
* Vendor implementation charges, once quotes are obtained

## Work packages requiring bottom-up labor estimates

* STLT workflow definition
* Governance and decision procedures
* Legal and privacy review
* Pilot architecture adaptation
* Minimum dataset mapping
* Measure logic
* Data-quality rule configuration
* Provider source validation
* Secondary-use demonstration
* Sustainability assessment

## Work packages requiring vendor quotes

* Up to two new endpoint configurations
* Any EHR-specific export or API fees
* Measure licensing
* Proprietary terminology or validation tools
* Incremental interface maintenance fees
* Material cloud or storage expansion

## Decisions that most strongly affect the cost model

1. Whether the six provider networks truly meet the 75% connectivity threshold
2. Number of distinct EHR vendors and source types
3. Which chronic domain and measure are selected
4. Whether existing agreements can be amended
5. Number and complexity of defects identified
6. Whether one or two new endpoints are required
7. Amount of provider and STLT effort reimbursed
8. Incremental intermediary operations cost
9. Evaluation rigor
10. Allocation of portfolio-shared costs

## Costs to display separately

Stage 4 should calculate and display:

* Direct sponsor-funded pilot cost
* Allocated portfolio-shared cost
* Participant-funded or unreimbursed cost
* In-kind labor
* Contributed intermediary infrastructure
* Optional-extension cost
* Total economic cost

## Greatest omission risks

* Provider clinical and IT labor
* STLT legal and governance labor
* Existing infrastructure contribution
* Vendor fees embedded in other contracts
* Source-specific data correction
* Operational support after the pilot
* Cost of unresolved defects
* Measure licensing
* Security exceptions
* Portfolio-level work incorrectly repeated in each pilot

## Greatest double-counting risks

* Shared versus pilot PMO
* Common architecture versus intermediary design
* Legal templates versus legal negotiations
* Onboarding versus participant labor
* Mapping versus testing
* Testing versus remediation
* Stabilization versus operations
* Operational metrics versus evaluation
* Vendor fees versus internal implementation labor
* Secondary-use demonstration versus a second production implementation

The most consequential Stage 4 modeling rule should be:

> Price the intermediary’s incremental pilot delta, not the full economic value or replacement cost of the existing HDU platform.

That rule, together with the 75% connectivity threshold, two-endpoint cap, one-domain limit, one operational workflow, and four-month operating period, is what keeps the WBS consistent with a target near $3 million per pilot.

---

# Prompt

What do you recommend that I review carefully before we proceed to create the pro forma model?

# Response

Before building the pro forma, I recommend a focused review of the items below. The first six materially determine whether the model will stay near the $3 million target.

## 1. Confirm the pilot’s exact clinical thin slice

Lock down:

* The single condition domain
* The single primary measure or analytic workflow
* The cohort definition
* The measurement period
* Required stratifications
* The minimum dataset
* The authoritative measure specification or clinical logic

This decision drives data-element count, terminology work, mapping, testing, clinical SME effort, and potential licensing. The model should not proceed with a generic placeholder such as “hypertension or diabetes,” because those choices can produce materially different implementation costs.

A good signoff artifact would be a one-page **Use Case Definition** containing the cohort, numerator, denominator, exclusions, required elements, and expected output.

## 2. Validate that the 75% connectivity assumption is real

This is probably the most important factual validation.

For each of the six provider networks, confirm:

* What data are already connected to the intermediary
* Whether the connection is operational or merely contractually available
* Whether it contains the required data elements
* Whether the intermediary can reuse the data for this purpose
* Whether the source is FHIR, HL7 v2, C-CDA, flat file, claims, or another format
* Whether vendor assistance is required
* Whether the connection is production-quality

“Connected” should mean more than having an existing interface. A feed that lacks blood pressure components, A1c values, provenance, or usable patient attribution may still require substantial implementation.

I would classify each source as:

| Classification | Meaning                                                                   |
| -------------- | ------------------------------------------------------------------------- |
| Ready          | Existing connection and required data are usable with minor configuration |
| Configurable   | Existing connection exists but requires mapping or filtering              |
| Materially new | New endpoint or significant vendor configuration required                 |
| Out of scope   | Cannot be made usable within the pilot constraints                        |

The base model should only be accepted if no more than two sources fall into “materially new.”

## 3. Confirm the provider-network and system counts

The model currently uses six provider networks, but cost will be driven more directly by:

* Number of distinct EHR platforms
* Number of EHR instances
* Number of source systems
* Number of interfaces
* Number of data formats
* Number of endpoint configurations
* Number of legal entities

Six networks using one shared EHR instance are very different from six networks using six vendors and multiple local instances.

The cost model should therefore include both:

* Provider-network count
* Distinct technical-source count

## 4. Define what “one fully operational downstream use” means

You should specify:

* Who receives the operational output
* What format they receive
* How frequently it is delivered
* Whether it is line-level, de-identified, or aggregate
* Whether the recipient accesses the intermediary or receives an extract
* Whether production monitoring and support are required
* What constitutes successful operational use

The original chronic pilot contemplated several possible consumers and reuse patterns.  The revised model should select exactly one production pathway.

For example:

> The intermediary will produce a monthly, jurisdiction-approved line-level or aggregate chronic surveillance dataset for use by the participating STLT program during four months of live operations.

That is more estimable than a general requirement to “support CDC and STLT surveillance.”

## 5. Bound the second downstream use

The second use should be explicitly described as a demonstration, not a production implementation.

Confirm whether it will be:

* A computed quality-measure result
* A FHIR MeasureReport
* A sample HRSA-aligned output
* A validated transformed dataset
* A one-time analytic extract
* A technical feasibility demonstration

Also define what is excluded:

* No new production interface
* No production SLA
* No recurring support
* No separate dashboard
* No recipient-specific data pipeline
* No extensive measure certification

Without this boundary, the second use could quietly become a second full implementation.

## 6. Verify existing intermediary capabilities

Require the intermediary to provide evidence that the following are already operational:

* Hosting
* Identity and access management
* Master patient index or attribution method
* Audit logging
* Monitoring
* Backup and recovery
* Secure development and test environments
* Production support
* Data normalization capability
* Existing provider connectivity
* Data lineage or provenance
* Operational incident management

Also identify which capabilities require incremental work.

The pro forma should distinguish:

* Existing platform capability included in the intermediary’s normal operations
* Incremental configuration funded by the pilot
* Contributed infrastructure reported as in-kind economic value
* New platform development, which should be excluded

## 7. Review the minimum dataset carefully

The provisional range of approximately 15–25 elements is useful, but it should be validated before costing.

For each element, identify:

* Source system
* Standard representation
* Required terminology
* Required versus optional status
* Completeness expectation
* Whether transformation is required
* Whether it is needed for the primary measure, stratification, provenance, or evaluation

Remove elements that do not directly support:

1. Cohort identification
2. Measure calculation
3. Required stratification
4. Provenance
5. Data-quality assessment

Every additional element can multiply mapping and validation effort across source types.

## 8. Review legal and data-access assumptions

Confirm:

* Whether existing DUAs can be amended
* Whether provider-to-HDU authority already covers the use
* Whether STLT access requires a new agreement
* Whether federal access is included
* Whether the second downstream use requires a separate agreement
* Whether line-level data are permitted
* Retention and redisclosure requirements
* Whether a business associate agreement is implicated
* Whether consent is relevant
* Whether each provider is a separate contracting entity

Legal effort is difficult to estimate until the agreement structure is known. A single addendum to an existing statewide framework is materially different from seven or eight independent agreements.

## 9. Decide what participant work will be funded

The model needs an explicit policy for:

* STLT labor
* Provider labor
* Provider stipends
* Vendor fees
* Intermediary subaward
* Legal expenses
* Security-review time
* Clinical SME participation
* Evaluation-data submission

At minimum, decide whether each category is:

* Reimbursed
* Covered through a fixed subaward
* Included in an intermediary agreement
* Contributed in kind
* Eligible only with prior approval

Otherwise, the pro forma may meet the sponsor target only by moving substantial costs to participants.

## 10. Review testing and remediation boundaries

The two-cycle cap is valuable, but the model needs a more precise definition.

Confirm:

* What constitutes a remediation cycle
* Whether the cycle is per provider, interface, or pilot
* Which severity levels must be corrected
* Who bears provider-side defect costs
* Who bears vendor-side defect costs
* What happens to unresolved defects
* Whether failed participants may be removed
* Whether replacement participants are allowed

I recommend:

> Each source pathway receives up to two coordinated remediation cycles. After the second cycle, unresolved findings are documented, and additional correction requires separate approval and funding.

## 11. Confirm the schedule and phase durations

The model assumes 12 months total and four months live. Review whether the remaining eight months realistically accommodate:

* Mobilization
* Partner confirmation
* Agreements
* Requirements
* Readiness assessment
* Design
* Configuration
* Mapping
* Testing
* Two remediation cycles
* Training
* Go-live
* Evaluation and closeout

A practical draft schedule might be:

| Phase                         |                                               Months |
| ----------------------------- | ---------------------------------------------------: |
| Mobilization and requirements |                                                  1–2 |
| Governance, legal, and design |                                                  2–4 |
| Configuration and mapping     |                                                  3–6 |
| Testing and remediation       |                                                  6–8 |
| Go-live preparation           |                                                    8 |
| Live operations               |                                                 9–12 |
| Evaluation                    | Begins before go-live and continues through closeout |

The legal and technical work will need to overlap. A purely sequential model likely will not preserve four months of operations.

## 12. Review the evaluation burden

Define exactly what will be measured:

* Data completeness
* Conformance
* Timeliness
* Operational reliability
* Provider burden
* STLT usefulness
* Reuse demonstration
* Implementation cost
* Sustainability

Avoid adding an outcomes evaluation that requires demonstrating changes in hypertension control or population health during four months. The pilot can credibly assess whether the data support the measure and are useful for surveillance; it likely cannot attribute clinical outcome changes to the pilot within the available timeframe.

## 13. Review portfolio-shared versus pilot-specific work

Before costing, mark every shared work package as one of:

* Built once at portfolio level
* Adapted per pilot
* Delivered separately per pilot
* Reused without incremental cost

Pay particular attention to:

* PMO
* Governance framework
* Legal templates
* Security requirements
* Reference architecture
* Conformance tooling
* Training materials
* Evaluation framework
* Playbook structure
* Communications

The pro forma should show:

1. Direct pilot cost
2. Allocated shared cost
3. Portfolio central cost

This will prevent the same work from being counted three or four times.

## 14. Review optional exclusions

Ensure the following remain explicitly outside the base model unless deliberately restored:

* Custom dashboards
* Additional condition domains
* Additional measures
* More than two new endpoints
* New MPI or identity platform
* New IAM platform
* New cloud environment
* Claims or payer integration
* TEFCA connectivity
* Referral-loop implementation
* CBO integration
* AI development
* Advanced predictive analytics
* New terminology service
* More than four months of operation
* Production implementation of the second downstream use

These should appear in an optional-cost schedule, not disappear entirely.

# Recommended review order

I would conduct the review in this sequence:

1. **Clinical scope:** condition, measure, cohort, dataset.
2. **Participant readiness:** six networks, EHRs, interfaces, connectivity.
3. **Outputs:** operational use and secondary demonstration.
4. **Intermediary baseline:** existing versus incremental capability.
5. **Legal and security:** agreement and approval pathways.
6. **Funding policy:** reimbursed versus in-kind effort.
7. **Testing and acceptance:** defect, remediation, and go-live rules.
8. **Schedule and evaluation:** confirm feasibility.
9. **Shared-cost allocation:** portfolio versus pilot.
10. **Optional scope:** confirm exclusions.

# Minimum decisions needed before Stage 4

The pro forma can be built with assumptions, but it will be substantially more defensible once these ten inputs are settled:

| Decision                           | Why It Matters                      |
| ---------------------------------- | ----------------------------------- |
| Selected condition                 | Determines clinical and data scope  |
| Selected primary measure/workflow  | Determines logic and testing        |
| Minimum dataset                    | Determines mapping workload         |
| Six provider networks              | Determines participant count        |
| Distinct EHR/source systems        | Determines technical complexity     |
| Existing versus new endpoint count | Determines integration cost         |
| Operational downstream output      | Determines production scope         |
| Secondary-use artifact             | Prevents second implementation      |
| Participant funding policy         | Separates sponsor and economic cost |
| Portfolio shared-cost treatment    | Prevents duplicate costing          |

My strongest recommendation is to review the **connectivity evidence and exact measure definition** most carefully. Those are the two areas most likely to make a $3 million pilot appear feasible on paper but materially exceed the target during implementation.

---

# Prompt

Given that we only have a year for the pilots, are there things from the pilot description that you would flag as unlikely be able to be finished and included even without answers to the minimum decisions you identified?

# Response 

Yes. Even without resolving the remaining design decisions, several elements in the current pilot description are either incompatible with the agreed one-year thin-slice model or too risky to promise as completed outcomes.

The brief itself acknowledges that the timeline is too short for net-new connectivity and recommends accelerating existing work.  With four months reserved for live operations, the pilot effectively has about eight months for selection, agreements, design, configuration, mapping, testing, and launch.

## Items I would remove from the one-year commitment

| Pilot-description element                                           | Assessment                                | Recommended treatment                                                                                                                                                                                  |
| ------------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Comparing multiple intermediary models                              | **Incompatible with the revised design**  | Remove from this pilot. One intermediary cannot demonstrate or compare HIE/HDU, HCCN, QHIN/vendor, and MENDS-related pathways. Treat comparison as a portfolio-level synthesis across separate pilots. |
| Demonstrating more than one intermediary-enabled pathway            | **Incompatible**                          | Replace with demonstrating one reusable pathway through the selected intermediary.                                                                                                                     |
| Optional closed-loop referral pilot                                 | **Highly unlikely**                       | Exclude entirely from the base period. It adds CBOs, referral platforms, consent, Gravity mapping, status return, and workflow redesign.                                                               |
| Site-selected extension domain                                      | **Unlikely and unnecessary**              | Remove. Restrict the pilot to one common condition and one primary workflow.                                                                                                                           |
| Three substantive downstream outputs—CDC, HRSA, and digital quality | **Unlikely**                              | Require one operational STLT/public-health output and one bounded reuse demonstration. Do not promise three operational or equivalent products.                                                        |
| Broad national scaling or adoption                                  | **Not achievable as an outcome**          | Produce preliminary scale recommendations and reusable artifacts; do not claim the pilot will establish a nationally scalable operating model.                                                         |
| AI-ready data or advanced analytics                                 | **Not demonstrable within the pilot**     | Limit to documenting whether the resulting data have basic prerequisites for future analytics. No AI implementation or validated AI readiness claim.                                                   |
| Meaningful provider burden reduction                                | **Difficult to demonstrate conclusively** | Measure implementation effort and perceived burden; do not promise proven reporting-cost reduction unless an existing parallel submission can actually be retired.                                     |
| Clinical or population outcome improvement                          | **Not evaluable in four live months**     | Exclude changes in hypertension control, diabetes control, or health outcomes as pilot success criteria.                                                                                               |
| Robust sustainability implementation                                | **Unlikely**                              | Deliver a sustainability assessment and continuation decision, not a completed long-term operating and funding model.                                                                                  |

The original brief describes comparing several intermediary types and demonstrating that more than one pathway can create a conformant product.  That directly conflicts with the new assumption of one intermediary per pilot. The conflict should be corrected in the brief before procurement or costing.

## Items that may fit only in a reduced form

### 1. The “shared trust layer”

The complete concept includes conformance, completeness, timeliness, provenance, auditability, longitudinal continuity, transparent scoring, and remediation guidance.  A full, portable trust framework that is comparable across jurisdictions is too ambitious for one intermediary and one year.

A feasible minimum would include:

* Automated conformance checks for the selected dataset
* Required-element completeness
* Event-to-availability timeliness
* Source provenance
* Access and transformation logging
* A standard validation report

Do not promise:

* A validated national trust-scoring methodology
* Cross-jurisdiction comparability
* Complex composite scores
* Longitudinal completeness certification
* Broad publication of provider-level scorecards

The current slide language refers to transparent trust scoring that enables cross-site comparison.  With one STLT and one intermediary, the pilot can test score generation, but not establish that the scores support valid national or cross-jurisdiction comparison.

### 2. A fully standardized “dual-use” dataset

A minimum dataset and mapping guide are feasible. A dataset proven equally fit for CDC surveillance, HRSA reporting, and NCQA digital measurement is less certain.

Within one year, the pilot can reasonably show:

* One common underlying dataset
* One operational public-health use
* One second artifact or measure result produced from the same dataset
* Documented gaps preventing broader reuse

It should not promise that the dataset is fully validated for all three federal and quality ecosystems.

### 3. Digital measure execution

Executing one measure may be feasible when:

* The measure is already specified
* Licensing is resolved
* The intermediary has an existing CQL or measure engine
* The necessary data are already present
* Certification or formal audit is not required

A new measure-engine implementation, measure certification, or full concordance study would be unlikely to fit.

The brief currently references QI-Core/CQL and several possible CDC, HRSA, and quality outputs.  That should be narrowed to “execute or generate one representative measure or analytic artifact.”

### 4. Deduplication and longitudinal records

Basic use of an existing MPI is feasible. Proving comprehensive longitudinal completeness across six provider networks is not.

The pilot can test:

* Existing identity resolution
* Duplicate detection within the intermediary
* Attribution or cohort assignment
* Known match limitations

It should not promise:

* A complete longitudinal patient record
* New privacy-preserving linkage technology
* Validated matching performance across all relevant care settings
* Resolution of incomplete source coverage

### 5. Six provider networks

Six networks may fit only when most are genuinely ready. Even with 75% existing connectivity, six organizations still create six sets of contacts, approvals, mappings, validation activities, and operational dependencies.

I would distinguish:

* **Target:** six provider networks
* **Minimum successful operational cohort:** four
* **Stretch:** all six

This avoids making the entire pilot fail because one or two networks cannot complete internal approvals or vendor work.

## Items that are feasible but should be described carefully

These outputs appear realistic within one year:

* Minimum dataset specification
* FHIR mapping guide
* One configured intermediary pathway
* One operational chronic surveillance data product
* One bounded second-use demonstration
* Basic conformance and data-quality reports
* Provider-network readiness assessments
* Two capped remediation cycles
* Four months of live operation
* Pilot-specific implementation documentation
* Preliminary scale and sustainability recommendations

The deliverables section also includes an implementation playbook and MENDS-informed readiness framework.  Both can be completed, but they should be framed as **version 1 pilot outputs**, not validated national guidance. Four months of operations in one jurisdiction will not establish that the methods work across materially different intermediaries or jurisdictions.

## Evaluation claims that should be softened

The current brief proposes measuring data-quality improvement, reuse efficiency, reduced duplicated submissions, and decision/action utility.  I would revise the claims as follows:

| Current ambition                            | One-year feasible formulation                                                                                     |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Demonstrate data-quality improvement        | Document baseline and end-of-pilot changes for selected elements                                                  |
| Demonstrate reduced duplicative submissions | Identify integrations or extracts that could be reused or avoided; confirm actual retirement only where it occurs |
| Prove reuse efficiency                      | Measure incremental effort required to create the second output                                                   |
| Demonstrate public-health action            | Document whether the output supported defined surveillance questions or a specific decision                       |
| Establish national scalability              | Identify prerequisites, costs, barriers, and adaptations for scaling                                              |
| Enable cross-site comparison                | Assess whether common rules can be applied across participating sources within one intermediary                   |
| Demonstrate outcome improvement             | Not included; evaluate data and workflow capability instead                                                       |

## Schedule-related risks that exist regardless of the final measure

### Partner selection and contracting

The pilot descriptions imply that governance and DUAs may be established in approximately 30 days.  That is an eligibility aspiration, not a reliable planning assumption. If participants are not preselected and agreements are not substantially reusable, contracting alone could consume several months.

The one-year plan should require at award:

* Named STLT and intermediary
* Identified provider networks
* Existing contractual relationships
* Existing data-sharing authority or a clearly defined addendum path
* Evidence of endpoint availability
* Named operational teams

### Sequential design

Pressure-testing the dataset broadly with STLTs, HCCNs, HRSA, NCQA, and quality stakeholders before recruitment is unlikely to fit if treated as a consensus process.  Requirements refinement, partner onboarding, governance, and technical assessment will need to occur concurrently.

### Four months of live operations

To preserve four months of live operations, go-live must occur around the end of month eight. Any scope requiring:

* Net-new contracting
* More than two new endpoints
* New infrastructure
* New measure-engine deployment
* Novel linkage
* New cross-agency production access

should be automatically deferred if not resolved by an early gate, probably no later than months two or three.

## Recommended revised definition of success

I would define successful completion as:

> Within 12 months, one STLT and one existing intermediary use predominantly existing provider connections to produce and operate for four months a standardized dataset for one chronic condition and one primary surveillance or measurement workflow. The intermediary applies a minimum trust-control package, delivers one operational public-health output, and demonstrates one additional reuse from the same data. The pilot documents implementation effort, data quality, timeliness, usability, incremental reuse effort, unresolved gaps, and prerequisites for scale.

That definition preserves the central strategic proof without promising national standardization, broad outcome improvement, multiple operational consumer integrations, or an expanded referral ecosystem.

## My strongest flags

Before the brief is used to solicit or fund work, I would explicitly revise these four statements:

1. **Remove the expectation to compare or demonstrate multiple intermediary models.**
2. **Replace CDC + HRSA + NCQA multi-consumer execution with one operational use plus one demonstration.**
3. **Reframe cross-site comparability and national scaling as learning objectives, not proven outcomes.**
4. **Move closed-loop referrals, site-selected extensions, advanced analytics, payer data, TEFCA, and multi-source linkage to separately funded future phases.**

The project can finish meaningful work in a year, but it should be positioned as an **operational proof with reusable evidence**, not as completion of the full future-state chronic surveillance model.

---

# Prompt

If we want the pilot participants to exchange data for 6 to 9 months, what would you change about your feedback and recommendations?

# Response

A 6–9 month exchange period materially changes the pilot from an implementation-heavy project into a **rapid activation of preexisting capabilities**. In a 12-month period, it leaves only:

* **Six-month exchange:** roughly four to five months to mobilize and launch, with one to two months for final analysis and closeout.
* **Nine-month exchange:** roughly two to three months to launch, with evaluation occurring largely during operations.

That does not make the pilot impossible, but it makes several readiness assumptions non-negotiable.

# What I would change in the recommendations

## 1. Tighten the definition of an eligible participant

The earlier recommendation of at least 75% existing connectivity is probably sufficient for a six-month exchange period, but not necessarily for nine months.

I would use:

| Exchange target | Minimum readiness standard                                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Six months      | At least 75% of required source pathways operational; no more than two materially new configurations                                        |
| Nine months     | Nearly all required pathways operational at selection; ideally no more than one configuration-only gap and no genuinely greenfield endpoint |

For a nine-month exchange, providers should not merely have a contractual or technical relationship with the intermediary. The relevant data must already be flowing in production and be legally reusable for the pilot purpose.

The participant selection gate should require evidence of:

* Current production feeds
* Required data-element availability
* Existing data-sharing authority or a short-form addendum path
* Identified technical and program staff
* Existing test and production environments
* Ability to begin testing almost immediately

## 2. Treat partner selection as a pre-award activity

Previously, partner confirmation was included as an early pilot activity. With six to nine months of exchange, substantial recruitment and readiness screening must occur before the 12-month implementation clock begins.

By award or formal launch, the pilot should already have:

* One named intermediary
* One named STLT
* The six candidate provider networks
* A selected condition domain
* A selected primary workflow
* A draft minimum dataset
* A clear operational recipient
* A preliminary legal-pathway assessment
* Evidence that the connectivity threshold is met

The CIO engagement and pilot-design process already anticipates securing commitment, mobilizing the team, refining the design, and approving a charter before implementation launch.  For a long operating period, those activities cannot consume the first several months of the funded pilot.

## 3. Move more design work to the portfolio level

The longer exchange period strengthens the case for developing common assets before individual pilots begin.

The portfolio should provide at launch:

* Charter template
* Governance model
* Model agreements
* Security requirements
* Reference architecture
* Standard readiness assessment
* Basic conformance framework
* Evaluation instruments
* Testing templates
* Operations-report template

Pilot participants should adapt these assets rather than develop them.

This is consistent with the cross-pilot framework, which already anticipates shared standards, governance, privacy, security, infrastructure, and portable implementation artifacts. 

## 4. Reduce technical implementation scope further

Longer operations do not create more time overall. They reduce the time available for implementation.

For a six-month exchange, I would retain:

* One condition
* One primary workflow
* One operational output
* One bounded reuse demonstration
* Up to two materially new endpoint configurations

For a nine-month exchange, I would change the endpoint assumption:

* Prefer zero new endpoints
* Permit one endpoint only when it is a straightforward activation of an existing certified or vendor-supported capability
* Treat a second material endpoint as an optional extension or backup source

The project should not attempt to stand up and stabilize two genuinely new endpoints within the first two or three months.

## 5. Replace “two remediation cycles” with time-boxed gates

Two remediation cycles remain sensible, but they should not be allowed to delay operations.

A better structure would be:

* **Pre-go-live remediation:** correct defects that prevent minimum viable exchange.
* **Early-operation remediation:** correct high-priority defects during the first one or two operating months.
* **Later defects:** document, prioritize, and resolve only when they do not threaten the operating period.

For nine months of exchange, the pilot may need to begin operations with known noncritical data-quality limitations rather than waiting for a theoretically complete dataset.

Success should be based on:

* Stable exchange of the minimum required data
* Transparent disclosure of known gaps
* Measurable improvement during operations
* Fitness for the selected workflow

It should not require every optional element or every source to be perfect before go-live.

## 6. Use a minimum viable dataset at launch

The earlier estimate of approximately 15–25 elements may still work for six months, but a nine-month exchange period argues for a staged dataset:

### Initial operational dataset

Only elements necessary for:

* Cohort identification
* Primary measure or analytic workflow
* Essential stratification
* Provenance
* Timeliness
* Basic quality assessment

### Post-launch improvements

During operations, participants may improve:

* Race and ethnicity completeness
* Organization attribution
* Medication context
* Secondary stratifications
* Optional provenance detail
* Noncritical clinical elements

This creates a useful evaluation opportunity: the pilot can measure whether data quality improves through an intermediary-managed feedback process.

## 7. Keep the secondary use extremely bounded

With four months of live operations, a second reuse demonstration could reasonably be developed near or after go-live. With nine months of exchange, the project has much less implementation runway.

I would define the second use at pilot launch and ensure that it relies on exactly the same data elements as the primary use. It should not introduce:

* Additional source feeds
* Additional endpoint configurations
* Additional legal agreements
* A materially different cohort
* New identity resolution
* A separate production environment

A suitable second use would be a one-time or periodic calculation generated from the same curated dataset—for example, a representative quality-measure result or HRSA-aligned analytic output.

## 8. Shift evaluation effort into the operating period

A longer exchange period improves the evaluation substantially. Instead of evaluating only whether exchange occurred, the pilot can assess:

* Stability over time
* Data drift
* Recurrent source failures
* Data-quality improvement
* Seasonal or monthly volume variation
* Support burden
* Remediation effort
* Actual use by STLT staff
* Repeated production of the second-use artifact
* Operational cost per month
* Incremental cost of reuse

This is a major benefit. Six to nine months provides a more credible basis for assessing operational sustainability than four months.

However, the evaluation must begin before go-live. Baseline metrics and instruments need to be ready during mobilization, not designed after exchange starts.

## 9. Strengthen operational success criteria

With six to nine months of data exchange, I would expect stronger evidence than merely showing that the pipeline worked once.

Suggested operational criteria include:

* Exchange sustained for the required period
* Defined percentage of expected reporting cycles completed
* Documented uptime or successful processing rate
* Median data latency
* Required-element completeness by month
* Number and duration of incidents
* Support hours per month
* Number of quality defects opened and resolved
* Stable production of the primary output
* At least two or three successful executions of the secondary reuse, depending on cadence
* Documented use or review by the STLT

The longer period makes “meaningful exchange” more defensible, but only if the pilot defines what regular, sustained use means.

## 10. Reduce the number of provider networks required at initial go-live

Six provider networks can remain the overall target, but I would avoid making all six a prerequisite for starting the exchange clock.

Use a rolling model:

* **Initial go-live:** four ready provider networks
* **Early operating period:** onboard or activate the remaining two
* **Final operating cohort:** target all six, subject to readiness

For evaluation, distinguish:

* Months of operation per network
* Number of networks live at each point
* Data volume and completeness by source
* Reasons for delayed activation

A rolling approach prevents the least-ready participant from shortening the entire exchange period.

## 11. Change the definition of the exchange period

The project should clearly define whether “six to nine months of exchange” means:

1. All six provider networks exchange continuously for the entire period, or
2. The pilot operates for that period, with sources joining during an early ramp-up window.

I recommend the second formulation:

> The production pilot environment will operate for at least six months, targeting nine months where readiness permits. A minimum operational cohort will be live at the start of the period, and remaining approved sources may join during a defined early ramp-up window.

Requiring all providers to be live on day one for nine full months would create a high likelihood of missing the target.

# Revised feasibility assessment of the original pilot elements

| Pilot element                     | Four-month operations assessment | Six-to-nine-month assessment                                               |
| --------------------------------- | -------------------------------- | -------------------------------------------------------------------------- |
| One intermediary pathway          | Feasible                         | Feasible and necessary                                                     |
| Six provider networks             | Feasible with readiness risk     | Feasible only with rolling activation or exceptionally mature participants |
| Two new endpoints                 | Potentially feasible             | Six months: possible; nine months: too risky unless simple configuration   |
| Minimum dataset and mapping guide | Feasible                         | Feasible if substantially drafted before launch                            |
| One operational use               | Feasible                         | Feasible with stronger operational evidence                                |
| Second-use demonstration          | Feasible                         | Feasible only if technically and legally dependent on the same dataset     |
| Trust/data-quality reporting      | Feasible in minimum form         | More valuable because improvement can be tracked longitudinally            |
| Custom dashboards                 | Exclude                          | Continue to exclude                                                        |
| Closed-loop referral extension    | Exclude                          | Continue to exclude                                                        |
| Additional chronic domain         | Exclude                          | Continue to exclude                                                        |
| National scalability claim        | Learning only                    | Still learning only, although operational evidence is stronger             |
| Provider burden reduction         | Directional evidence             | More credible if recurring effort is measured over time                    |
| Outcome improvement               | Not supportable                  | Still generally not supportable within one year                            |
| Sustainability assessment         | Preliminary                      | More credible because actual monthly run rates can be observed             |

# Revised 12-month schedules

## Six-month exchange model

| Period            | Primary activities                                                              |
| ----------------- | ------------------------------------------------------------------------------- |
| Month 0/pre-award | Select participants, condition, workflow, and preliminary dataset               |
| Month 1           | Charter, readiness verification, agreement finalization, detailed design        |
| Month 2           | Configuration, mapping, security setup, baseline evaluation                     |
| Month 3           | Testing and first remediation cycle                                             |
| Month 4           | Final readiness, go-live of minimum operational cohort                          |
| Months 5–10       | Six months of exchange, monitoring, remediation, rolling onboarding, evaluation |
| Months 11–12      | Final analysis, sustainability planning, reporting, closeout                    |

This is aggressive but credible when partners are preselected and existing connectivity is genuine.

## Nine-month exchange model

| Period            | Primary activities                                                                                |
| ----------------- | ------------------------------------------------------------------------------------------------- |
| Month 0/pre-award | Complete participant selection, thin-slice design, legal-path assessment, and technical readiness |
| Month 1           | Final charter, configuration plan, access setup, baseline collection                              |
| Month 2           | Mapping, testing, and priority remediation                                                        |
| Month 3           | Go-live                                                                                           |
| Months 4–12       | Nine months of exchange, continuous evaluation, reporting, and transition planning                |

This model leaves virtually no room for greenfield integration or prolonged agreement negotiation. Closeout and final reporting would need to overlap with the final operating months or extend briefly beyond the exchange period.

# Budget implications

Moving from four months to six or nine months should not proportionally increase the entire pilot cost because much of the work is fixed. It primarily increases:

* HDU operations labor
* Help desk and incident support
* Performance reporting
* Incremental compute, storage, and logging
* STLT operational-use labor
* Provider source-support labor
* Evaluation monitoring and analysis
* PMO duration devoted to operations

At the same time, the implementation budget must shrink or remain tightly controlled to stay near $3 million.

A revised allocation might be:

| Work area                 | Four-month model |                               Six-to-nine-month direction |
| ------------------------- | ---------------: | --------------------------------------------------------: |
| Design and implementation |           Higher |                         Reduce through stricter readiness |
| New endpoint work         |        Up to two |                        Prefer zero to one for nine months |
| Operations                |         Moderate |                                                  Increase |
| Evaluation                |         Moderate |                             Increase recurring monitoring |
| Remediation               |           Capped |                              Remain capped and time-boxed |
| Contingency               |          General | Concentrate on source stability and operational incidents |

For the nine-month model, I would not fund significant platform configuration and a long operations period from the same $3 million unless participant readiness is exceptionally high.

# Revised non-negotiables

For a six-month minimum:

1. Participants selected before formal project launch.
2. At least four provider networks capable of go-live by month four.
3. At least 75% existing usable connectivity.
4. No more than two materially new endpoints.
5. Existing agreements or a credible addendum path.
6. Minimum dataset largely defined during the first month.
7. One operational output and one tightly bounded reuse.
8. Baseline evaluation completed before go-live.
9. Operations begin no later than month five.
10. Remaining participants may join through a controlled ramp-up.

For a nine-month target:

1. Participants and use case substantially finalized before launch.
2. Minimum operational cohort ready within 60–90 days.
3. Nearly all required data pathways already live.
4. Prefer no more than one configuration-only endpoint gap.
5. No novel legal, security, identity, or architecture work.
6. No custom application development.
7. No new measure-engine implementation.
8. Evaluation and closeout conducted concurrently with operations.
9. High-priority defects corrected after go-live where safe.
10. Nine months treated as a stretch target unless readiness is verified before award.

## Recommended formulation

I would describe the operating requirement as:

> Each pilot will maintain production data exchange for a minimum of six months and target up to nine months when pre-launch readiness permits. The exchange period will begin when a defined minimum operational cohort and the primary downstream output are live. Additional approved sources may join during a limited early ramp-up period. The pilot will prioritize sustained, measurable operations over completion of nonessential technical extensions.

My overall recommendation changes in one important way: **six months should become the contractual minimum; nine months should be a readiness-dependent target rather than an unconditional requirement.** A firm nine-month requirement in a 12-month project is realistic only when the pilot is selected as an already functioning exchange that needs limited configuration—not as a new implementation.

---

# Prompt

List everything that requires my input before we proceed to STAGE 4 in a table, and I'll fill it out, then attach it, so we can proceed.

# Response

Below is the input table I recommend completing before Stage 4. Items marked **Required** materially affect the base pro forma. Items marked **Preferred** can remain provisional, but the model will be less precise.

| ID  | Priority  | Input Required                              | What You Need to Provide                                                                              | Suggested Options or Current Working Assumption                                                                                     | Your Response |
| --- | --------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| S01 | Required  | Pilot condition domain                      | Name the single chronic condition addressed by this pilot                                             | Hypertension; diabetes; childhood asthma; another defined domain                                                                    |               |
| S02 | Required  | Primary measure or analytic workflow        | Identify the one measure, surveillance indicator, or workflow that will be fully operational          | Example: hypertension control; diabetes care cascade; asthma-related acute-care utilization                                         |               |
| S03 | Required  | Primary customer                            | Identify the organization or program expected to use the operational output                           | Participating STLT chronic disease program                                                                                          |               |
| S04 | Required  | Primary operational output                  | Describe exactly what will be delivered to the primary customer                                       | Line-level dataset; aggregate dataset; recurring extract; FHIR resource set; measure result; analytic table                         |               |
| S05 | Required  | Primary output cadence                      | State how frequently the operational output will be produced                                          | Near real time; daily; weekly; monthly; quarterly                                                                                   |               |
| S06 | Required  | Primary output access method                | State how the recipient receives or accesses the output                                               | Existing portal; secure file transfer; API; Bulk FHIR; direct database access; existing BI tool                                     |               |
| S07 | Required  | Primary output data-access level            | State the level of detail delivered                                                                   | Identifiable line-level; limited dataset; de-identified line-level; aggregate                                                       |               |
| S08 | Required  | Secondary downstream use                    | Identify the second reuse to be demonstrated                                                          | HRSA-aligned output; NCQA/digital quality result; CDC program extract; other                                                        |               |
| S09 | Required  | Secondary-use artifact                      | Define what constitutes completion of the second reuse                                                | One-time measure calculation; FHIR MeasureReport; sample extract; validated transformation; recurring nonproduction output          |               |
| S10 | Required  | Secondary-use boundary                      | Confirm that it is a demonstration rather than a second production implementation                     | Working assumption: no new production interface, SLA, dashboard, or recurring support                                               |               |
| S11 | Required  | Exchange-period requirement                 | Select the required production exchange period                                                        | Minimum six months; target nine months; firm nine months                                                                            |               |
| S12 | Required  | Exchange-period start rule                  | Define when the exchange clock begins                                                                 | When minimum operational cohort and primary output are live                                                                         |               |
| S13 | Required  | Minimum operational cohort                  | State how many provider networks must be live before the exchange period begins                       | Recommended: four of six                                                                                                            |               |
| S14 | Required  | Final participation target                  | Confirm the total number of provider networks expected to participate                                 | Current assumption: six                                                                                                             |               |
| S15 | Required  | Rolling onboarding permitted                | Confirm whether remaining networks may join after the exchange period begins                          | Recommended: yes, during a defined early ramp-up period                                                                             |               |
| S16 | Required  | Ramp-up window                              | Specify how long remaining sources have to join after initial go-live                                 | One month; two months; no rolling onboarding                                                                                        |               |
| S17 | Required  | Total project duration                      | Confirm the period from mobilization through closeout                                                 | Current assumption: 12 months                                                                                                       |               |
| S18 | Required  | Pre-award work permitted                    | Identify which activities may occur before the formal 12-month pilot begins                           | Participant selection, readiness review, use-case selection, draft dataset, legal-path assessment                                   |               |
| P01 | Required  | Intermediaries per pilot                    | Confirm the number of intermediary organizations                                                      | Current assumption: one                                                                                                             |               |
| P02 | Required  | STLT jurisdictions per pilot                | Confirm the number of participating jurisdictions                                                     | Current assumption: one                                                                                                             |               |
| P03 | Required  | Named or representative intermediary        | Identify the actual intermediary, if known, or the type to model                                      | State HDU; statewide HIE; regional HIE; HCCN; other                                                                                 |               |
| P04 | Required  | Named or representative STLT                | Identify the actual jurisdiction, if known, or describe the model jurisdiction                        | State health department; territorial agency; local health department                                                                |               |
| P05 | Preferred | Provider-network identities                 | List the six expected networks, if known                                                              | Names or representative provider types                                                                                              |               |
| P06 | Required  | Provider-network composition                | Describe what counts as one provider network                                                          | Health system; HCCN; FQHC network; ACO; hospital network; other                                                                     |               |
| P07 | Required  | Distinct EHR vendor count                   | Estimate the number of different EHR products represented across the six networks                     | 1–2; 3–4; 5–6; unknown                                                                                                              |               |
| P08 | Required  | Distinct EHR instance count                 | Estimate the number of separately configured EHR instances                                            | Number or range                                                                                                                     |               |
| P09 | Required  | Other source-system count                   | Identify non-EHR sources required for the base pilot                                                  | None; laboratory; claims; pharmacy; ADT; registry; other                                                                            |               |
| P10 | Required  | Connectivity threshold                      | Confirm the minimum percentage of required source pathways already connected                          | Current assumption: at least 75%                                                                                                    |               |
| P11 | Required  | Meaning of “connected”                      | Confirm the readiness definition                                                                      | Recommended: production feed exists, required data are present, and reuse is legally permitted                                      |               |
| P12 | Required  | New endpoint cap                            | Confirm the maximum number of materially new endpoint configurations                                  | Current assumption: no more than two; for nine months, preferably zero or one                                                       |               |
| P13 | Required  | Treatment if cap is exceeded                | State what happens if readiness shows more new endpoints are required                                 | Remove source; reduce cohort; separately fund; abandon participant; revise budget                                                   |               |
| P14 | Preferred | Backup participants                         | State whether backup provider networks will be identified before award                                | Yes or no                                                                                                                           |               |
| D01 | Required  | Minimum dataset size                        | Confirm the intended size or provide the draft data-element list                                      | Current planning range: approximately 15–25 elements                                                                                |               |
| D02 | Required  | Required stratifications                    | Identify required demographic or geographic stratifications                                           | Age; sex; race/ethnicity; geography; payer; organization; other                                                                     |               |
| D03 | Required  | Required provenance fields                  | Identify minimum source and transformation metadata                                                   | Source organization, source system, timestamps, transformation history                                                              |               |
| D04 | Required  | Data sources permitted                      | Identify which formats or pathways may support the base use case                                      | FHIR API; Bulk FHIR; HL7 v2; C-CDA; flat file; existing repository                                                                  |               |
| D05 | Required  | Preferred technical pathway                 | Select the primary pathway the pro forma should model                                                 | Existing intermediary repository; Bulk FHIR; REST API; existing HL7 feeds; mixed                                                    |               |
| D06 | Required  | Measure specification source                | Identify the authoritative clinical or measure specification                                          | CDC definition; CMS measure; HRSA UDS+ measure; NCQA measure; locally defined logic                                                 |               |
| D07 | Required  | Measure licensing                           | State whether the selected measure requires licensing                                                 | Yes; no; unknown                                                                                                                    |               |
| D08 | Required  | Measure engine availability                 | State whether the intermediary already has an appropriate execution engine                            | Existing CQL engine; other analytics engine; no engine required; unknown                                                            |               |
| D09 | Required  | Patient matching requirement                | Define whether the use case requires longitudinal matching                                            | Existing MPI only; cohort attribution without matching; no matching; other                                                          |               |
| D10 | Required  | Existing MPI adequacy                       | Confirm whether the intermediary’s current matching capability is assumed sufficient                  | Current assumption: yes; no new MPI development                                                                                     |               |
| T01 | Required  | Existing hosting                            | Confirm that the intermediary will use an existing hosted environment                                 | Current assumption: yes                                                                                                             |               |
| T02 | Required  | Existing IAM                                | Confirm existing identity and access management will be reused                                        | Current assumption: yes                                                                                                             |               |
| T03 | Required  | Existing audit and logging                  | Confirm existing logging and audit capabilities will be reused                                        | Current assumption: yes                                                                                                             |               |
| T04 | Required  | Existing operations support                 | Confirm that production monitoring, incident management, and help desk already exist                  | Current assumption: yes                                                                                                             |               |
| T05 | Required  | Existing development and test environments  | Confirm whether these environments are already available                                              | Yes; no; partially                                                                                                                  |               |
| T06 | Required  | Existing data-normalization capability      | Confirm whether the intermediary already normalizes relevant data                                     | Yes; no; partially                                                                                                                  |               |
| T07 | Required  | Custom application development              | Confirm exclusion of custom portal or dashboard development                                           | Current assumption: excluded                                                                                                        |               |
| T08 | Required  | Standard report format                      | Select what replaces a custom dashboard                                                               | Existing dashboard; CSV/Excel extract; PDF quality report; API response; BI dataset                                                 |               |
| T09 | Preferred | Estimated data volume                       | Provide approximate patients, encounters, records, or transactions per month                          | Number or range                                                                                                                     |               |
| T10 | Preferred | Number of environments charged to pilot     | State whether the pilot pays incremental costs for development, test, and production                  | Existing/included; incremental; unknown                                                                                             |               |
| G01 | Required  | Legal pathway                               | Describe the expected agreement approach                                                              | Existing DUA covers use; addendum required; new DUA; multiple provider agreements; unknown                                          |               |
| G02 | Required  | Number of expected agreements               | Estimate the number of agreements or addenda                                                          | One statewide agreement; one per provider; other                                                                                    |               |
| G03 | Required  | Federal data-access requirement             | State whether CDC will directly receive pilot data                                                    | Yes—line-level; yes—de-identified; yes—aggregate; no direct data access                                                             |               |
| G04 | Required  | Secondary-consumer agreement                | State whether the secondary use requires a distinct data-sharing agreement                            | Yes; no; unknown                                                                                                                    |               |
| G05 | Required  | Security approval pathway                   | Identify who must approve the intermediary’s controls                                                 | Intermediary only; STLT; provider networks; CDC; another entity                                                                     |               |
| G06 | Required  | CDC ATO assumption                          | Confirm whether a CDC authorization to operate is required                                            | Current assumption: no CDC ATO unless CDC-hosted                                                                                    |               |
| G07 | Required  | Consent requirement                         | State whether individual consent is expected to apply                                                 | No; yes; unknown                                                                                                                    |               |
| G08 | Required  | Data-retention requirement                  | Define how long pilot data must be retained                                                           | Existing policy; pilot duration only; defined number of years; unknown                                                              |               |
| G09 | Preferred | Redisclosure restrictions                   | Identify any known downstream-use restrictions                                                        | Description or unknown                                                                                                              |               |
| F01 | Required  | STLT funding treatment                      | Select how STLT work will be funded                                                                   | Direct award; subaward; fixed stipend; reimbursed labor; in kind                                                                    |               |
| F02 | Required  | Intermediary funding treatment              | Select how intermediary work will be funded                                                           | Fixed subaward; cost-reimbursement; milestone payments; prime subcontract                                                           |               |
| F03 | Required  | Provider funding treatment                  | Select whether provider effort will be compensated                                                    | In kind; fixed stipend; reimbursed labor; paid through intermediary                                                                 |               |
| F04 | Required  | Provider stipend amount or method           | If providers are compensated, specify the amount or calculation basis                                 | Fixed per network; actual labor; capped allowance; TBD                                                                              |               |
| F05 | Required  | Vendor-fee funding                          | State who pays EHR or vendor implementation charges                                                   | Sponsor; intermediary; provider; shared; excluded                                                                                   |               |
| F06 | Required  | Legal-cost funding                          | State whether participant legal costs are reimbursable                                                | Yes; no; allowance only                                                                                                             |               |
| F07 | Required  | Security-review funding                     | State whether participant security review is reimbursable                                             | Yes; no; allowance only                                                                                                             |               |
| F08 | Required  | In-kind valuation                           | State whether Stage 4 should monetize participant in-kind labor                                       | Yes; report hours only; both hours and value; exclude with disclosure                                                               |               |
| F09 | Required  | Existing infrastructure treatment           | Select how existing HDU infrastructure should be represented                                          | Exclude from sponsor cost but report as contributed value; do not monetize; allocate estimated value                                |               |
| F10 | Required  | Sponsor-funded cost target                  | Confirm the target for each direct pilot budget                                                       | Current target: approximately $3 million                                                                                            |               |
| F11 | Required  | Treatment of shared portfolio costs         | Select reporting method                                                                               | Central only; allocated equally; allocated by labor usage; show both central and allocated views                                    |               |
| F12 | Required  | Portfolio size                              | Confirm how many pilots will share common assets                                                      | Three; four; another number                                                                                                         |               |
| F13 | Required  | Contingency treatment                       | Select how contingency should be modeled                                                              | Fixed percentage; risk-item allowances; both; no contingency                                                                        |               |
| F14 | Preferred | Target contingency level                    | Provide target percentage or leave for Stage 4 recommendation                                         | Example: 5%–10%                                                                                                                     |               |
| Q01 | Required  | Testing rigor                               | Define the expected testing level                                                                     | Basic conformance and end-to-end; formal parallel comparison; extensive edge cases                                                  |               |
| Q02 | Required  | Remediation-cycle definition                | Confirm whether the two-cycle cap applies per source pathway or to the pilot overall                  | Recommended: per source pathway, coordinated at pilot level                                                                         |               |
| Q03 | Required  | Defect severity threshold                   | State which defects must be corrected before go-live                                                  | Critical only; critical and high; all required-element defects                                                                      |               |
| Q04 | Required  | Post-go-live remediation                    | Confirm that priority defects may be corrected during early operations                                | Yes; no                                                                                                                             |               |
| Q05 | Required  | Unresolved defects after cycle two          | Select treatment                                                                                      | Document and accept limitation; remove source; separately fund; delay acceptance                                                    |               |
| Q06 | Required  | Participant replacement                     | State whether a failed provider may be replaced                                                       | Yes; no; only before go-live                                                                                                        |               |
| Q07 | Required  | Go-live acceptance authority                | Identify who makes the final go-live decision                                                         | Sponsor; STLT; intermediary; joint decision                                                                                         |               |
| Q08 | Required  | Minimum go-live criteria                    | Define the minimum conditions for exchange to begin                                                   | Minimum cohort, core elements, primary output, security approval, operational support                                               |               |
| O01 | Required  | Service expectations                        | Identify whether formal service levels are required                                                   | Best effort; defined response targets; formal SLA                                                                                   |               |
| O02 | Required  | Support coverage                            | Define support hours during live operations                                                           | Business hours; extended hours; 24×7                                                                                                |               |
| O03 | Required  | Operational reporting cadence               | State how often intermediary performance reports are required                                         | Weekly; monthly; quarterly                                                                                                          |               |
| O04 | Required  | Secondary-use frequency                     | State how often the second-use artifact must be generated                                             | Once; twice; monthly; quarterly                                                                                                     |               |
| O05 | Required  | Exchange-period success threshold           | Define the minimum successful reporting-cycle completion rate                                         | Example: 90%, 95%, or another threshold                                                                                             |               |
| O06 | Required  | Source continuity requirement               | State whether every provider must remain active for the full period                                   | All sources; minimum cohort only; defined percentage                                                                                |               |
| E01 | Required  | Evaluation dimensions                       | Select the required evaluation domains                                                                | Data quality; conformance; timeliness; reliability; burden; utility; reuse; cost; sustainability                                    |               |
| E02 | Required  | Baseline requirement                        | State whether baseline data must be collected before go-live                                          | Recommended: yes                                                                                                                    |               |
| E03 | Required  | Burden measurement                          | Identify how participant burden should be measured                                                    | Time reporting; interviews; surveys; ticket counts; qualitative only                                                                |               |
| E04 | Required  | Decision-utility evidence                   | Define what counts as evidence that the STLT used the output                                          | Documented review; meeting decision; investigation; program action; user attestation                                                |               |
| E05 | Required  | Cost evaluation                             | State whether actual participant and sponsor costs must be collected during the pilot                 | Yes; sponsor only; total economic cost; no                                                                                          |               |
| E06 | Required  | Outcome-evaluation boundary                 | Confirm that clinical or population outcome improvement is not required                               | Recommended: exclude from base pilot                                                                                                |               |
| E07 | Required  | Final evaluation timing                     | State whether evaluation and reporting may overlap with live operations                               | Required for a nine-month target; recommended generally                                                                             |               |
| E08 | Preferred | Independent evaluator requirement           | State whether evaluation must be organizationally independent                                         | Yes; no; partially independent                                                                                                      |               |
| C01 | Required  | Portfolio-shared assets available at launch | Identify which common assets will exist before pilot mobilization                                     | Charter, governance, legal, security, architecture, testing, evaluation, training, playbook templates                               |               |
| C02 | Required  | Pilot-specific adaptation responsibility    | Identify who adapts portfolio assets for the pilot                                                    | Portfolio PMO; pilot PMO; intermediary; shared                                                                                      |               |
| C03 | Required  | Common PMO treatment                        | State whether a central portfolio PMO will operate in addition to pilot PMO                           | Yes; no                                                                                                                             |               |
| C04 | Required  | Common technical services                   | State whether architecture, conformance, legal, security, and evaluation experts are centrally funded | Yes; no; selected services only                                                                                                     |               |
| C05 | Required  | Shared-cost allocation method               | Confirm how central work will be reflected in each pilot’s pro forma                                  | Actual use; equal share; central only; multiple views                                                                               |               |
| X01 | Required  | Optional extensions                         | Confirm all work excluded from the base pilot                                                         | Custom dashboards; additional domains; extra measures; payer data; TEFCA; referrals; CBOs; AI; new MPI/IAM; more than two endpoints |               |
| X02 | Required  | Optional-cost schedule                      | State whether Stage 4 should price excluded extensions separately                                     | Yes; no; selected extensions only                                                                                                   |               |
| X03 | Preferred | Extensions to price                         | Identify any optional items you want included in the pro forma as add-ons                             | List items                                                                                                                          |               |
| A01 | Required  | Low/base/high scenarios                     | Confirm whether Stage 4 should create three cost scenarios                                            | Recommended: yes                                                                                                                    |               |
| A02 | Required  | Base-case posture                           | Select the intended base scenario                                                                     | Six-month minimum; nine-month target; exceptionally ready nine-month case                                                           |               |
| A03 | Required  | High-case treatment                         | State whether the high case may exceed $3 million or must reduce scope to remain within the ceiling   | Allow overrun visibility; force scope reduction; show both                                                                          |               |
| A04 | Required  | Sponsor-cost presentation                   | Select the primary budget view                                                                        | Direct pilot cost only; direct plus allocated shared cost; both                                                                     |               |
| A05 | Required  | Economic-cost presentation                  | Select whether total economic cost should appear alongside sponsor cost                               | Yes; no; appendix only                                                                                                              |               |
| A06 | Required  | Labor-rate basis                            | Identify the rate source Stage 4 should use                                                           | Existing contract rates; federal schedules; market rates; blended placeholder rates                                                 |               |
| A07 | Preferred | Known labor rates                           | Attach or provide applicable rates, if available                                                      | Rate card or contract labor categories                                                                                              |               |
| A08 | Preferred | Known vendor or intermediary quotes         | Attach any available pricing or preliminary estimates                                                 | Quote, budgetary estimate, or none                                                                                                  |               |

## Items that can remain provisional

You do not need final answers for every detailed quantity before Stage 4. The model can use low/base/high assumptions for:

* Number of distinct source systems
* Data volume
* Number of test scenarios
* Defect counts
* Support-ticket volume
* Incremental cloud consumption
* Training cohort size
* Legal hours
* Participant in-kind hours
* Vendor charges pending quotes

The pro forma should flag these as validation inputs rather than silently treating them as known.

## Most critical fields

At minimum, complete these before Stage 4:

**S01–S18, P01–P13, D01–D10, G01–G08, F01–F13, Q01–Q08, E01–E07, C01–C05, X01–X02, and A01–A06.**

Those decisions establish the scope, schedule, funding boundaries, and scenario structure. The remaining fields improve precision but do not prevent construction of a defensible first model.

---

# Prompt

What are my options for S12?

# Response

For **S12 — Exchange-period start rule**, you have several defensible options. The choice determines when the six- or nine-month “meaningful exchange” clock begins and how much implementation risk sits with the pilot.

| Option                                 | Start Rule                                                                                                                                     | Advantages                                                                               | Risks / Limitations                                                                                          | Best Fit                                                         |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------- |
| 1. First production transmission       | Clock starts when the intermediary successfully sends the first production data to the primary recipient                                       | Simple and easy to document                                                              | A single successful transmission may not represent stable operations; can overstate the true exchange period | Proof-of-concept pilots with minimal operational expectations    |
| 2. Primary output operational          | Clock starts when the primary downstream output is available in production and passes minimum acceptance criteria                              | Ties the period to delivery of the actual pilot product                                  | Could start before enough provider networks are live                                                         | Pilots focused mainly on the intermediary-to-STLT output         |
| 3. Minimum operational cohort live     | Clock starts when the required minimum number of provider networks are contributing and the primary output is operational                      | Balances schedule protection with meaningful participation                               | Requires a clearly defined minimum cohort and acceptance criteria                                            | Recommended for this pilot                                       |
| 4. All planned participants live       | Clock starts only when all six provider networks are contributing and the primary output is operational                                        | Produces a clean, consistent evaluation period                                           | One delayed participant can shorten or derail the entire operating period                                    | Only when all participants are exceptionally mature before award |
| 5. Stability threshold achieved        | Clock starts after the pilot meets a defined operational threshold for a specified period, such as two consecutive successful reporting cycles | Ensures the exchange period reflects stable production rather than initial go-live       | Delays the clock and may make nine months impossible within a 12-month project                               | Six-month exchange with strong emphasis on reliability           |
| 6. Fixed calendar date                 | Clock starts on a predetermined date regardless of participant or technical readiness                                                          | Easy for contract administration and reporting                                           | May count time when data are incomplete or systems are not functioning                                       | Funding instruments requiring fixed dates                        |
| 7. Staged exchange clock               | The pilot operating period starts when the minimum cohort is live; each additional participant gets its own participation-duration clock       | Supports rolling onboarding and preserves the overall exchange period                    | More complex evaluation and reporting                                                                        | Pilots with four initial networks and two later joiners          |
| 8. Hybrid readiness-and-stability rule | Clock starts when the minimum cohort is live, the primary output passes acceptance, and one complete reporting cycle is successfully completed | Strong evidence that operations are real while avoiding an excessive stabilization delay | Requires objective acceptance criteria and quick readiness review                                            | Best overall option for a six-month minimum                      |

## Recommended option

I recommend a **hybrid of Options 3 and 8**:

> The exchange period begins when the minimum operational cohort is contributing production data, the primary downstream output has passed defined acceptance criteria, required security and governance approvals are complete, and one complete reporting cycle has been successfully processed.

For the current pilot assumptions, the minimum operational cohort could be:

* Four of six provider networks
* The intermediary operating in production
* The STLT able to receive or access the primary output
* Core required data elements meeting minimum thresholds
* No unresolved critical defects
* Monitoring and support procedures active

The remaining two provider networks could join during the ramp-up period without restarting the clock.

## Simpler wording for the input table

For S12, you could enter:

> The exchange clock begins when at least four of six provider networks are live in production, the primary STLT output has passed minimum acceptance criteria, required approvals are complete, and one full reporting cycle has been successfully completed. Remaining networks may join during the approved ramp-up period.

## Alternative for a firm nine-month requirement

A nine-month exchange period leaves less room for stabilization. In that case, use:

> The exchange clock begins when the minimum operational cohort and primary output enter production. The first reporting cycle is treated as stabilization but counts toward the exchange period, provided no critical failure interrupts production.

That approach preserves nine months but accepts more operational risk.

## Alternative for a conservative six-month requirement

For a six-month contractual minimum with stronger evidence:

> The exchange clock begins after the minimum operational cohort and primary output complete two consecutive successful reporting cycles and meet the minimum data-quality, timeliness, and reliability thresholds.

This provides stronger evidence of sustained exchange but requires an earlier initial go-live.

---

# Prompt

Explain what you are seeking to clarify with C05.

# Response

C05 is asking **how the cost of portfolio-level shared work should appear in each individual pilot’s pro forma**.

The shared work includes items such as:

* Common governance framework
* Model legal agreements
* Common security requirements
* Reference architecture
* Shared conformance and testing methods
* Common evaluation framework
* Portfolio PMO
* Shared training materials
* Common implementation-playbook structure

Those costs support all three or four pilots, but they are not necessarily incurred separately by each pilot. C05 is intended to prevent two opposite errors:

* **Double counting:** charging the full shared cost to every pilot.
* **Understating pilot cost:** excluding shared support entirely, making each pilot look cheaper than the portfolio actually is.

## The main options

| Option                | How the pro forma would show shared costs                                                     | When it is useful                                                       |
| --------------------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Central only          | Shared costs appear once in a separate portfolio budget and not in individual pilot totals    | Best for managing the total portfolio budget                            |
| Equal allocation      | Divide shared costs equally across all pilots                                                 | Simple, but may be arbitrary if pilots use different amounts of support |
| Actual-use allocation | Allocate costs based on recorded labor, services, or resources used by each pilot             | Most defensible, but requires time and cost tracking                    |
| Weighted allocation   | Allocate using a complexity factor, such as interfaces, participants, or technical difficulty | Useful when pilots differ materially in size or complexity              |
| Multiple views        | Show direct pilot cost, allocated shared cost, and fully loaded pilot cost separately         | Best for decision-making and transparency                               |

## What I recommend

For C05, I recommend entering:

> Show multiple views. Report portfolio-shared costs centrally, allocate them to pilots based on actual labor usage where available, and also show each pilot’s direct cost and fully loaded cost separately.

That would produce three figures for each pilot:

1. **Direct pilot cost**
   Costs incurred specifically for that pilot.

2. **Allocated shared cost**
   The pilot’s share of common portfolio services.

3. **Fully loaded pilot cost**
   Direct pilot cost plus allocated shared cost.

This is especially important because you are targeting approximately $3 million per pilot. You need to decide whether that target means:

* $3 million in direct pilot spending, excluding central shared costs, or
* $3 million fully loaded, including each pilot’s share of shared portfolio costs.

That distinction is what C05 is really trying to resolve.

---

# Prompt

Run the STAGE 4 PROMPT using the attached assumptions ("Chronic Assumptions.xlsx").

# Response

Completed the Stage 4 pro forma using the attached assumptions and the Stage 3 organization-specific WBS. The workbook follows the required model structure and scenario logic in the Stage 4 prompt. 

[Download the Chronic Care Cascade Pro Forma Cost Model](sandbox:/mnt/data/Chronic_Care_Cascade_Pro_Forma_Cost_Model.xlsx)

### Initial model results

| Cost measure                       |        Low |        Base |        High |
| ---------------------------------- | ---------: | ----------: | ----------: |
| Sponsor cost before contingency    |     $1.02M |      $2.06M |      $3.45M |
| Contingency                        |     $0.05M |      $0.16M |      $0.35M |
| Sponsor cost including contingency | **$1.08M** |  **$2.23M** |  **$3.80M** |
| Participant-funded cost            |     $0.05M |      $0.10M |      $0.15M |
| Total economic-cost proxy*         |     $1.13M |      $2.33M |      $3.95M |
| In-kind participant labor          |  669 hours | 1,656 hours | 2,713 hours |

*The economic-cost proxy excludes monetized in-kind labor and existing intermediary infrastructure, consistent with your assumptions.

The base scenario has approximately **$773,000 of headroom** below the $3 million direct pilot target. The high scenario exceeds the target, primarily because of greater integration effort, defects and remediation, operational support, evaluation intensity, and non-labor allowances.

### Workbook contents

The workbook includes:

* Executive summary and cost charts
* Editable pilot parameters
* Provisional 2026 labor rates
* Detailed organization-specific WBS cost model
* Non-labor and in-kind schedules
* Cost summaries by organization and phase
* Recurring operations and annualized run-rate analysis
* Risk-based contingency analysis
* Sensitivity analysis
* Basis-of-estimate documentation
* Completed assumptions and decisions
* Source register
* Explicit exclusions
* Optional-extension allowances
* Formula and structural validation checks

Blue-font cells are editable inputs, black cells contain calculations, and green formulas link across worksheets. The workbook contains no macros and produced no detected formula-reference errors.

---

# Prompt 

I've obtained some clarifications that impact the cost model:

We only need to build up the costs for the following participants in the pilot:
- Intermediary (expected to be a state HIE or an HDU)
- Health Center Controlled Network
- State Public Health Agency
- Hospital System

We need to see the cost and major cost drivers for each type of participant in that list. 

We also need to see the work breakdown and labor categories grouped by each type of participant.

How does this change the model? Are there any stage prompts that need to be updated or rerun?

---

# Response

This clarification changes the **organization structure of the model more than the underlying pilot scope**. The current model can be reused, but its participant-cost architecture should be revised before relying on the results.

The four required participant types should become the primary Level 1 cost centers:

1. Intermediary — state HIE or HDU
2. Health Center Controlled Network
3. State Public Health Agency
4. Hospital System

Sponsor, portfolio PMO, evaluator, and shared-services costs may still exist, but they should be shown separately as **central program costs**, not mixed into the participant cost build-up.

## How the model changes

### Current versus revised organization structure

| Current model category    | Revised treatment                                                                                    |
| ------------------------- | ---------------------------------------------------------------------------------------------------- |
| HDU                       | Rename to **Intermediary — State HIE/HDU** and retain as a primary participant                       |
| STLT                      | Narrow to **State Public Health Agency** and retain as a primary participant                         |
| Provider                  | Split into **Health Center Controlled Network** and **Hospital System**                              |
| Downstream consumer       | Remove as a separate participant cost center unless one of the four organizations performs that role |
| Sponsor                   | Retain as a central program-cost category, outside participant cost build-up                         |
| PMO / prime contractor    | Retain as central program delivery cost, outside participant cost build-up                           |
| Evaluator                 | Retain centrally or allocate only if the sponsor wants fully loaded participant views                |
| EHR/vendor                | Treat as a non-labor input or subcontract/vendor cost borne by one of the four participant types     |
| Cloud/platform provider   | Treat as an input to the intermediary, not a separate participant                                    |
| Portfolio shared services | Retain centrally and report separately                                                               |

The main structural correction is the split of the existing generic “Provider” category. An HCCN and a hospital system perform materially different work and incur different costs.

---

# Participant-specific cost structure

## 1. Intermediary — State HIE or HDU

The intermediary remains the largest technical cost center.

### Major work areas

* Pilot mobilization and technical planning
* Existing-connectivity inventory
* Source-system and data-readiness assessment
* Architecture adaptation
* Security and access configuration
* Data ingestion and routing configuration
* Patient matching using the existing MPI
* Data normalization and terminology mapping
* Measure or analytic-workflow implementation
* Data-quality and provenance rules
* Primary public-health output configuration
* Secondary reuse artifact generation
* End-to-end testing
* Defect remediation
* Production launch and stabilization
* Six-to-nine months of operations
* Incident support and performance reporting
* Evaluation-data production
* Sustainability and scale assessment

### Major cost drivers

| Cost driver                                 | Effect                                                                   |
| ------------------------------------------- | ------------------------------------------------------------------------ |
| Number of contributing source organizations | Drives onboarding, mapping, testing, and support                         |
| Number of distinct EHR instances            | More important than nominal organization count                           |
| Number of existing versus new endpoints     | New endpoints materially increase cost and schedule risk                 |
| Number of data-source formats               | FHIR, HL7 v2, C-CDA, and files create separate mapping and testing needs |
| Minimum dataset size                        | Drives mapping, validation, and quality-rule effort                      |
| Data completeness and conformance           | Drives remediation                                                       |
| Measure or analytic complexity              | Drives clinical, data, and engineering labor                             |
| Operating months                            | Drives support, monitoring, cloud, and reporting                         |
| Ticket and incident volume                  | Drives recurring support                                                 |
| Security and legal deltas                   | Drives review and configuration work                                     |

### Primary labor categories

* Intermediary project manager
* Solution architect
* Interoperability architect
* Data architect
* Integration engineer
* Data engineer
* Terminology specialist
* Clinical or public-health measure SME
* Security architect
* Security engineer
* IAM administrator
* QA/test engineer
* Data analyst
* Operations engineer
* Help-desk analyst
* Privacy or governance specialist
* Technical writer

---

## 2. Health Center Controlled Network

The HCCN should not be modeled merely as another provider. It may coordinate multiple health centers, centralize EHR/vendor engagement, support data extraction, and act as the implementation and technical-assistance layer for its member organizations.

### Major work areas

* HCCN project mobilization
* Member health-center identification and confirmation
* EHR and source-system inventory across members
* Member readiness assessment
* Coordination with EHR vendors
* Data-use and participation coordination
* Clinical-workflow and documentation review
* Validation of required diabetes data
* Mapping and measure-logic review
* Test-data coordination
* Member-level testing support
* Defect triage and remediation coordination
* Training and technical assistance
* Production monitoring across member sites
* Data-quality feedback to member health centers
* Evaluation interviews, surveys, and burden reporting
* Sustainability planning for HCCN members

### Major cost drivers

| Cost driver                                     | Effect                                            |
| ----------------------------------------------- | ------------------------------------------------- |
| Number of participating health centers          | Primary scale variable                            |
| Number of EHR vendors and instances             | Drives coordination and mapping complexity        |
| Degree of centralized HCCN technical control    | Greater centralization may reduce per-site effort |
| Existing HCCN data warehouse or FHIR capability | Can substantially reduce integration cost         |
| Member readiness variation                      | Drives TA and remediation                         |
| Number of member-level approvals                | Drives legal and project-management effort        |
| Need for HCCN-hosted transformation             | Adds data engineering and operations              |
| Training cohort count                           | Drives technical-assistance effort                |
| Provider documentation quality                  | Drives validation and improvement cycles          |

### Primary labor categories

* HCCN project manager
* HCCN technical lead
* HCCN interoperability or interface analyst
* EHR implementation specialist
* Data analyst
* Clinical quality SME
* UDS+/quality-reporting SME
* Training and technical-assistance specialist
* Member-engagement coordinator
* Privacy or compliance specialist
* Security analyst
* QA/test analyst
* Evaluation coordinator

### Key modeling decision

The cost model must distinguish whether the HCCN:

* Merely coordinates member health centers; or
* Operates a shared data warehouse or integration platform; or
* Performs data aggregation, mapping, quality checks, or FHIR-bundle generation.

Those roles produce very different cost profiles.

---

## 3. State Public Health Agency

The state public health agency is not primarily an integration implementer. Its cost is concentrated in public-health requirements, authority, governance, validation, operational use, and evaluation.

### Major work areas

* Pilot leadership and participation
* Definition of the surveillance workflow
* Identification of users and public-health decision points
* Measure and cohort validation
* Data-access and governance approval
* Legal and privacy review
* Security review
* Definition of acceptance criteria
* User acceptance testing
* Public-health user training
* Operational review of the data product
* Investigation or programmatic use of the output
* Data-quality and utility feedback
* Evaluation participation
* Sustainability and continuation decisions

### Major cost drivers

| Cost driver                        | Effect                                                  |
| ---------------------------------- | ------------------------------------------------------- |
| Number of state programs involved  | More programs increase governance and SME effort        |
| Line-level versus aggregate access | Changes privacy, security, and user workflows           |
| Frequency of the output            | Drives recurring analyst effort                         |
| Number of public-health users      | Drives training and access management                   |
| Complexity of the measure          | Drives epidemiologist and clinical SME review           |
| Novelty of legal authority         | Can materially affect schedule and counsel effort       |
| Security-review requirements       | Drives state IT effort                                  |
| Evaluation rigor                   | Drives data collection and staff participation          |
| Expected decision use              | More operational use increases recurring analyst effort |

### Primary labor categories

* State program director
* Pilot project manager
* Epidemiologist
* Chronic disease SME
* Clinical SME
* Public-health informatician
* Surveillance analyst
* Data analyst
* Legal counsel
* Privacy officer
* Security architect or security analyst
* Governance specialist
* Training participant or super-user
* Evaluation coordinator
* Executive sponsor

---

## 4. Hospital System

The hospital-system cost profile differs from the HCCN because it is more likely to contribute acute-care, ADT, laboratory, claims, pharmacy, and encounter data through enterprise infrastructure.

### Major work areas

* Hospital-system project mobilization
* Enterprise EHR and interface inventory
* Confirmation of existing HIE/HDU feeds
* Data-use and legal review
* Security and access review
* Clinical workflow review
* Source-data and code validation
* Endpoint configuration support
* Test-data preparation
* Interface and end-to-end testing
* Defect investigation and correction
* Production go-live authorization
* Ongoing source-feed monitoring
* Incident and data-quality response
* Clinical and technical validation
* Evaluation participation
* Sustainability assessment

### Major cost drivers

| Cost driver                                    | Effect                                                    |
| ---------------------------------------------- | --------------------------------------------------------- |
| Number of hospitals and facilities             | Drives coordination and source validation                 |
| Number of EHR instances                        | Drives interface-specific work                            |
| Enterprise versus facility-specific interfaces | Determines whether work is centralized or repeated        |
| Number of feed types                           | ADT, laboratory, pharmacy, claims, and FHIR each add work |
| Existing HIE relationship                      | Major determinant of incremental effort                   |
| Vendor configuration requirements              | Drives external fees and internal coordination            |
| Hospital security/change-control process       | Can drive schedule and labor                              |
| Data-quality defects                           | Drives clinical and technical remediation                 |
| Operational support requirements               | Drives recurring interface and data-quality labor         |

### Primary labor categories

* Hospital project manager
* Enterprise integration lead
* Interface analyst
* EHR application analyst
* Data engineer
* Clinical informaticist
* Quality-measure SME
* Laboratory or pharmacy-system analyst, where applicable
* Security analyst
* Privacy officer
* Legal counsel
* QA/test analyst
* Operations/support analyst
* Vendor product specialist
* Evaluation coordinator

---

# How the workbook should change

## Executive Summary

Replace the present organization view with:

| Participant Type | Funded Labor | Funded Non-Labor | In-Kind Hours | One-Time Cost | Recurring Cost | Low | Base | High | Major Cost Drivers |
| ---------------- | -----------: | ---------------: | ------------: | ------------: | -------------: | --: | ---: | ---: | ------------------ |

Rows:

* Intermediary — State HIE/HDU
* Health Center Controlled Network
* State Public Health Agency
* Hospital System

Then show central program costs separately:

* Sponsor
* Central PMO
* Evaluation
* Portfolio-shared work

## WBS Cost Model

The Level 1 WBS should be reorganized to:

* `INT` — Intermediary
* `HCCN` — Health Center Controlled Network
* `PHA` — State Public Health Agency
* `HOSP` — Hospital System
* `CENT` — Central sponsor/PMO/evaluation costs

The current `PRV` rows must be split. They should not simply be duplicated because the HCCN and hospital system have different responsibilities.

## Labor Rates

Add organization-specific labor categories, especially:

### HCCN

* HCCN technical lead
* HCCN member-engagement coordinator
* HCCN TA specialist
* HCCN quality-reporting SME
* HCCN interface analyst

### Hospital system

* Enterprise interface lead
* EHR application analyst
* Clinical informaticist
* Laboratory-system analyst
* Pharmacy-system analyst
* Hospital security/change-control analyst

### State PHA

* Epidemiologist
* Public-health informatician
* Surveillance analyst
* State program manager

Rates may use common benchmark classes initially, but the labels should reflect who performs the work.

## Pilot Parameters

Add or clarify:

* Number of HCCNs
* Number of health centers represented by each HCCN
* Number of hospital systems
* Number of hospitals or facilities in each system
* Number of distinct EHR instances within the HCCN
* Number of distinct EHR instances within the hospital system
* Number of feed types contributed by the hospital system
* Whether the HCCN has a shared data platform
* Whether the HCCN or intermediary generates the UDS+ bundle
* Whether health centers are direct pilot participants or represented entirely through the HCCN
* Whether hospitals receive compensation or contribute effort in kind
* Whether provider allowances go to the HCCN, hospital system, or both

## Cost by Organization

This becomes the key participant-cost worksheet and should show both:

* Total cost for each participant type
* Unit or marginal costs, where meaningful

Potential unit outputs:

* Cost per HCCN
* Cost per HCCN member health center
* Cost per hospital system
* Cost per hospital facility
* Cost per state PHA
* Cost per existing source connection
* Cost per new endpoint
* Monthly intermediary operating cost

## In-Kind Schedule

Split provider in-kind labor into:

* HCCN-funded or HCCN in-kind effort
* Member health-center effort, if tracked
* Hospital-system effort
* State PHA effort

If individual member health centers are not being costed separately, their effort should either:

* Be included as an HCCN-supported participant cost; or
* Be disclosed as excluded member-level in-kind work.

---

# Do the stage prompts need to be rerun?

## Stage 1: Update, not a full rerun

A full Stage 1 rerun is not necessary.

Update these sections:

* Participating-organization inventory
* Responsibility matrix
* Labor-category inventory
* Non-labor-cost inventory
* Cost-driver register
* Assumptions register

The principal change is replacing the generic provider category with two distinct organization types.

## Stage 2: Targeted supplement recommended

A complete Stage 2 rerun is probably unnecessary. The existing intermediary, public-health, integration, and evaluation benchmarks remain useful.

However, conduct a **targeted Stage 2 supplement** for:

* HCCN implementation and technical-assistance costs
* HCCN member onboarding
* UDS+/FHIR work performed by HCCNs
* Hospital-system interface and EHR configuration costs
* Hospital internal labor for data-sharing pilots
* Hospital ADT, laboratory, pharmacy, and FHIR feed implementation
* Provider stipends or subawards to HCCNs and hospital systems

The existing research may not adequately distinguish the HCCN from a conventional provider network.

## Stage 3: Revise or rerun

Stage 3 should be rerun—or at least substantially regenerated—because it is explicitly organization-specific.

The current Stage 3 structure contains:

* Intermediary
* STLT
* Generic provider
* Vendor
* Downstream consumer
* Evaluator and central organizations

The revised Stage 3 must create separate WBS structures for:

* Intermediary
* HCCN
* State PHA
* Hospital system

This is more than a label change. It affects:

* Activities
* Deliverable ownership
* Labor categories
* Scaling units
* Funding treatment
* In-kind work
* Cost drivers
* Dependencies
* Non-labor inputs

A revised Stage 3 is the most important prerequisite to updating the model properly.

## Stage 4: Rerun after Stage 3 revision

Stage 4 should be rerun after the revised Stage 3 is complete.

The current numerical results should be treated as provisional because:

* Generic provider labor is understated or misallocated.
* HCCN coordination and TA work are not separately represented.
* Hospital enterprise integration work is not separately represented.
* Provider allowances are currently modeled per generic network.
* Participant-level cost summaries do not match the newly required reporting structure.

---

# Recommended sequence

| Step | Action                                                          | Full rerun?                 |
| ---- | --------------------------------------------------------------- | --------------------------- |
| 1    | Update participant assumptions and role definitions             | No                          |
| 2    | Conduct targeted HCCN and hospital-system benchmark research    | Targeted Stage 2 supplement |
| 3    | Regenerate organization-specific WBS and labor mapping          | Yes, revised Stage 3        |
| 4    | Rebuild the Excel pro forma using four participant cost centers | Yes, revised Stage 4        |
| 5    | Reconcile new participant totals to the prior overall estimate  | Yes, validation step        |

## Expected effect on the total estimate

The change may not dramatically change total pilot cost if the existing model already captured most technical and participant work. It will, however, change **where costs sit**.

Likely directional effects:

* **Intermediary cost:** similar, although some work may shift to the HCCN.
* **State PHA cost:** similar.
* **HCCN cost:** higher than the prior generic-provider allocation because coordination, TA, UDS+ expertise, and member management become explicit.
* **Hospital-system cost:** potentially higher than prior generic-provider assumptions because enterprise interface, change-control, clinical validation, and multi-feed support become explicit.
* **Central PMO cost:** may decline slightly if HCCN coordination replaces some prime-contractor provider management.
* **In-kind cost:** likely increases once hospital and HCCN labor are represented separately.

The next defensible step is therefore a **targeted Stage 2 supplement followed by revised Stages 3 and 4**, rather than simply relabeling worksheets in the existing workbook.

---

# Prompt

That's helpful. I also need to ensure that any costs derived from the STAGE 2 research get attributed to the source from the research. How can I assure that occurs?

Build traceability into both the revised Stage 3 and Stage 4 deliverables as a mandatory data structure, not as narrative notes added afterward.

## What to require in the revised Stage 3

For every material work package, require these fields:

| Field                | Purpose                                                                            |
| -------------------- | ---------------------------------------------------------------------------------- |
| Source ID            | Unique identifier for the Stage 2 source                                           |
| Source title         | Human-readable citation                                                            |
| Source organization  | Publisher or issuing entity                                                        |
| Source date          | Supports inflation and recency assessment                                          |
| Source type          | Contract, grant, budget, report, rate schedule, case study, etc.                   |
| Cost datum used      | Exact figure, rate, percentage, hours, or range taken from the source              |
| Cost datum unit      | Per hour, per interface, per organization, total award, annual run rate, etc.      |
| Original dollar year | Needed for adjustment                                                              |
| Evidence use         | Scope, labor intensity, unit cost, staffing mix, schedule, non-labor cost, or risk |
| Adjustment method    | Inflation, scope normalization, quantity scaling, exclusion of unrelated scope     |
| Supported WBS IDs    | The work packages informed by the source                                           |
| Confidence           | High, moderate, or low                                                             |
| Limitations          | What the source does not support                                                   |

The revised Stage 3 prompt should also require:

> No work package may be labeled “direct analogue,” “bounded analogue,” or “derived from public source” unless it identifies at least one valid Stage 2 Source ID and explicitly states the datum used and the adjustment applied.

## What to require in Stage 4

The Stage 4 model should use a normalized source architecture with at least four linked worksheets.

### 1. Stage 2 Source Register

| Source ID | Source Title | Organization | Date | Source Type | Citation or URL | Dollar Year | Geographic Scope | Program Scope | Confidence | Limitations |

Each source receives one permanent identifier, such as:

* `S2-001`
* `S2-002`
* `S2-003`

Do not reuse or renumber these IDs after the model is circulated.

### 2. Stage 2 Cost Evidence

One row per usable cost datum:

| Evidence ID | Source ID | Cost Datum Description | Original Value | Unit | Original Dollar Year | Scope Included | Scope Excluded | Evidence Classification | Confidence | Notes |

Examples:

| Evidence ID | Source ID | Cost Datum Description         |      Value | Unit                |
| ----------- | --------- | ------------------------------ | ---------: | ------------------- |
| E-001       | S2-004    | Interface implementation labor |        240 | hours per interface |
| E-002       | S2-009    | Participant onboarding award   |    $75,000 | per organization    |
| E-003       | S2-013    | HIE annual operations cost     | $1,200,000 | per year            |

This prevents a source from being cited vaguely without identifying which number was actually used.

### 3. Evidence-to-WBS Mapping

Because one source can support several WBS elements and one WBS element can use multiple sources, use a separate many-to-many mapping table:

| Mapping ID | Evidence ID | WBS ID | Evidence Use | Weight or Role | Adjustment | Used in Low, Base, or High | Notes |
| ---------- | ----------- | ------ | ------------ | -------------- | ---------- | -------------------------- | ----- |

The “weight or role” should use categories such as:

* Primary basis
* Corroborating source
* Lower bound
* Upper bound
* Staffing-pattern evidence
* Scope evidence only
* Reasonableness cross-check

Do not mechanically average multiple sources unless the mapping table explains the method.

### 4. Basis of Estimate

Every cost row should link to the evidence mapping:

| BOE ID | WBS ID | Cost Element | Estimating Method | Quantity | Hours or Unit Cost | Source/Evidence IDs | Adjustment Formula | Result | Confidence |

A formula-backed source attribution might look conceptually like:

> Base hours per interface = Evidence E-001 adjusted downward by 20% because the base case assumes an existing connection rather than a greenfield interface.

That is much stronger than merely writing “based on Stage 2 research.”

## Add source columns directly to the WBS Cost Model

The detailed cost model should include:

| Column                  | Required content                                                     |
| ----------------------- | -------------------------------------------------------------------- |
| Evidence classification | Directly sourced, bounded analogue, bottom-up, expert judgment, etc. |
| Primary Source ID       | Main Stage 2 source                                                  |
| Evidence ID             | Exact datum used                                                     |
| Secondary Source IDs    | Corroborating evidence                                               |
| Original source value   | Source amount or labor quantity                                      |
| Original unit           | Unit from source                                                     |
| Original dollar year    | Year of source cost                                                  |
| Adjustment factor       | Inflation or scope adjustment                                        |
| Adjusted benchmark      | Value after adjustment                                               |
| Model input used        | The actual hours or unit cost entered                                |
| Variance from benchmark | Difference between adjusted benchmark and model input                |
| Attribution note        | Why the source applies                                               |

This allows an independent reviewer to move from the modeled cost back to the exact public datum.

## Formula requirement

Where a sourced amount drives a model input, the model should calculate it rather than manually retype it.

For example:

```text
Adjusted unit cost =
Original source cost
× inflation factor
× scope adjustment factor
× complexity adjustment factor
```

The corresponding workbook formula should reference cells in the evidence table, not a hard-coded number in the WBS sheet.

For a labor benchmark:

```text
Base labor hours =
Source hours per unit
× quantity
× documented complexity factor
```

This makes the traceability auditable and reduces transcription errors.

## Distinguish evidence from judgment

Every model input should be assigned one of these categories:

| Classification                  | Requirement                                                     |
| ------------------------------- | --------------------------------------------------------------- |
| Directly sourced                | Exact source datum used with minimal adjustment                 |
| Derived from source             | Source datum transformed through a documented formula           |
| Bounded analogue                | Source defines a plausible range but is not directly comparable |
| Corroborated bottom-up estimate | Analyst-built estimate checked against one or more sources      |
| Expert judgment                 | No adequate public evidence; judgment explicitly disclosed      |
| Placeholder pending quote       | Temporary value to be replaced                                  |
| Vendor quote                    | Identified quote and date                                       |

A source should not be attached to a bottom-up estimate merely to make it look sourced. The model should state whether the source actually determines the value or only supports reasonableness.

## Add attribution validation checks

Include automated checks such as:

| Check                    | Rule                                                                                              |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| Sourced-row check        | Any row classified as sourced must contain a Source ID and Evidence ID                            |
| Source-register check    | Every cited Source ID must exist in the source register                                           |
| Evidence-register check  | Every Evidence ID must exist in the evidence table                                                |
| Dollar-year check        | Historical monetary values must have a year and adjustment factor                                 |
| Adjustment check         | Derived values must include an adjustment explanation                                             |
| Unsupported-cost check   | Material rows with no source must be classified as bottom-up, judgment, allowance, or placeholder |
| Orphan-evidence check    | Identify Stage 2 evidence not mapped to any WBS element                                           |
| Unused-source check      | Identify sources listed but not actually used                                                     |
| Duplicate-evidence check | Flag the same cost datum used in multiple cost rows where double counting may occur               |

The validation sheet should show `PASS`, `REVIEW`, or `ERROR`.

## Require source-specific comments on calculated cells

For the most material sourced inputs, add a cell note or adjacent attribution field containing:

* Source ID
* Evidence ID
* Original value
* Adjustment
* Final modeled value

This is particularly useful for:

* Labor rates
* Interface implementation assumptions
* Onboarding costs
* HCCN technical-assistance effort
* Hospital integration labor
* Cloud or infrastructure allowances
* Evaluation costs
* Participant stipends

## Update the prompts explicitly

### Add to the revised Stage 2 supplement prompt

> Assign a stable Source ID to every source and a stable Evidence ID to every usable cost datum. Record each datum’s value, unit, dollar year, scope, exclusions, confidence, and limitations. Do not summarize multiple cost data into an undocumented blended benchmark.

### Add to Stage 3

> Every WBS element informed by Stage 2 research must reference the exact Evidence ID used. State whether the evidence supports scope, quantity, hours per unit, labor rate, non-labor unit cost, schedule, or risk. Identify all adjustments and distinguish primary from corroborating evidence.

### Add to Stage 4

> All source-derived model inputs must link by formula or explicit reference to the Stage 2 Cost Evidence table. No source-derived amount may be hard-coded directly into the WBS cost model. Every material cost row must contain either a valid Evidence ID or a clearly identified non-source estimating classification.

## Recommended governance rule

Use this acceptance rule for the revised model:

> A cost is considered traceable only when a reviewer can move from the Executive Summary to the detailed cost row, from the cost row to the BOE entry, from the BOE entry to an Evidence ID, and from the Evidence ID to the original Stage 2 source and datum.

The traceability chain should be:

**Executive total → organization summary → WBS cost row → BOE → Evidence ID → Source ID → original source**

## Recommended next-step sequence

1. Update the Stage 2 research into a structured source-and-evidence register.
2. Conduct the targeted HCCN and hospital-system research using the same identifiers.
3. Revise Stage 3 so every sourced WBS assumption maps to an Evidence ID.
4. Rerun Stage 4 using formula-linked evidence inputs.
5. Run attribution validation before accepting the workbook.

The current model’s generic references such as “Stage 2 bounded analogue” are not sufficient for independent review. The revised model should replace those labels with exact source and evidence identifiers.
