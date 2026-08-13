# PHIG B4 Cost Modeling Workflow — README

## Purpose

This package defines a repeatable workflow for developing PHIG B4 pilot use-case cost models using a **deterministic pipeline with bounded agentic reasoning**.

The workflow is designed to produce two persistent use-case-specific deliverables:

1. **Cost Model Benchmarks for the [Use Case] Pilot**
2. **[Use Case] Cost Model Pro Forma**

The methodology uses the Chronic Care Cascade pilot as the initial reference implementation and reusable baseline, while requiring each new use case to be modeled from its own approved scope, organizations, evidence, work breakdown, and scenario structure.

The workflow is intended to support both:

- **manual execution in ChatGPT or another capable AI environment today**, and
- **future implementation as an orchestrated agentic workflow** using structured state.

---

# 1. What is in this package

The implementation package consists of five layers.

## 1.1 Controlling workflow specification

**`WORKFLOW SPECIFICATION.md`**

Defines the overall methodology and operating rules, including:

- four-stage workflow;
- deterministic versus agentic responsibilities;
- canonical state;
- human gates;
- evidence traceability;
- selective reruns;
- workbook-transformation rules;
- validation;
- independent review;
- final acceptance criteria.

This is the controlling methodological document.

---

## 1.2 Orchestrator

**`PHIG B4 COST MODELING - ORCHESTRATOR PROMPT.md`**

Controls:

- workflow state;
- stage eligibility;
- human gates;
- project-state versioning;
- stale-state detection;
- change detection;
- dependency analysis;
- targeted reruns;
- correction cycles;
- finalization.

The orchestrator should not replace the stage agents. It determines **what should run and why**.

---

## 1.3 Stage prompts

### Stage 1

**`STAGE 1 - SCOPING PROMPT.md`**

Converts the pilot proposal into estimating-ready structured scope.

Outputs include:

- scope;
- organization/cost-center structure;
- responsibilities;
- technical/data flows;
- lifecycle;
- cost drivers;
- initial parameters;
- risks;
- exclusions;
- research taxonomy;
- Human Gate 1 decision package.

Stage 1 does **not** estimate dollars.

---

### Stage 2

**`STAGE 2 - BENCHMARK RESEARCH PROMPT.md`**

Begins with the Chronic Care Cascade benchmark evidence and conducts targeted delta research.

Core sequence:

```text
CCC evidence baseline
        ↓
APPLY / UPDATE / ADAPT / CORROBORATE / EXCLUDE / REPLACE / NEW
        ↓
Targeted delta research
        ↓
Source IDs + Evidence IDs
        ↓
Model-ready parameters
        ↓
Benchmark report
```

Stage 2 produces the first persistent deliverable:

**`Cost Model Benchmarks for the [Use Case] Pilot.docx`**

---

### Stage 3

**`STAGE 3 - ORGANIZATION WBS PROMPT.md`**

Translates approved scope plus exact evidence into the estimating design.

Outputs include:

- organization-specific WBS;
- performing vs cost-bearing organization;
- funding/in-kind treatment;
- scaling logic;
- labor/non-labor inputs;
- estimating method;
- Evidence ID linkage;
- shared-cost treatment;
- double-counting rules;
- model-input register;
- Stage 4 readiness;
- Human Gate 2, if required.

Stage 3 is the principal translation layer between research and the spreadsheet model.

---

### Stage 4

**`STAGE 4 - MODEL CREATION PROMPT.md`**

Creates the final use-case model by modifying the actual Chronic Care Cascade workbook.

Core sequence:

```text
CCC workbook
      ↓
Workbook inventory
      ↓
Model Delta Plan
      ↓
Controlled workbook transformation
      ↓
WBS / Parameter / Evidence mappings
      ↓
Formula and reconciliation validation
      ↓
Final cost model
```

Stage 4 produces:

**`[Use Case] Cost Model Pro Forma.xlsx`**

---

## 1.4 Independent review

**`INDEPENDENT REVIEW PROMPT - REVISED.md`**

Performs an independent conceptual review of:

- scope;
- organization coverage;
- WBS;
- evidence;
- benchmark reuse;
- parameter provenance;
- formulas;
- labor;
- non-labor;
- scenarios;
- contingency;
- in-kind;
- shared costs;
- model deltas;
- reconciliation;
- executive conclusions.

The review deliberately does not assume the model is valid because it passed deterministic validation.

---

## 1.5 Canonical register schemas

Folder:

**`PHIG B4 Cost Modeling Schemas/`**

The schemas define the authoritative project state.

Key registers include:

- Project Register
- Scope Register
- Organization Register
- Assumption & Decision Register
- Cost Driver Register
- Scenario Register
- Parameter Register
- Source Register
- Evidence Register
- WBS Register
- Model Mapping Register
- Risk & Uncertainty Register
- Exclusion Register
- Validation Register
- Shared Cost Register
- In-Kind Cost Register
- Double-Counting Register
- Model Input Register
- Change Log
- Human Gate Register

These schemas are implementation-neutral.

They can be represented as:

- Markdown tables;
- JSON;
- relational tables;
- spreadsheet support tables;
- another typed state store.

---

# 2. Reference artifacts

The workflow assumes the following Chronic Care Cascade reference artifacts are available.

## 2.1 Benchmark baseline

**`Cost Model Benchmarks for the Chronic Care Cascade Pilot v2.docx`**

Used as:

- the initial benchmark evidence library;
- a source of reusable cross-cutting implementation evidence;
- the structural reference for future benchmark reports.

It is **not** authority for the new use case's scope.

---

## 2.2 Workbook baseline

**`Chronic Care Cascade Cost Model Pro Forma v2.xlsx`**

Used as:

- the authoritative Excel template;
- the baseline formula architecture;
- the formatting/convention baseline;
- the starting point for controlled model transformation.

Do not recreate an equivalent workbook from scratch.

Always preserve the original CCC workbook.

---

# 3. Core workflow

The recommended operating sequence is:

```text
INGEST
  ↓
STAGE 1 — SCOPING
  ↓
HUMAN GATE 1
  ↓
STAGE 2 — BENCHMARK RESEARCH
  ↓
STAGE 3 — ORGANIZATION WBS
  ↓
HUMAN GATE 2, IF TRIGGERED
  ↓
STAGE 4 — MODEL CREATION
  ↓
INDEPENDENT REVIEW
  ↓
CORRECTIONS, IF REQUIRED
  ↓
FINAL
```

---

# 4. The two persistent deliverables

Although the workflow creates substantial intermediate state, only two artifacts are required as persistent use-case deliverables.

## Benchmark report

```text
Cost Model Benchmarks for the [Use Case] Pilot.docx
```

Produced in Stage 2.

---

## Cost model

```text
[Use Case] Cost Model Pro Forma.xlsx
```

Produced in Stage 4.

---

## Internal working state

The following may remain internal:

- scope register;
- organization register;
- assumptions;
- Source/Evidence registers;
- WBS;
- model-input register;
- baseline disposition matrix;
- Model Delta Plan;
- validation results;
- change log;
- independent-review findings.

They remain mandatory workflow state even when they are not client-facing.

---

# 5. Manual execution in ChatGPT

The workflow can be run manually before any orchestration software is built.

## Step 1 — Start a new use case

Upload/provide:

- use-case proposal;
- relevant supplementary materials;
- `WORKFLOW SPECIFICATION.md`;
- `STAGE 1 - SCOPING PROMPT.md`.

Then instruct:

> Run Stage 1 of the PHIG B4 Cost Modeling Workflow using the attached use-case materials. Follow the controlling workflow specification and Stage 1 prompt. Produce the canonical Stage 1 state and Human Gate 1 package. Do not proceed to Stage 2.

---

## Step 2 — Review Human Gate 1

Review only the material decisions surfaced by Stage 1.

Provide explicit decisions.

Examples:

- participant count;
- operating model;
- cost-center organizations;
- data scope;
- live-operation duration;
- existing versus net-new capability;
- optional scope;
- exclusions.

Then tell the model to update the canonical state and mark Gate 1 approved.

---

## Step 3 — Run Stage 2

Provide:

- approved Stage 1 output/state;
- `STAGE 2 - BENCHMARK RESEARCH PROMPT.md`;
- CCC benchmark report.

Instruction:

> Run Stage 2 using the approved Stage 1 state. Begin with the CCC evidence baseline screen. Conduct targeted delta research only as required by the evidence-disposition rules. Produce the benchmark report and Source/Evidence/Parameter state. Do not proceed to Stage 3.

Stage 2 should use current web research for all required `UPDATE`, `REPLACE`, and `NEW` evidence.

---

## Step 4 — Run Stage 3

Provide:

- approved Stage 1 state;
- Stage 2 benchmark report;
- Source/Evidence/Parameter state;
- `STAGE 3 - ORGANIZATION WBS PROMPT.md`.

Instruction:

> Run Stage 3. Translate approved scope and Stage 2 evidence into the organization-specific WBS and estimating design. Preserve exact Evidence IDs. Determine whether Human Gate 2 is triggered. Do not proceed to Stage 4.

---

## Step 5 — Resolve Human Gate 2 if required

Only review the issues Stage 3 identifies as materially structural or cost-sensitive.

If no Gate 2 is triggered, proceed directly to Stage 4.

---

## Step 6 — Run Stage 4

Provide:

- Stage 1 approved state;
- Stage 2 evidence;
- Stage 3 WBS;
- CCC workbook;
- `STAGE 4 - MODEL CREATION PROMPT.md`.

Instruction:

> Run Stage 4. Modify the attached CCC workbook as the authoritative template. Inventory it first, create the Model Delta Plan, apply approved deltas, preserve applicable formula/format patterns, and run the required validation suite. Produce the final use-case workbook.

Do not ask the model to "make a workbook similar to" the CCC workbook.

The instruction should always be to **modify the actual template**.

---

## Step 7 — Independent review

Provide:

- original use-case proposal;
- approved gate decisions;
- Stage 2 benchmark report;
- Stage 3 WBS/state;
- final workbook;
- model delta/validation outputs;
- `INDEPENDENT REVIEW PROMPT - REVISED.md`.

Instruction:

> Perform the independent review. Treat the original pilot description and approved human decisions as authoritative. Independently test evidence use, WBS completeness, model logic, formula integrity, double counting, scenario treatment, reconciliation, and decision usefulness.

---

# 6. Recommended use of a Project workspace

For manual execution, keep one project/workspace per pilot use case.

Recommended files:

```text
/use-case/
    Pilot Proposal
    Supporting Materials

/reference/
    WORKFLOW SPECIFICATION.md
    ORCHESTRATOR PROMPT.md
    STAGE 1 PROMPT.md
    STAGE 2 PROMPT.md
    STAGE 3 PROMPT.md
    STAGE 4 PROMPT.md
    INDEPENDENT REVIEW PROMPT.md
    CCC Benchmark Report
    CCC Workbook

/state/
    Project Register
    Scope Register
    Organization Register
    Assumption Decision Register
    Parameter Register
    Source Register
    Evidence Register
    WBS Register
    Model Mapping Register
    Validation Register
    Change Log

/output/
    Benchmark Report
    Cost Model
    Independent Review
```

Exact storage structure can vary.

The important rule is that the **current canonical state must remain identifiable**.

---

# 7. How to use the orchestrator manually

The orchestrator prompt can be used as the top-level controller in a long-running ChatGPT project.

Provide:

- workflow specification;
- orchestrator prompt;
- all stage prompts;
- schema package;
- reference artifacts;
- current project state.

Then instruct:

> Act as the PHIG B4 Cost Modeling Orchestrator. Determine the current workflow state, identify the next eligible stage, and invoke or prepare only the work required for that stage. Preserve canonical IDs, enforce human gates, and use targeted reruns rather than restarting unaffected work.

The orchestrator should return a concise status after each stage:

- current workflow state;
- state changes;
- validation results;
- gate status;
- stale outputs;
- next required action.

---

# 8. Targeted reruns

One of the workflow's most important design features is the ability to rerun only affected work.

## Example — participant count changes

Suppose:

```text
PAR-014 Provider organizations = 6
```

changes to:

```text
PAR-014 Provider organizations = 10
```

Default response:

- update the parameter;
- update organization quantity if relevant;
- do not rerun Stage 2 unless scale comparability changes;
- update Stage 3 variable WBS quantities;
- recalculate Stage 4;
- rerun affected validations.

---

## Example — new organization type

Suppose the model originally used:

```text
Generic provider organization
```

and later needs separate:

```text
HCCN
Hospital system
```

Default response:

- targeted Stage 1 organization/cost-center update;
- targeted Stage 2 HCCN/hospital evidence supplement;
- regenerate affected Stage 3 organization-specific WBS;
- update Stage 4 organization cost centers;
- reconcile new allocation against prior total economic cost.

---

## Example — existing infrastructure becomes unavailable

Suppose:

```text
Existing identity matching capability = available
```

changes to:

```text
Existing identity matching capability = unavailable
```

This is structural.

Default response:

- reopen technical Stage 1 scope;
- research new linkage/MPI evidence;
- add design/build/test/operate WBS;
- likely trigger Human Gate 2;
- structurally update Stage 4.

---

# 9. Targeted rerun wrapper

Use this language:

```text
RUN TYPE: TARGETED RERUN

Reconsider only the canonical objects and downstream relationships identified below.
Preserve all unaffected approved state and stable IDs.
Do not broadly reinterpret the project.

Changed objects: [IDs]
Reason: [change]
Potentially invalidated objects: [IDs]
Required outputs to update: [registers/deliverables]
Do not change: [approved unaffected IDs/state]
```

This should prevent the model from unnecessarily reopening settled decisions.

---

# 10. Human gates

## Human Gate 1

Mandatory.

Occurs after Stage 1.

Use it to approve material decisions such as:

- pilot objective;
- organization structure;
- reporting cost centers;
- primary workflow;
- architecture;
- scale;
- live-operation duration;
- major exclusions;
- structural scenarios.

Do not use Gate 1 to review every minor parameter.

---

## Human Gate 2

Conditional.

Occurs after Stage 3 only if an unresolved issue could materially change:

- cost centers;
- operating model;
- structural scenarios;
- major scope;
- infrastructure;
- primary evidence;
- base cost;
- sponsor/participant funding;
- workbook structure.

If uncertainty can be safely parameterized, Gate 2 is not required.

---

# 11. CCC evidence reuse

Stage 2 always begins with the existing CCC benchmark evidence.

Each material evidence item is classified:

| Disposition | Treatment |
|---|---|
| APPLY | Reuse as current/applicable |
| UPDATE | Refresh value |
| ADAPT | Reuse after documented adjustment |
| CORROBORATE | Secondary support only |
| EXCLUDE | Prohibit model use |
| REPLACE | Find better evidence |
| NEW | Research new use-case need |

This is performed at the evidence/parameter level, not merely the document level.

---

# 12. Source and Evidence IDs

Every model-driving source receives:

```text
SRC-###
```

Every usable datum receives:

```text
EVD-###
```

Example:

```text
SRC-014
Federal HIE modernization award

EVD-027
Interface configuration: 40–80 hours per reporting interface
```

The model should not merely say:

> Source: Federal HIE modernization award

Instead it should be possible to identify exactly what datum was used.

---

# 13. Traceability chain

The expected audit chain is:

```text
Pilot requirement
  ↓
SCP-###
  ↓
WBS-HDU-07.02.01
  ↓
PAR-###
  ↓
EVD-###
  ↓
SRC-###
  ↓
Workbook row/cell
  ↓
Organization/workstream total
  ↓
Executive total
```

For judgment-based values:

```text
PAR-###
  ↓
ASM-###
```

For user-approved values:

```text
PAR-###
  ↓
DEC-###
```

---

# 14. Workbook rules

The CCC workbook is the baseline.

Always:

- preserve an untouched original;
- make a working copy;
- inventory the workbook first;
- document every material delta;
- preserve unaffected formulas;
- preserve applicable formatting;
- remove chronic-specific content;
- add use-case-specific content;
- test all formulas.

Do not rebuild the workbook from scratch unless the baseline itself is unusable and that exception is explicitly approved.

---

# 15. Model Delta Plan

Before modifying Excel, create:

| Delta ID | Template Element | Action | Governing State | Reason |
|---|---|---|---|---|

Allowed actions:

- PRESERVE
- UPDATE
- ADD
- REMOVE
- REPLACE

Example:

```text
MDL-011
Template: HCCN cost center
Action: REMOVE
Reason: No HCCN in approved use-case organization register
Governing state: ORG-007
```

---

# 16. Existing infrastructure rule

The workflow estimates the **incremental pilot requirement**.

Do not automatically price:

- replacement value of existing HIE/HDU;
- existing cloud platform;
- existing IAM;
- existing MPI;
- existing audit infrastructure;
- existing production interfaces;
- sunk software development.

Price:

- pilot-specific configuration;
- incremental capacity;
- new interfaces;
- new transformation logic;
- incremental support;
- new licensing;
- genuinely net-new capability.

If contributed infrastructure needs to be reflected economically, show it separately rather than automatically as sponsor-funded cost.

---

# 17. In-kind cost

Participant labor may be economically material even if not reimbursed.

Examples:

- leadership;
- legal/privacy;
- security;
- clinical SMEs;
- public-health SMEs;
- data validation;
- testing;
- workflow redesign;
- governance;
- training;
- evaluation.

Show separately:

- sponsor-funded cost;
- participant-funded cost;
- in-kind cost;
- total economic cost.

---

# 18. Shared costs

Shared costs should normally retain a natural cost-bearing view.

If an allocated participant view is useful, allocation must reconcile:

```text
sum of allocations = original shared cost
```

Allocation must not increase the project total.

---

# 19. Optional components

Use optional add-ons only for genuinely separable scope.

Examples may include:

- a separately selectable data interface;
- a distinct downstream workflow;
- a formal security authorization not required in base;
- a separable specialized analytic capability.

Do not create add-ons for ordinary variation such as:

- participant count;
- interface count;
- remediation cycles;
- support duration;
- routine complexity.

Those belong in parameters or scenarios.

---

# 20. Low / Base / High

Low/base/high should vary underlying assumptions.

Examples:

- participant count;
- source count;
- complexity;
- labor effort;
- rate;
- duration;
- vendor cost;
- evaluation intensity.

Do not create:

```text
High = Base × arbitrary uplift
```

unless the uplift itself has a defensible basis.

---

# 21. Validation

The workflow contains two different forms of assurance.

## Deterministic validation

Checks:

- formulas;
- IDs;
- references;
- source links;
- dollar years;
- scenario logic;
- summary reconciliation;
- double counting;
- workbook integrity.

Results:

- PASS
- REVIEW
- ERROR

Unresolved ERROR blocks progression.

---

## Independent review

Challenges whether:

- the scope is complete;
- the evidence is comparable;
- the WBS is realistic;
- the hours are plausible;
- the model is biased;
- the scenarios are credible;
- the estimate is decision-useful.

A formula can pass validation and still be conceptually wrong.

---

# 22. State freshness

Registers and deliverables should be treated as:

- Current
- Potentially stale
- Stale
- Superseded

Example:

If a new vendor quote replaces a placeholder:

```text
Evidence Register: Current
Parameter Register: Current
WBS: Current if method unchanged
Workbook: Stale until recalculated
Benchmark report: Potentially stale
```

Do not present stale artifacts as current.

---

# 23. Recommended naming conventions

## Use-case files

```text
[Use Case] - Stage 1 State.md
Cost Model Benchmarks for the [Use Case] Pilot.docx
[Use Case] - Stage 3 WBS State.md
[Use Case] Cost Model Pro Forma.xlsx
[Use Case] - Independent Review.md
```

## Versioned output

```text
[Use Case] Cost Model Pro Forma v1.xlsx
[Use Case] Cost Model Pro Forma v2.xlsx
```

Use the project state/change log to explain why a new version exists.

---

# 24. Future automated implementation

A future software implementation should preserve the same logical architecture.

Recommended pattern:

```text
Orchestrator
   |
   +-- Scope Agent
   |
   +-- Benchmark Agent
   |
   +-- WBS Agent
   |
   +-- Model Agent
   |
   +-- Independent Review Agent
```

The agents should not negotiate authoritative state peer-to-peer.

The orchestrator owns:

- state;
- routing;
- invalidation;
- gates;
- versioning.

---

# 25. Recommended machine-readable state

The Markdown schemas can later map directly to typed objects.

Example:

```json
{
  "parameter_id": "PAR-014",
  "name": "provider_count",
  "unit": "organizations",
  "low": 4,
  "base": 6,
  "high": 10,
  "value_classification": "approved decision",
  "decision_ids": ["DEC-006"],
  "status": "active"
}
```

Example evidence object:

```json
{
  "evidence_id": "EVD-027",
  "source_id": "SRC-014",
  "description": "interface configuration effort",
  "value": [40, 80],
  "unit": "hours/interface",
  "confidence": "moderate",
  "disposition": "ADAPT"
}
```

Example WBS object:

```json
{
  "wbs_id": "WBS-HDU-07.02.01",
  "organization_id": "ORG-002",
  "activity": "Configure source interface",
  "scaling_unit": "interface",
  "quantity_parameter_id": "PAR-021",
  "primary_evidence_ids": ["EVD-027"],
  "estimating_method": "bottom-up parametric"
}
```

---

# 26. Recommended automation technology

The workflow does not require a specific orchestration framework.

A future implementation could use:

- OpenAI API/Agents tooling;
- Python state machine;
- durable workflow engine;
- relational database;
- object store;
- job queue;
- structured-output schemas.

The technology choice should not alter:

- stage boundaries;
- human gates;
- canonical schemas;
- evidence traceability;
- selective-rerun rules;
- workbook-delta methodology.

---

# 27. Suggested minimum viable automated version

Do not begin by automating every analytical detail.

A practical MVP would automate:

1. project-state initialization;
2. schema validation;
3. stage routing;
4. human-gate state;
5. Source/Evidence ID assignment;
6. dependency tracking;
7. change logging;
8. selective-rerun routing;
9. Stage 4 workbook inventory;
10. Model Delta Plan;
11. deterministic spreadsheet validation.

Keep analytical judgment agentic for:

- scope interpretation;
- evidence applicability;
- analogue selection;
- WBS decomposition;
- estimating method;
- independent review.

---

# 28. What not to automate first

Avoid early automation of:

- automatic acceptance of benchmark comparability;
- automatic labor-hour generation;
- automatic complexity multipliers;
- automatic contingency percentages;
- automatic optional-component classification;
- automatic approval of stage gates.

These remain judgment-heavy.

---

# 29. First-use checklist

Before running the workflow on a new pilot, confirm:

- [ ] Use-case proposal available
- [ ] Supporting technical materials available
- [ ] Workflow specification available
- [ ] Orchestrator prompt available
- [ ] Stage 1 prompt available
- [ ] Stage 2 prompt available
- [ ] Stage 3 prompt available
- [ ] Stage 4 prompt available
- [ ] Independent review prompt available
- [ ] Canonical schemas available
- [ ] CCC benchmark report available
- [ ] CCC workbook available
- [ ] Original CCC workbook preserved
- [ ] New Project ID assigned
- [ ] Project Register initialized
- [ ] Human Gate 1 status = Pending

---

# 30. Stage completion checklist

## Stage 1

- [ ] Scope complete
- [ ] Organizations complete
- [ ] Cost centers identified
- [ ] Technical flows represented
- [ ] Cost drivers identified
- [ ] Parameters created
- [ ] Risks/exclusions explicit
- [ ] Human Gate 1 package ready
- [ ] No unresolved ERROR

## Stage 2

- [ ] CCC baseline screened
- [ ] Evidence dispositions assigned
- [ ] Required delta research complete
- [ ] Source IDs assigned
- [ ] Evidence IDs assigned
- [ ] Parameters supported
- [ ] Benchmark report complete
- [ ] Evidence gaps explicit
- [ ] No unresolved ERROR

## Stage 3

- [ ] Organization WBS complete
- [ ] Cost-bearing roles explicit
- [ ] Scaling units defined
- [ ] Estimating methods defined
- [ ] Exact Evidence IDs mapped
- [ ] Labor/non-labor inputs defined
- [ ] Shared/in-kind treatments defined
- [ ] Double-counting boundaries defined
- [ ] Stage 4 inputs complete
- [ ] Human Gate 2 resolved/not triggered
- [ ] No unresolved ERROR

## Stage 4

- [ ] CCC workbook inventoried
- [ ] Model Delta Plan complete
- [ ] Workbook transformed
- [ ] Excluded CCC content removed
- [ ] New-use-case content added
- [ ] Formulas validated
- [ ] Source traceability validated
- [ ] Summary reconciliation complete
- [ ] Scenario logic validated
- [ ] In-kind/shared cost treatment correct
- [ ] No unresolved ERROR
- [ ] Workbook ready for independent review

## Review

- [ ] Critical findings resolved
- [ ] High findings resolved/accepted
- [ ] Final benchmark report current
- [ ] Final workbook current
- [ ] Change log current
- [ ] Final state version recorded

---

# 31. Recommended first production test

Before treating the workflow as production-ready, run it end-to-end on one additional PHIG B4 use case.

Use the test to assess:

- whether Stage 1 creates too many or too few gate decisions;
- whether Stage 2 baseline screening reduces research burden;
- whether Source/Evidence IDs are manageable;
- whether Stage 3 is sufficiently detailed for Stage 4;
- whether the CCC workbook can absorb new use-case structures cleanly;
- whether selective reruns work in practice;
- whether the independent review identifies materially different issues from deterministic validation.

Then refine the prompts/schemas based on observed failure modes rather than adding complexity preemptively.

---

# 32. Recommended operating posture

Treat this workflow as a **cost-estimating control system**, not simply a sequence of prompts.

The desired properties are:

- repeatability;
- traceability;
- comparability;
- controlled change;
- explicit uncertainty;
- human accountability;
- reproducible workbook logic;
- evidence discipline.

The goal is not for every pilot cost model to look identical.

The goal is for every pilot cost model to be produced through the same disciplined chain:

```text
Scope
→ Evidence
→ Work
→ Parameters
→ Cost
→ Validation
→ Decision
```

That common chain is what makes the resulting models comparable, reviewable, and maintainable across PHIG B4 use cases.
