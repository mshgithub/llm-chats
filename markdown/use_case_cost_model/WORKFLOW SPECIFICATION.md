# PHIG B4 Cost Modeling Workflow Specification

**Version:** 1.0  
**Status:** Draft controlling specification  
**Reference implementation:** Chronic Care Cascade Pilot  
**Primary outputs:**  
1. `Cost Model Benchmarks for the [Use Case] Pilot.docx`  
2. `[Use Case] Cost Model Pro Forma.xlsx`

---

## 1. Purpose

This specification defines the deterministic workflow used to develop PHIG B4 pilot use-case cost models.

The workflow preserves the established four-stage cost-modeling methodology:

1. **Scoping**
2. **Benchmark research**
3. **Work breakdown by organization**
4. **Model creation**

The methodology is implemented as a deterministic workflow with bounded agentic steps. The workflow controls stage order, required inputs and outputs, identifiers, validation rules, human gates, state transitions, and selective reruns. Agentic reasoning is used only where interpretation, research judgment, analogue assessment, work decomposition, or estimating judgment is required.

The workflow is designed to produce two persistent, use-case-specific deliverables:

- a benchmark research report; and
- an Excel cost model.

Stage 1 and Stage 3 outputs are required intermediate analytical state. They are not required to be separate client-facing deliverables.

The Chronic Care Cascade benchmark report and pro forma workbook serve as the initial reference implementation and reusable baseline. New use cases are modeled through controlled differences from that baseline rather than by recreating the methodology, evidence base, or workbook from scratch.

---

## 2. Governing principles

### 2.1 Deterministic workflow; bounded agentic judgment

The workflow determines:

- what stage runs;
- which inputs are authoritative;
- what structured outputs are required;
- which identifiers must be assigned;
- when human approval is required;
- when a prior stage must be revisited;
- which validation tests must pass; and
- what constitutes completion.

Agents may exercise judgment within those boundaries, but may not silently change approved upstream state.

### 2.2 Canonical state is authoritative

The authoritative record of the analysis is a set of structured registers maintained across stages.

Narrative reports, chat responses, and spreadsheet summaries are derived views of that state. If a narrative statement conflicts with approved canonical state, the canonical state governs unless the conflict is explicitly resolved and the state is updated.

### 2.3 Traceability is mandatory

Every material modeled cost must be traceable through the following chain:

> **Executive total → organization/workstream summary → cost-model row → basis of estimate → parameter and/or Evidence ID → Source ID or explicit non-source estimating basis → original source or approved assumption**

A model is not considered traceable merely because it contains citations or formulas.

### 2.4 Build from required work, not available budget

The WBS and cost model must represent the work needed to execute the approved pilot scope. A target budget may be used to test affordability, identify scope choices, or develop constrained scenarios, but it may not silently redefine required work.

### 2.5 Price the incremental pilot requirement

Existing platforms, interfaces, hosting, IAM, matching, audit, monitoring, analytics, and other infrastructure are not priced as net-new capabilities unless the approved scope requires them to be newly created, replaced, or materially expanded.

The model must distinguish:

- existing capability reused without incremental cost;
- existing capability requiring pilot-specific configuration;
- contributed infrastructure whose economic value is shown separately, if appropriate;
- incremental capacity or licensing;
- net-new capability required by the pilot; and
- excluded future-state capability.

### 2.6 Preserve uncertainty

Unknown or weakly supported values must remain visible as:

- editable inputs;
- low/base/high ranges;
- scenario switches;
- allowances;
- contingency risks;
- placeholders pending validation; or
- explicit exclusions.

The workflow must not manufacture precision to complete a model.

### 2.7 Use analogues at the work-package level

Whole-project analogues are primarily reasonableness cross-checks and contextual bounds. They must not be mechanically divided across participants or activities unless the source provides a defensible allocation basis.

Component evidence should be matched to the work it actually supports.

### 2.8 Distinguish economic and funding views

At minimum, the workflow preserves separate treatment of:

- sponsor-funded cost;
- participant-funded or participant-incurred cost;
- contractor/vendor cost;
- in-kind labor and contributed resources;
- total economic cost;
- one-time cost;
- recurring pilot-operating cost;
- post-pilot recurring cost, when supportable;
- fixed and variable cost; and
- shared and participant-specific cost.

### 2.9 Reuse does not imply applicability

The Chronic Care Cascade evidence base and workbook are mandatory starting points, not mandatory conclusions.

Reusable cross-cutting structures may include management, governance, legal/privacy/security, specification, configuration, testing, onboarding, operations, evaluation, and closeout.

Use-case-specific adaptation is normally required for:

- minimum datasets;
- source systems;
- standards and implementation guides;
- specialized SMEs;
- transformation or linkage logic;
- outputs;
- workflows;
- evaluation measures;
- organization types; and
- scenario structure.

### 2.10 Selective reruns are preferred to full restarts

When new information changes approved state, the workflow determines which objects are invalidated and reruns only the affected stages and downstream dependencies.

No stage may silently absorb a material upstream change.

---

## 3. Workflow architecture

### 3.1 State machine

```text
INGEST
  ↓
STAGE 1 — SCOPING
  ↓
HUMAN GATE 1 — SCOPE APPROVAL
  ↓
STAGE 2A — CCC BASELINE SCREEN
  ↓
STAGE 2B — TARGETED DELTA RESEARCH
  ↓
STAGE 2C — BENCHMARK REPORT
  ↓
STAGE 3 — ORGANIZATION WBS / ESTIMATING DESIGN
  ↓
HUMAN GATE 2 — CONDITIONAL MATERIALITY GATE
  ↓
STAGE 4A — MODEL DELTA PLAN
  ↓
STAGE 4B — WORKBOOK TRANSFORMATION
  ↓
STAGE 4C — MODEL VALIDATION
  ↓
INDEPENDENT REVIEW
  ↓
FINAL BENCHMARK REPORT + COST MODEL
```

### 3.2 Agents and responsibilities

#### Orchestrator

The orchestrator owns workflow state and stage transitions.

It must:

- initialize project state;
- identify authoritative inputs;
- maintain version and status metadata;
- enforce ID uniqueness;
- enforce gate requirements;
- identify invalidated objects after changes;
- route targeted reruns;
- prevent downstream use of superseded state;
- maintain the change log; and
- determine whether final acceptance criteria are satisfied.

The orchestrator does **not** independently redefine scope, invent benchmarks, construct WBS activities, or modify model logic outside the appropriate stage.

#### Stage 1 Scope Agent

Responsible for:

- scope interpretation;
- participant and organization identification;
- operating model;
- data flows;
- deliverables;
- lifecycle;
- cost drivers;
- assumptions;
- unresolved decisions;
- cost-center requirements; and
- research taxonomy.

It does not develop dollar estimates.

#### Stage 2 Benchmark Agent

Responsible for:

- screening Chronic Care Cascade evidence;
- determining evidence disposition;
- targeted delta research;
- analogue qualification;
- source and Evidence ID creation;
- normalization;
- current-dollar adjustment where required;
- parameter support;
- evidence gaps; and
- benchmark report production.

#### Stage 3 WBS Agent

Responsible for:

- translating approved scope into costable work;
- assigning organizational responsibilities;
- defining performing and cost-bearing organizations;
- distinguishing funded and in-kind work;
- identifying estimating methods;
- linking WBS elements to exact evidence;
- defining scaling logic;
- identifying labor and non-labor inputs;
- preventing double counting;
- defining model inputs; and
- determining Stage 4 readiness.

#### Stage 4 Model Agent

Responsible for:

- inventorying the Chronic Care Cascade workbook;
- generating a model-delta plan;
- modifying the existing workbook rather than recreating it;
- removing excluded parameters and values;
- updating retained parameters;
- adding new parameters;
- preserving unaffected formulas, tables, formatting, and calculation patterns;
- implementing use-case scenarios;
- reconciling summaries;
- validating formulas and traceability; and
- producing the final cost model.

#### Independent Review Agent

Responsible for challenging:

- scope completeness;
- organizational completeness;
- WBS quality;
- analogue use;
- traceability;
- estimating logic;
- labor hours and rates;
- non-labor cost treatment;
- scenario coherence;
- risk and contingency;
- shared costs;
- in-kind costs;
- formulas;
- double counting;
- exclusions;
- sensitivities; and
- executive conclusions.

The independent reviewer must not assume that detail, formulas, or balanced totals imply validity.

---

## 4. Authoritative inputs and precedence

### 4.1 Source hierarchy

Unless the user explicitly establishes a different hierarchy, use the following precedence:

1. **Latest explicit user decision or approved human-gate decision**
2. **Authoritative pilot/use-case description**
3. **Approved Stage 1 canonical state**
4. **Approved Stage 2 evidence**
5. **Approved Stage 3 WBS and estimating state**
6. **Chronic Care Cascade reference artifacts**
7. **Analytical inference or expert judgment**

A lower-ranked input may not silently override a higher-ranked input.

### 4.2 Conflict handling

When inputs conflict:

1. Identify the conflicting statements or state objects.
2. Determine whether the conflict is material to scope, organization, schedule, cost, scenario structure, or evidence.
3. Record a conflict item in the Assumption & Decision Register.
4. Apply an approved or explicit provisional treatment.
5. Identify affected downstream objects.
6. Trigger a human gate if required by the materiality rules.
7. Do not resolve the conflict silently.

### 4.3 Superseded state

All superseded assumptions, decisions, parameters, evidence, WBS elements, and model mappings remain in the audit history but must be marked inactive.

Superseded IDs must not be reused.

---

## 5. Canonical project state

The workflow maintains the following registers.

### 5.1 Project Register

Minimum fields:

| Field | Description |
|---|---|
| Project ID | Stable use-case identifier |
| Project Name | Pilot/use-case name |
| Version | Workflow-state version |
| Status | Current workflow state |
| Authoritative Scope Source | Primary pilot description |
| CCC Baseline Version | Reference benchmark/model version |
| Target Dollar Year | Dollar basis for model |
| Created | Date |
| Last Updated | Date |
| Human Gate 1 Status | Pending/Approved/Approved with conditions |
| Human Gate 2 Status | N/A/Pending/Approved |
| Benchmark Report Version | Current output version |
| Cost Model Version | Current output version |

### 5.2 Scope Register

Each material scope statement receives a stable Scope ID.

Suggested prefix: `SCP-###`

Fields:

| Field | Description |
|---|---|
| Scope ID | Stable identifier |
| Scope Statement | Requirement, boundary, or outcome |
| Classification | Explicit / implied / assumed / excluded / optional |
| Scope Area | Functional / technical / organizational / schedule / evaluation / etc. |
| Source | Original source or decision |
| Confidence | High / Moderate / Low |
| Materiality | Critical / High / Moderate / Low |
| Status | Active / superseded / unresolved |
| Related Organization IDs | Links |
| Related Parameter IDs | Links |
| Related WBS IDs | Populated in Stage 3 |
| Notes | Limitations or interpretation |

### 5.3 Organization Register

Suggested prefix: `ORG-###`

Must distinguish organization **type**, **instance/count**, **performing role**, **cost-bearing role**, and **reporting cost center**.

Fields:

| Field | Description |
|---|---|
| Organization ID | Stable identifier |
| Organization Type | PHA, intermediary, provider, vendor, evaluator, etc. |
| Organization Name | If known |
| Required/Optional | Participation status |
| Quantity | Count |
| Role | Pilot role |
| Performing Organization | Yes/No |
| Cost-Bearing Organization | Yes/No |
| Required Cost Center | Yes/No |
| Funding Treatment | Sponsor-funded / participant-funded / in-kind / mixed / TBD |
| Relationships | Dependencies |
| Source/Basis | Scope or decision |
| Status | Active/superseded |

### 5.4 Assumption & Decision Register

Suggested prefixes:

- `ASM-###` — assumption
- `DEC-###` — approved decision
- `QST-###` — unresolved question

Fields:

| Field | Description |
|---|---|
| ID | Stable identifier |
| Type | Assumption / Decision / Question |
| Statement | Exact issue/treatment |
| Category | Scope / participation / technical / schedule / legal / funding / etc. |
| Basis | Evidence or rationale |
| Low/Base/High | Where applicable |
| Cost Effect | Direction/materiality |
| Confidence | High/Moderate/Low |
| Validation Needed | What would replace uncertainty |
| Owner | Decision/validation owner |
| Status | Active/superseded/resolved |
| Affected IDs | Dependency links |

### 5.5 Cost Driver Register

Suggested prefix: `DRV-###`

Fields include:

- driver;
- definition;
- cost category;
- scaling unit;
- known quantity;
- plausible range;
- affected organizations;
- cost/schedule effect;
- source or assumption;
- fixed/variable/step-fixed;
- one-time/recurring;
- parameter mapping.

### 5.6 Scenario Register

Suggested prefix: `SCN-###`

Scenarios are use-case-specific. Chronic Care Cascade scenarios must not be carried forward unless the new use case supports the same scenario dimensions.

Fields:

| Field | Description |
|---|---|
| Scenario ID | Stable identifier |
| Scenario Name | Human-readable name |
| Scenario Dimensions | Variables that structurally define scenario |
| Included Scope | Scope IDs |
| Excluded Scope | Scope IDs |
| Parameter Overrides | Parameter/value links |
| Optional Components | Included switches |
| Rationale | Why scenario matters |
| Status | Active/inactive |

Low/base/high estimating cases are not necessarily separate structural scenarios. They should normally vary underlying parameter values within a structural scenario.

### 5.7 Parameter Register

Suggested prefix: `PAR-###`

Fields:

| Field | Description |
|---|---|
| Parameter ID | Stable identifier |
| Name | Parameter |
| Definition | Exact meaning |
| Unit | Hours, interfaces, months, %, dollars, etc. |
| Parameter Type | Quantity / effort / rate / unit cost / factor / switch / duration |
| Low | Value |
| Base | Value |
| High | Value |
| Selected Value | Scenario result |
| Value Classification | Sourced / derived / historical / expert judgment / placeholder |
| Evidence IDs | Exact supporting evidence |
| Assumption/Decision IDs | If not directly sourced |
| Original Dollar Year | If monetary |
| Target Dollar Year | If adjusted |
| Adjustment ID | Inflation/escalation link |
| Confidence | High/Moderate/Low |
| Editable | Yes/No |
| Status | Active/superseded |

### 5.8 Source Register

Suggested prefix: `SRC-###`

Source IDs are permanent once circulated. Do not renumber sources merely because a source is later excluded.

Fields:

| Field | Description |
|---|---|
| Source ID | Stable identifier |
| Source Title | Title |
| Organization | Publisher/issuer |
| Date | Publication/award date |
| Source Type | Contract, grant, report, pricing page, study, etc. |
| URL/Citation | Original source |
| Dollar Year | If applicable |
| Geographic Scope | Scope |
| Program/Technical Scope | Scope |
| Source Quality | Primary / secondary |
| Confidence | High/Moderate/Low/Context |
| Limitations | What source does not establish |
| Status | Active/unused/superseded |

### 5.9 Evidence Register

Suggested prefix: `EVD-###`

One row per usable datum or distinct evidence claim.

Fields:

| Field | Description |
|---|---|
| Evidence ID | Stable identifier |
| Source ID | Parent source |
| Evidence Description | Exact datum/claim |
| Original Value | Value or range |
| Unit | Unit |
| Original Dollar Year | If monetary |
| Scope Included | What it covers |
| Scope Excluded | What it excludes |
| Cost-Bearing Organization | Organization represented |
| Evidence Use | Scope / quantity / hours / rate / non-labor / schedule / risk / corroboration |
| Evidence Classification | Direct / derived / bounded analogue / context |
| Confidence | High/Moderate/Low/Context |
| CCC Baseline Disposition | See Section 8 |
| Adjustment Needed | Yes/No |
| Adjustment Method | Normalization/inflation/scope adaptation |
| Supported Parameter IDs | Links |
| Supported WBS IDs | Links |
| Limitations | Explicit limits |
| Status | Active/excluded/superseded |

Do not combine multiple data points into an undocumented blended benchmark.

### 5.10 WBS Register

Suggested prefix: `WBS-[ORG]-##.##`

Each cost-estimating element must be specific enough to assign, scale, and cost.

Minimum fields:

- WBS ID;
- parent WBS ID;
- organization type;
- lifecycle phase;
- workstream;
- work package;
- activity;
- description;
- accountable organization;
- performing organization;
- supporting organizations;
- cost-bearing organization;
- funded/in-kind treatment;
- output/completion condition;
- dependencies;
- scaling classification;
- scaling unit;
- quantity Parameter ID;
- lead labor category;
- supporting labor categories;
- participant/vendor labor;
- non-labor input;
- estimating method;
- Evidence IDs;
- evidence use;
- confidence;
- Assumption IDs;
- Risk IDs;
- scenario applicability;
- recurrence;
- optional/base treatment;
- status.

### 5.11 Model Mapping Register

Suggested prefix: `MAP-###`

The Model Mapping Register controls the relationship between canonical state and the Excel workbook.

Fields:

| Field | Description |
|---|---|
| Mapping ID | Stable identifier |
| WBS ID / Parameter ID | Source state object |
| Workbook Sheet | Destination |
| Table/Range | Destination structure |
| Row/Cell/Named Range | Destination reference |
| Template Element | CCC element being reused/replaced |
| Action | Preserve / Update / Add / Remove / Replace |
| Formula Pattern | Formula or formula family |
| Evidence ID | Where applicable |
| Source ID | Where applicable |
| Notes | Transformation logic |
| Validation Status | PASS/REVIEW/ERROR |

### 5.12 Risk & Uncertainty Register

Suggested prefix: `RSK-###`

Risks must distinguish:

- known scope already included;
- uncertain values represented through low/base/high;
- discrete risks included in contingency;
- optional scope;
- management reserve, if used.

Fields should include probability, cost impact basis, schedule impact, WBS links, scenario treatment, contingency treatment, mitigation, and double-counting check.

### 5.13 Exclusion Register

Suggested prefix: `EXC-###`

Every material exclusion must state:

- excluded work/cost;
- reason;
- likely cost-bearing party;
- potential magnitude, if supportable;
- risk if omitted/misunderstood;
- recommended future/optional treatment; and
- source or decision.

### 5.14 Validation Register

Suggested prefix: `VAL-###`

Fields:

| Field | Description |
|---|---|
| Validation ID | Stable identifier |
| Test | Test name |
| Category | Structural / formula / traceability / reasonableness / reconciliation |
| Object Tested | Workbook/register |
| Result | PASS / REVIEW / ERROR |
| Evidence | Test result |
| Severity | Critical/High/Moderate/Low |
| Correction | Required action |
| Status | Open/closed |

---

## 6. Identifier rules

1. IDs are unique within a project.
2. IDs persist across revisions.
3. IDs are never silently reused.
4. Superseded objects retain their original IDs and are marked inactive.
5. New replacement objects receive new IDs unless the object is genuinely the same parameter/evidence element with an updated value.
6. Source IDs and Evidence IDs must remain stable after a report/model is circulated.
7. The workflow may preserve CCC IDs for CCC baseline objects where practical, but new use-case state must be unambiguous.
8. Human-readable labels may change without changing IDs when the underlying object is unchanged.
9. Every cross-register reference must resolve to an active or explicitly historical object.

---

## 7. Stage 1 — Scoping

### 7.1 Purpose

Convert the authoritative pilot proposal into an estimating-ready scope model without assigning dollar values.

### 7.2 Required inputs

- original pilot/use-case description;
- supplementary design materials;
- user-provided decisions;
- portfolio-wide constraints;
- known schedule and funding constraints;
- Chronic Care Cascade only as methodological context, not as a source of new-use-case scope.

### 7.3 Required analytical outputs

Stage 1 populates or updates:

- Project Register;
- Scope Register;
- Organization Register;
- Assumption & Decision Register;
- Cost Driver Register;
- initial Scenario Register;
- initial Parameter Register for non-dollar quantities;
- initial Risk & Uncertainty Register;
- Exclusion Register;
- research taxonomy.

### 7.4 Organization and cost-center rule

Stage 1 must explicitly identify:

1. every organization type whose work is necessary;
2. every organization type expected to receive funding;
3. every organization type likely to incur unreimbursed effort;
4. every performing organization;
5. every cost-bearing organization; and
6. every organization category that must appear as a distinct reporting cost center.

The workflow must not assume these categories are identical.

### 7.5 Scope classification

Every material statement must be classified as:

- explicit requirement;
- reasonable implication;
- analyst assumption;
- approved decision;
- optional scope;
- exclusion; or
- unresolved question.

### 7.6 Stage 1 completion criteria

Stage 1 is complete only when:

- full lifecycle is represented;
- all organization types are identified;
- major technical flows are documented;
- primary deliverables and completion criteria are represented;
- major cost drivers are parameterized;
- existing-versus-net-new capability is explicit;
- likely in-kind work is identified;
- cost-center structure is explicit;
- scenario dimensions are identified or deliberately deferred;
- material conflicts are logged;
- research taxonomy is use-case-specific; and
- the Stage 1 Human Gate package is prepared.

---

## 8. Human Gate 1 — Scope approval

### 8.1 Mandatory gate

No Stage 2 research may be treated as final until Human Gate 1 is approved.

Research may be explored before approval when useful, but such research remains provisional.

### 8.2 Gate package

Present only the decisions that materially affect cost, architecture, participant structure, research scope, or model structure.

At minimum, where applicable:

- pilot objective and success definition;
- participant/cost-center structure;
- primary workflow/use case;
- primary operational output;
- optional components;
- existing versus net-new capability;
- participant counts;
- interface/source assumptions;
- operating duration;
- scenario dimensions;
- funding/in-kind treatment;
- material exclusions;
- unresolved issues that cannot safely be parameterized.

### 8.3 Approval outcomes

- **Approved**
- **Approved with provisional parameters**
- **Approved with conditions**
- **Return to Stage 1**

Unanswered questions do not automatically block approval. If a question can be safely parameterized without distorting the model, retain it as an editable assumption.

---

## 9. Stage 2 — Benchmark research

Stage 2 consists of three deterministic substeps.

### 9.1 Stage 2A — CCC baseline screen

The Chronic Care Cascade benchmark evidence is reviewed **before** new research.

Screen at the Evidence ID/parameter level, not only at the source level.

Assign one disposition:

| Disposition | Meaning | Default workflow action |
|---|---|---|
| APPLY | Evidence concept and current value are directly applicable | Retain; no new research required solely for this item |
| UPDATE | Same parameter/evidence concept applies, but value is stale or otherwise needs refreshing | Conduct targeted current-value research |
| ADAPT | Evidence is functionally applicable after documented scope/unit/quantity adjustment | Document adaptation; research if adjustment is material or uncertain |
| CORROBORATE | Useful supporting evidence but insufficient as primary BOE | Retain as secondary evidence |
| EXCLUDE | Evidence is not applicable | Prohibit use in model |
| REPLACE | Parameter remains necessary but CCC evidence is inappropriate | Research replacement evidence |
| NEW | New use-case parameter/evidence absent from CCC baseline | Research new evidence |

Disposition is separate from source quality. A high-quality source may still be excluded because it is not applicable.

### 9.2 Baseline-screen criteria

Assess:

- underlying activity similarity;
- organization represented;
- technical similarity;
- scale;
- duration;
- regulatory/security context;
- delivery model;
- funding model;
- unit compatibility;
- recency;
- dollar year;
- whether the CCC value was itself provisional;
- whether the new use case changes the relevant scaling variable.

### 9.3 Stage 2B — Targeted delta research

Fresh research is mandatory for:

- `UPDATE`;
- `REPLACE`;
- `NEW`.

Fresh research is conditional for:

- `ADAPT`;
- `CORROBORATE`.

Fresh research is not required solely for an `APPLY` item when the evidence remains current and applicable.

Research should also occur when:

- Stage 1 identifies a cost-driving organization absent from CCC;
- the use case introduces new technical or regulatory work;
- a CCC benchmark is low-confidence and material;
- the target dollar year or market conditions require an update;
- no credible evidence supports a material parameter;
- an independent reasonableness check is needed for a high-impact assumption.

### 9.4 Source hierarchy

Prioritize:

1. official government procurement/award records;
2. grants/cooperative agreements with cost detail;
3. official program/budget documents;
4. implementation/evaluation reports;
5. public rate schedules and vendor pricing;
6. peer-reviewed implementation studies;
7. secondary sources only when primary evidence is unavailable.

### 9.5 Evidence capture

Every usable datum receives an Evidence ID and records:

- exact value/range;
- unit;
- source;
- dollar year;
- scope included;
- scope excluded;
- organization whose cost it represents;
- proposed use;
- required adjustment;
- confidence;
- limitations.

### 9.6 Normalization

For every derived benchmark:

1. preserve original value;
2. preserve original unit;
3. show the formula;
4. identify numerator and denominator;
5. identify shared fixed costs;
6. identify assumptions;
7. identify dollar-year adjustments;
8. distinguish directly supported unit values from contextual ratios.

Do not divide whole-project totals by participant count and call the result a unit cost unless the allocation is defensible.

### 9.7 Stage 2C — Benchmark report

Produce:

> **Cost Model Benchmarks for the [Pilot Name] Pilot**

The report should preserve the analytical sequence and general presentation of the Chronic Care Cascade reference report while adapting content to the new use case.

Required core content:

1. Executive Summary
2. Methodology and Fit to the Pilot
3. Whole-Project Analogue Awards
4. Component-Level Benchmarks
5. Mapping to the Cost Model
6. Recommended Parameter Defaults
7. Uncertainties and Conservative Modeling Guidance
8. Prioritized Sources and Cost-Structure Observations
9. Source References

The report is a human-readable rendering of the Source, Evidence, Parameter, Risk, and Assumption registers.

### 9.8 Stage 2 completion criteria

Stage 2 is complete only when:

- all CCC evidence relevant to the new model has a disposition;
- all `UPDATE`, `REPLACE`, and `NEW` items have been researched or explicitly marked as evidence gaps;
- material parameters have evidence or an explicit non-source estimating treatment;
- no source-derived parameter lacks an Evidence ID;
- all monetary values have a dollar-year treatment where required;
- benchmark limitations are recorded;
- organization-specific evidence coverage has been assessed; and
- the benchmark report is consistent with the canonical registers.

---

## 10. Stage 3 — Organization-specific WBS and estimating design

### 10.1 Purpose

Translate approved scope and evidence into a complete cost-estimating structure.

Stage 3 is the principal translation layer between research and the Excel model.

### 10.2 Required inputs

- approved Stage 1 state;
- Stage 2 Source and Evidence Registers;
- Stage 2 parameter recommendations;
- benchmark report;
- any post-Stage-1 decisions.

### 10.3 WBS design rule

Build the WBS from required work, not from the evidence available.

Evidence may inform effort, units, staffing, or cost. It may not narrow approved scope.

### 10.4 Required activity classification

Each material activity must identify:

- accountable organization;
- performing organization;
- supporting organizations;
- cost-bearing organization;
- required reporting cost center;
- funded or in-kind treatment;
- fixed/variable/step-fixed treatment;
- one-time/recurring treatment;
- primary scaling unit;
- scenario applicability;
- output/completion condition;
- labor categories;
- non-labor requirements;
- estimating method;
- evidence use;
- risk/uncertainty.

If an activity contains materially different scaling rules, cost-bearing organizations, labor rates, recurrence, or funding treatment, split it.

### 10.5 Evidence attribution rule

No WBS element may be classified as:

- directly sourced;
- derived from public source;
- direct analogue; or
- bounded analogue

unless it identifies at least one exact Evidence ID.

The WBS must state what the evidence supports:

- scope;
- quantity;
- hours per unit;
- staffing composition;
- labor rate;
- non-labor unit cost;
- schedule;
- recurrence; or
- risk range.

Primary and corroborating evidence must be distinguished.

### 10.6 Non-source estimating methods

When evidence is inadequate, use an explicit classification:

- bottom-up labor estimate;
- historical internal estimate;
- vendor quote;
- expert judgment;
- allowance;
- risk-adjusted range;
- placeholder pending validation;
- excluded from sponsor cost but shown in economic cost.

Lack of public evidence does not justify omission.

### 10.7 Shared cost rule

For each shared cost, recommend:

- retain centrally;
- allocate by actual labor usage;
- allocate by participant type;
- allocate by interface/source/use;
- allocate by benefit/usage;
- show only in supplemental allocation view.

Allocations must not change total economic cost.

### 10.8 Double-counting boundary rules

Stage 3 must explicitly test overlap between:

- central PMO and participant PM;
- common architecture and site-specific design;
- legal templates and participant negotiation;
- platform development and source configuration;
- onboarding and technical assistance;
- testing and remediation;
- training and change management;
- stabilization and recurring operations;
- monitoring and evaluation;
- vendor fees and internal labor;
- scenario uncertainty and contingency.

### 10.9 Stage 4 readiness assessment

Stage 3 must classify each material model element as:

- ready to cost;
- requires bottom-up estimation;
- requires vendor quote;
- requires participant validation;
- requires sponsor decision;
- optional/excluded;
- insufficiently defined.

### 10.10 Stage 3 completion criteria

Stage 3 is complete only when:

- every material scope responsibility is represented or excluded;
- every required cost-center organization has a complete cost view;
- every estimable element has a scaling unit;
- every sourced element has exact evidence attribution;
- every non-sourced element has an explicit estimating classification;
- labor and non-labor requirements are identified;
- shared-cost treatment is defined;
- in-kind work is defined;
- double-counting boundaries are established;
- model inputs are enumerated;
- scenario applicability is defined; and
- Stage 4 readiness is assessed.

---

## 11. Human Gate 2 — Conditional materiality gate

### 11.1 Gate trigger

Human Gate 2 is required only when Stage 3 identifies an unresolved issue that would likely:

- add/remove an organization cost center;
- change the fundamental operating model;
- change structural scenario dimensions;
- add/remove a material use case or optional component;
- require a new platform or major infrastructure capability;
- invalidate a primary benchmark;
- materially change the base estimate;
- materially change sponsor-versus-participant funding treatment;
- require workbook structural changes beyond ordinary row/table extension; or
- make Stage 4 assumptions misleading if resolved incorrectly.

### 11.2 No-gate cases

Do not trigger the gate merely because:

- a labor-hour value is provisional;
- a vendor quote is pending and can be parameterized;
- a low-confidence parameter has a transparent range;
- a participant count remains editable;
- a minor non-labor cost is uncertain;
- an unresolved issue can safely be represented by an explicit scenario or switch.

### 11.3 Gate outputs

- approve provisional treatment;
- select among alternatives;
- revise Stage 1 scope;
- trigger targeted Stage 2 research;
- trigger partial Stage 3 regeneration.

---

## 12. Stage 4 — Model creation

Stage 4 consists of three deterministic substeps.

### 12.1 Governing rule

The Chronic Care Cascade workbook is the authoritative template.

The workflow must **modify the existing workbook**, not independently recreate an equivalent workbook.

### 12.2 Template preservation requirement

Preserve unless a documented model delta requires change:

- worksheets;
- worksheet order;
- tables;
- table styles;
- formulas and formula patterns;
- named ranges;
- formatting conventions;
- input/calculated-cell conventions;
- summary design;
- scenario-selection conventions;
- notes/cell comments where used;
- chart styles where present.

Use-case-specific rows, columns, formulas, tables, labels, parameters, and scenario structures may be changed when necessary.

Chronic-specific content must not be retained merely to preserve structure.

### 12.3 Stage 4A — Workbook inventory

Before modification:

1. Load the CCC workbook.
2. Inventory all worksheets.
3. Inventory tables and named ranges.
4. Identify input cells/tables.
5. Identify calculation regions.
6. Identify formulas and recurring formula patterns.
7. Identify scenario controls.
8. Identify summary reconciliations.
9. Identify source/benchmark columns.
10. Identify optional-component logic.
11. Identify formatting conventions.
12. Identify formulas or structures that embed chronic-specific assumptions.

### 12.4 Stage 4A — Model Delta Plan

Every material workbook change receives a Model Mapping/Delta entry.

Actions:

- `PRESERVE`
- `UPDATE`
- `ADD`
- `REMOVE`
- `REPLACE`

Example:

| Delta | Template Element | Action | Reason | Governing State |
|---|---|---|---|---|
| MD-001 | Chronic measure parameter | REMOVE | Not applicable | Scope |
| MD-002 | Source configuration count | UPDATE | New participant architecture | PAR-### |
| MD-003 | Linkage work package | ADD | Required by new use case | WBS-### |
| MD-004 | HCCN scenario | REMOVE | HCCN absent | ORG-### |

The Model Delta Plan must be completed before workbook transformation.

### 12.5 Stage 4B — Parameter transformation

For each CCC parameter:

1. identify the corresponding new-use-case parameter, if any;
2. use Stage 2 disposition:
   - Apply;
   - Update;
   - Adapt;
   - Corroborate;
   - Exclude;
   - Replace;
   - New;
3. remove excluded values;
4. update retained values;
5. add new parameters;
6. preserve source/evidence attribution;
7. preserve formulas where the underlying estimating relationship remains valid;
8. replace formulas only when the cost-driving relationship changes.

### 12.6 Source-derived input rule

No material source-derived amount may be entered into the cost build-up as an unexplained hard-coded value.

Each source-derived input must resolve to:

- Parameter ID;
- Evidence ID;
- Source ID;
- original value;
- adjustment method;
- modeled value.

Where workbook architecture does not contain dedicated Source/Evidence tables, this linkage may be implemented through existing source columns, notes, adjacent attribution fields, named ranges, or supporting tables while preserving the template architecture.

### 12.7 Formula principles

Use formulas rather than hard-coded calculated totals.

Representative patterns:

```text
Total hours = Fixed hours + (Quantity × Hours per unit)

Interface hours =
Participant count × Interfaces per participant × Hours per interface

Recurring labor hours =
Monthly labor hours × Operating months

Labor cost =
Total hours × Appropriate loaded rate

Non-labor cost =
Quantity × Unit cost

Scenario value =
Lookup or formula based on scenario inputs
```

Complexity may modify quantity **or** effort, but must not be applied twice.

### 12.8 Scenario methodology

Structural scenarios should represent materially different delivery configurations.

Low/base/high estimating cases should be driven by underlying values such as:

- participant count;
- source/interface count;
- complexity;
- labor effort;
- rate;
- duration;
- vendor cost;
- support intensity;
- evaluation rigor.

Do not create a high case by applying an arbitrary percentage to the base case.

### 12.9 Optional component rule

Use an optional add-on only when the scope is genuinely separable.

Changes in:

- participant count;
- source count;
- interface count;
- remediation cycles;
- operating duration;
- support intensity;
- environment capacity; or
- ordinary complexity

should normally be modeled as base parameters, sensitivities, or scenarios rather than optional add-ons.

### 12.10 Contingency rule

Do not use contingency to price known scope.

Avoid counting the same uncertainty in:

- low/base/high ranges; and
- contingency.

Contingency should be tied to identified residual risks or another explicit method.

### 12.11 Reconciliation requirement

After structural model changes:

- reconcile the new cost architecture to the prior CCC baseline where comparison is meaningful;
- explain major deltas;
- distinguish scope change from evidence/value change;
- distinguish cost reallocation from actual economic-cost change;
- confirm shared-cost allocation does not change the total;
- confirm removal/addition of cost centers does not hide costs.

---

## 13. Stage 4C — Deterministic validation suite

The following tests are mandatory.

### 13.1 Structural tests

- every material WBS element is costed or explicitly excluded;
- every cost row resolves to a valid WBS ID;
- every Parameter ID resolves;
- every labor category resolves to a rate or explicit placeholder;
- every non-labor item maps to a valid cost element;
- all organization and cost-center IDs resolve;
- all scenario references resolve;
- all summary totals reconcile.

### 13.2 Evidence and traceability tests

| Test | Requirement |
|---|---|
| Sourced-row check | Every sourced cost/parameter contains an Evidence ID |
| Source-register check | Every Source ID exists |
| Evidence-register check | Every Evidence ID exists |
| Evidence-source check | Every Evidence ID resolves to exactly one Source ID |
| Dollar-year check | Historical monetary evidence records its year |
| Adjustment check | Derived/adjusted values contain an adjustment basis |
| Unsupported-cost check | Material unsourced rows are explicitly classified as bottom-up/judgment/allowance/placeholder |
| Excluded-evidence check | `EXCLUDE` evidence is not used |
| Orphan-evidence check | Evidence expected to support the model but mapped nowhere is flagged |
| Unused-source check | Sources listed but never used are identified |
| Duplicate-evidence check | Same datum used in multiple rows is checked for double counting |

### 13.3 Formula tests

- no broken references;
- no circular references;
- no formulas referencing deleted rows/sheets/ranges;
- correct absolute/relative reference behavior;
- correct scenario lookup logic;
- no quantity multiplied twice;
- no duration multiplied twice;
- no complexity applied twice;
- no inflation/escalation applied twice;
- no contingency applied twice;
- low/base/high references use the correct assumptions;
- allocated views do not alter total cost;
- in-kind cost is not counted in both sponsor and economic totals.

### 13.4 Reasonableness tests

- adding participants increases relevant variable costs;
- adding an interface increases interface-specific work;
- extending operations increases recurring cost;
- fixed costs do not scale merely because participant count increases;
- high-complexity work does not cost less without explanation;
- recurring costs use correct operating duration;
- marginal cost differs appropriately from fully allocated average cost;
- model outputs are reasonably bounded by evidence or explain why not.

### 13.5 Case ordering test

Normally:

`Low ≤ Base ≤ High`

Any exception must have a documented reason.

### 13.6 Validation statuses

Every validation returns:

- `PASS`
- `REVIEW`
- `ERROR`

`ERROR` blocks final delivery unless explicitly waived through an approved human decision.

`REVIEW` requires documented disposition.

---

## 14. Independent review

### 14.1 Independence

The independent reviewer receives:

- original pilot description;
- approved Stage 1 state;
- Stage 2 benchmark report and evidence;
- Stage 3 WBS and estimating design;
- Stage 4 workbook;
- validation results;
- change log.

The reviewer must not presume the model is valid because it was produced by the workflow.

### 14.2 Review dimensions

At minimum:

1. Scope completeness
2. Organizational completeness
3. WBS quality
4. Estimate methodology
5. Analogue quality
6. Source traceability
7. Quantity/scaling logic
8. Labor-hour reasonableness
9. Labor-rate reasonableness
10. Non-labor completeness
11. Scenario integrity
12. Risk/contingency
13. Shared costs
14. In-kind treatment
15. Formula/arithmetic integrity
16. Double-counting prevention
17. Exclusions
18. Sensitivity analysis
19. Executive-summary accuracy
20. Decision usefulness

### 14.3 Finding severity

- Critical
- High
- Moderate
- Low
- Observation

Critical and High findings require resolution or explicit executive acceptance before a model is described as suitable for decision use.

---

## 15. Selective rerun and dependency rules

### 15.1 General rule

A change invalidates the changed object and any downstream object whose logic depends materially on it.

The orchestrator identifies affected objects by explicit links rather than by rerunning every stage.

### 15.2 Typical changes and workflow response

#### Quantity change

Example:

`Provider networks: 6 → 10`

Default response:

- Stage 1: update parameter and affected organization quantity;
- Stage 2: no rerun unless scale comparability is materially affected;
- Stage 3: update affected per-organization/per-interface quantities;
- Stage 4: recalculate and revalidate.

#### New organization type or cost center

Example:

`Generic provider → HCCN + hospital system`

Default response:

- Stage 1: revise Organization Register and responsibilities;
- Stage 2: targeted research for new organization-specific evidence;
- Stage 3: regenerate affected organization-specific WBS;
- Stage 4: update cost centers/model mappings;
- validation: reconcile new cost allocation to prior total.

#### Existing capability becomes unavailable

Example:

`Existing MPI = true → false`

Default response:

- Stage 1: reopen architecture/scope;
- Stage 2: research linkage/MPI implementation evidence;
- Stage 3: add design/build/test/operate WBS;
- Human Gate 2 likely required;
- Stage 4: structural model update and validation.

#### Source benchmark value becomes stale

Default response:

- Stage 2: update exact Evidence ID or create replacement evidence;
- Stage 3: verify evidence use still valid;
- Stage 4: update parameter and recalculate;
- no Stage 1 rerun.

#### Optional component activated

Default response:

- verify component is already defined;
- if yes: update Scenario/Parameter Register and Stage 4 switch;
- if no: return to Stage 1/2/3 for scope, evidence, and WBS definition before costing.

### 15.3 Full rerun triggers

A full four-stage rerun should be unusual. It may be required when:

- the use case is fundamentally replaced;
- the operating model changes entirely;
- authoritative source documents materially redefine the pilot;
- the participant architecture is comprehensively redesigned; or
- prior canonical state is judged unreliable.

---

## 16. Materiality rules

The workflow should focus human attention on decisions that can change the decision outcome.

Until quantitative materiality thresholds are approved, classify an issue as materially cost-sensitive when it plausibly:

- changes a major cost center;
- changes a principal scenario;
- changes the largest cost drivers;
- adds/removes a major technical component;
- changes pilot duration materially;
- changes participant funding policy;
- invalidates a primary source/analogue;
- changes recurring cost structure; or
- creates a step-change risk.

The workflow may later adopt numerical thresholds, such as percentage-of-base-cost or dollar thresholds, without changing the methodology.

---

## 17. Workbook preservation and change-control rules

### 17.1 CCC workbook as baseline

The current Chronic Care Cascade workbook is retained as the template baseline.

Before each use-case run:

- preserve an untouched baseline copy;
- create a use-case working copy;
- record baseline file/version/hash where available;
- record every structural modification.

### 17.2 Permitted modifications

Permitted when required by approved state:

- changing labels;
- changing scenario definitions;
- changing assumptions;
- removing chronic-specific parameters;
- adding use-case-specific parameters;
- adding/removing WBS rows;
- extending existing tables;
- updating formulas to reflect changed scaling logic;
- modifying optional add-ons;
- modifying summaries to reflect new organization types;
- adding attribution fields where necessary;
- correcting detected formula defects.

### 17.3 Prohibited modifications without explicit rationale

- wholesale redesign of workbook architecture;
- replacing existing formula-driven calculations with hard-coded totals;
- deleting traceability fields merely to simplify presentation;
- changing formatting conventions without need;
- silently overwriting the baseline workbook;
- preserving irrelevant CCC rows solely because they exist in the template.

---

## 18. Change log

Every workflow run maintains a change log.

Minimum fields:

| Change ID | Date | Stage | Object ID(s) | Change | Reason | Initiator | Upstream/Downstream Effect | Rerun Required | Status |

The final package should support answering:

- What changed since the CCC baseline?
- What changed since the prior version of this use-case model?
- Why did the cost change?
- Was the change caused by scope, evidence, quantity, rate, formula, scenario, allocation, or correction?
- Which human decision authorized the change?

---

## 19. Error handling and stop conditions

### 19.1 Block Stage 2 finalization when

- Human Gate 1 is not approved;
- authoritative scope cannot be identified;
- participant/cost-center structure remains fundamentally ambiguous.

### 19.2 Block Stage 4 transformation when

- Stage 3 is not estimating-ready;
- required WBS/cost-center architecture is unresolved;
- material source-derived inputs lack evidence attribution and cannot be replaced by explicit non-source methods;
- Human Gate 2 is triggered and unresolved.

### 19.3 Block final delivery when

- workbook cannot be opened;
- formulas contain unresolved errors;
- executive totals do not reconcile;
- sponsor/in-kind/economic totals are internally inconsistent;
- a material sourced amount cannot be traced;
- excluded evidence is used;
- a Critical independent-review finding remains unresolved;
- validation contains unresolved `ERROR` results.

### 19.4 Do not block solely because

- evidence is weak but transparently classified;
- vendor quotes are pending and parameterized;
- a low-confidence range is disclosed;
- an evidence gap is handled by an explicit bottom-up estimate;
- optional future scope remains unpriced with disclosure.

---

## 20. Final deliverables

### 20.1 Benchmark research report

File naming:

`Cost Model Benchmarks for the [Use Case] Pilot.docx`

Must be consistent with:

- Source Register;
- Evidence Register;
- Parameter Register;
- Stage 1 scope;
- Stage 3 modeling implications.

### 20.2 Cost model

File naming:

`[Use Case] Cost Model Pro Forma.xlsx`

Must:

- use the CCC workbook as template;
- preserve applicable workbook structures and formatting;
- contain formula-driven calculations;
- contain editable cost-sensitive assumptions;
- distinguish funding and economic views;
- preserve source and assumption traceability;
- calculate use-case-specific scenarios;
- reconcile summaries to detail;
- disclose exclusions and uncertainties;
- pass validation.

### 20.3 Internal workflow artifacts

The following may remain internal unless requested:

- canonical registers;
- baseline-screen matrix;
- model-delta plan;
- validation register;
- change log;
- independent-review findings and resolution log.

These internal artifacts are still required workflow state even when they are not delivered to the client.

---

## 21. Final acceptance criteria

The workflow is complete only when all of the following are true.

### Scope and organization

1. Approved scope is represented.
2. Every necessary organization type is represented.
3. Performing and cost-bearing organizations are distinguished.
4. Required reporting cost centers are explicit.
5. Optional and excluded scope are explicit.

### Evidence

6. CCC evidence has been screened at the evidence/parameter level.
7. All `UPDATE`, `REPLACE`, and `NEW` evidence needs have been addressed or explicitly documented as gaps.
8. Every material source-derived input has an Evidence ID.
9. Every Evidence ID resolves to a Source ID.
10. Adjustments and dollar-year treatments are transparent.

### WBS and estimating design

11. Every material activity is costed or explicitly excluded.
12. Every estimable activity has a scaling unit.
13. Fixed and variable work are distinguishable.
14. One-time and recurring work are distinguishable.
15. Funded and in-kind work are distinguishable.
16. Labor and non-labor requirements are distinguishable.
17. Shared-cost treatment is defined.
18. Double-counting boundaries are documented.

### Model

19. CCC workbook structure is preserved except for documented deltas.
20. Excluded CCC parameters/values are removed.
21. Applicable parameters are retained or updated.
22. New parameters are added where required.
23. Formulas reflect the approved scaling relationships.
24. Low/base/high cases are driven by underlying assumptions.
25. Scenario logic is use-case-specific.
26. Optional components are genuinely separable.
27. Contingency does not double count scenario uncertainty.
28. Sponsor, participant, in-kind, and total economic costs reconcile.
29. One-time and recurring costs reconcile.
30. Organization, phase, and workstream summaries reconcile to detail.

### Validation and review

31. All deterministic validation tests are `PASS` or resolved `REVIEW`.
32. No unresolved `ERROR` remains.
33. No unresolved Critical independent-review finding remains.
34. High findings are corrected or explicitly accepted.
35. Major changes from the CCC baseline and prior model version are explainable.
36. A reviewer can traverse the full traceability chain from executive total to original evidence or approved assumption.
37. The model can be updated through parameters and controlled deltas without reconstructing it from scratch.

---

## 22. Recommended execution modes

### 22.1 Interactive mode

Use when:

- scope is still being shaped;
- participant details are incomplete;
- high-impact assumptions need human judgment;
- the cost model will be reviewed closely by sponsors or participants.

Human Gate 1 is mandatory; Human Gate 2 operates as defined above.

### 22.2 Batch mode

Use only when:

- Stage 1 inputs are sufficiently standardized;
- approved defaults exist;
- use cases share stable portfolio constraints;
- unresolved items can be safely parameterized.

Batch mode does not remove validation or evidence requirements. It only reduces interactive approvals.

---

## 23. Design requirements for the four stage prompts

The individual prompts must be usable both manually and within the orchestrated workflow.

Each prompt must therefore contain:

1. **Purpose**
2. **Authoritative inputs**
3. **Canonical registers read**
4. **Canonical registers written**
5. **Permitted agent judgment**
6. **Prohibited actions**
7. **Required analytical outputs**
8. **ID and traceability rules**
9. **Conflict-handling rules**
10. **Validation checks**
11. **Stage exit criteria**
12. **Rerun/invalidation behavior**

The prompts must not depend on conversational memory for material state.

When run manually, the prompt may render the canonical state as structured tables or sections. When orchestrated, the same content may be stored in machine-readable form.

---

## 24. Reference implementation lessons incorporated from Chronic Care Cascade

The workflow incorporates the following lessons from development of the Chronic Care Cascade model:

- participant definitions can change after early scope analysis and require targeted benchmark research plus WBS/model restructuring;
- changing cost-center structure may alter cost allocation more than total cost, so reconciliation is required;
- generic benchmark labels are insufficient for independent review;
- Source IDs and Evidence IDs must be explicit and stable;
- source-derived values require documented adjustment from original evidence to modeled parameter;
- existing intermediary/platform capabilities should be priced as incremental pilot deltas rather than replacement value;
- participant in-kind effort must remain visible;
- whole-project analogues are useful as bounds, not mechanical cost allocators;
- ordinary scale changes belong in parameters/sensitivities, while genuinely separable scope belongs in optional components;
- formula correctness and conceptual estimating validity require separate checks;
- a model should remain provisional where rates, participant indirects, vendor fees, topology, readiness, or other material inputs require validation.

---

## 25. Future implementation considerations

This specification intentionally separates methodology from software implementation.

A future orchestrated implementation may represent the canonical registers in:

- JSON;
- relational tables;
- a lightweight database;
- spreadsheet support tables; or
- another typed state store.

Regardless of implementation technology, the following are invariant:

- stable IDs;
- explicit state transitions;
- authoritative-input precedence;
- human gates;
- evidence-level benchmark disposition;
- selective reruns;
- model-delta transformation;
- deterministic validation; and
- end-to-end traceability.

The workflow should be implemented as a **deterministic pipeline containing agentic steps**, not as a set of autonomous peer agents negotiating state.

---

## 26. Workflow summary

```text
AUTHORITATIVE PILOT INPUTS
        ↓
STAGE 1: STRUCTURED SCOPE STATE
        ↓
MANDATORY HUMAN SCOPE GATE
        ↓
CCC EVIDENCE BASELINE SCREEN
        ↓
TARGETED DELTA RESEARCH
        ↓
BENCHMARK REPORT + SOURCE/EVIDENCE/PARAMETER STATE
        ↓
STAGE 3 ORGANIZATION-SPECIFIC WBS
        ↓
CONDITIONAL MATERIALITY GATE
        ↓
CCC WORKBOOK INVENTORY
        ↓
MODEL DELTA PLAN
        ↓
CONTROLLED WORKBOOK TRANSFORMATION
        ↓
DETERMINISTIC VALIDATION
        ↓
INDEPENDENT REVIEW
        ↓
BENCHMARK REPORT + COST MODEL
```

The workflow is successful when the final cost estimate is not merely plausible, but **repeatable, explainable, source-traceable, structurally comparable across use cases, and updateable through controlled changes rather than model reconstruction**.
