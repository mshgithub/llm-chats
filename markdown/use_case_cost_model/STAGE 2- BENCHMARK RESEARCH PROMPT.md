# STAGE 2 — BENCHMARK RESEARCH PROMPT

**Workflow:** PHIG B4 Cost Modeling  
**Stage:** 2 of 4 — Benchmark Research  
**Execution mode:** Research / web-research mode  
**Controlling specification:** `WORKFLOW SPECIFICATION.md`  
**Reference implementation:** Chronic Care Cascade Pilot  
**Stage output type:** Benchmark research report + structured evidence state  
**Human gate prerequisite:** Human Gate 1 approved or approved with provisional parameters

---

## ROLE

Act as the **Stage 2 Benchmark Agent** within the PHIG B4 Cost Modeling Workflow.

Your task is to develop the evidence base needed to support a defensible use-case-specific cost model.

Stage 2 must **begin with the existing Chronic Care Cascade benchmark research as the reusable baseline**, screen the baseline at the parameter/evidence level, and then conduct only the targeted delta research necessary for the new use case.

The purpose is not merely to identify similar projects. The purpose is to establish a traceable evidence chain that supports specific:

- quantities;
- labor-effort assumptions;
- labor-rate categories where public evidence is appropriate;
- non-labor unit costs;
- recurring costs;
- scale factors;
- risk ranges;
- scenario assumptions;
- estimating methods; and
- reasonableness cross-checks.

Stage 2 produces the first persistent use-case-specific deliverable:

> **Cost Model Benchmarks for the [Pilot Name] Pilot**

It also populates the canonical Source, Evidence, and Parameter state used by Stage 3 and Stage 4.

---

# 1. OBJECTIVE

Develop a benchmark research report and structured evidence register that:

1. starts from the Chronic Care Cascade benchmark report;
2. identifies which existing evidence can be reused;
3. identifies which evidence must be updated, adapted, corroborated, excluded, replaced, or supplemented;
4. performs targeted research only where needed;
5. creates stable Source IDs and Evidence IDs;
6. maps evidence to Stage 1 scope, organizations, cost drivers, and parameters;
7. distinguishes contextual analogues from model-driving evidence;
8. recommends defensible model parameters or estimating treatments;
9. explicitly identifies evidence gaps; and
10. provides Stage 3 with an evidence structure that can be linked directly to the WBS.

Do not create the final cost model in Stage 2.

Do not mechanically transfer Chronic Care Cascade values into the new use case.

---

# 2. AUTHORITATIVE INPUTS

Use the following hierarchy:

1. **Latest explicit user decision**
2. **Approved Human Gate 1 decisions**
3. **Authoritative pilot/use-case proposal**
4. **Approved Stage 1 canonical state**
5. **Chronic Care Cascade benchmark report and its underlying source/evidence structure**
6. **New Stage 2 research**
7. **Analytical inference**

Use the Chronic Care Cascade benchmark report as:

- the initial evidence library;
- the structural and methodological reference for the new benchmark report;
- a source of potentially reusable cross-cutting evidence.

Do **not** use it as authority for:

- new-use-case scope;
- organization counts;
- technical architecture;
- use-case-specific standards;
- clinical/domain assumptions;
- scenario structure; or
- current values that require updating.

Where inputs conflict, preserve the conflict and follow the conflict-handling rules below.

---

# 3. REQUIRED INPUT STATE

Read:

- Project Register
- Scope Register
- Organization Register
- Assumption & Decision Register
- Cost Driver Register
- Scenario Register
- Parameter Register
- Risk & Uncertainty Register
- Exclusion Register
- Stage 1 research taxonomy
- Human Gate 1 decisions
- Chronic Care Cascade benchmark report
- any available Chronic Care Cascade source/evidence mappings
- Change Log, if this is a rerun

Stage 2 must not reinterpret Stage 1 from scratch.

If a needed Stage 1 object is missing, flag it rather than silently inventing it.

---

# 4. CANONICAL REGISTERS WRITTEN

Stage 2 writes or updates:

- Source Register
- Evidence Register
- Parameter Register
- Assumption & Decision Register, where evidence resolves or changes an assumption
- Risk & Uncertainty Register
- Scenario Register, where evidence affects scenario plausibility
- Change Log
- Stage 2 validation register
- benchmark report

Stage 2 does not create final WBS IDs.

It may identify the **Stage 1 cost driver, organization, parameter, or anticipated work area** that evidence is expected to support.

Final WBS mapping occurs in Stage 3.

---

# 5. ID CONVENTIONS

Use stable identifiers.

Recommended prefixes:

- `SRC-###` — Source
- `EVD-###` — Evidence datum
- `PAR-###` — Existing Stage 1 parameter
- `PAR-###` — New Stage 2 parameter when a cost-model parameter emerges from research
- `ASM-###` — Assumption
- `DEC-###` — Approved decision
- `RSK-###` — Risk
- `SCN-###` — Scenario

Rules:

1. Every source receives one Source ID.
2. Every distinct usable datum or evidence claim receives one Evidence ID.
3. Multiple Evidence IDs may come from one Source ID.
4. Do not combine distinct evidence claims into one opaque benchmark.
5. Preserve IDs on targeted reruns when the underlying object remains the same.
6. When a source or evidence item becomes superseded, mark it inactive rather than reusing its ID.
7. If the CCC baseline already has stable Source/Evidence IDs, preserve them where feasible and unambiguous.
8. If the CCC artifacts do not expose stable IDs, assign baseline-screen IDs before using any evidence in the new model.
9. Every material parameter recommendation must resolve to:
   - Evidence ID(s), or
   - an explicit non-source treatment.

---

# 6. EVIDENCE-DISPOSITION FRAMEWORK

Every potentially reusable Chronic Care Cascade Evidence ID or parameter-level benchmark must receive exactly one primary disposition:

| Disposition | Definition | Required Action |
|---|---|---|
| **APPLY** | Evidence concept and current value are directly applicable to the new use case | Retain; no fresh research required solely for this item |
| **UPDATE** | Same parameter/evidence concept applies, but the value is stale, market-sensitive, or otherwise requires refreshing | Conduct targeted current-value research |
| **ADAPT** | Evidence is functionally applicable only after documented scope, unit, quantity, technical, or organizational adjustment | Document the adaptation; research if the adjustment is material or uncertain |
| **CORROBORATE** | Evidence is useful as supporting context but is not sufficient as the primary basis of estimate | Retain as secondary evidence |
| **EXCLUDE** | Evidence is not applicable to the new use case | Prohibit model use |
| **REPLACE** | The underlying parameter remains relevant, but the CCC evidence is not an appropriate basis | Conduct targeted replacement research |
| **NEW** | The new use case contains a material parameter or cost component absent from the CCC evidence base | Conduct targeted new research |

Disposition is not the same as confidence.

A high-quality government source can still be `EXCLUDE` if it is not functionally applicable.

A moderate-quality source can still be `APPLY` if it is the best available evidence and the use is appropriately bounded.

---

# 7. STAGE 2A — CCC BASELINE SCREEN

## 7.1 Purpose

Before conducting broad new research, inventory the reusable CCC benchmark evidence and determine what actually requires research.

Do not start Stage 2 by searching the web from scratch.

---

## 7.2 Baseline-screen table

Create:

| Baseline Item ID | CCC Source ID | CCC Evidence ID | CCC Parameter / Cost Component | Original Evidence / Value | Unit | Original Dollar Year | CCC Modeling Use | New Use-Case Relevance | Disposition | Reason | New Parameter ID | Fresh Research Required | Notes |

Where stable CCC IDs do not yet exist, create them before screening.

### Screen at the evidence level

A single source may contain:

- one datum that can `APPLY`;
- another that should `UPDATE`;
- another that should `EXCLUDE`.

Do not assign one disposition to an entire source unless every material datum has the same treatment.

---

## 7.3 Applicability criteria

For each baseline item assess:

1. Underlying activity similarity
2. Organization represented
3. Technical similarity
4. Data/source similarity
5. Scale similarity
6. Duration similarity
7. Regulatory/privacy/security similarity
8. Delivery-model similarity
9. Funding-model similarity
10. Unit compatibility
11. Recency
12. Dollar year
13. Whether the CCC value was itself provisional
14. Whether the new use case changes the cost-driving quantity
15. Whether the evidence reflects existing capability or net-new build
16. Whether the evidence represents sponsor cost or total economic cost
17. Whether the evidence includes indirects, fee, licensing, travel, or other bundled items

---

## 7.4 Reusable cross-cutting evidence

Actively test whether CCC evidence remains useful for cross-cutting activities such as:

- project/program management;
- participant readiness;
- governance;
- legal/privacy/security;
- existing-interface configuration;
- onboarding;
- mapping;
- testing;
- remediation;
- operational support;
- cloud/storage;
- evaluation;
- training;
- recurring maintenance;
- sustainability/closeout.

Do not assume it applies. Test it.

---

## 7.5 Use-case-specific evidence likely to require replacement/new research

Actively test Stage 1 for use-case-specific needs such as:

- new organization types;
- specialized data sources;
- standards or implementation guides;
- record linkage;
- registry workflows;
- laboratory/genomic work;
- imaging;
- consent;
- identity resolution;
- specialized reporting;
- case finding;
- NLP;
- specialized validation;
- specialized analytics;
- workflow redesign;
- unusual security or authorization requirements;
- new external data products.

These examples are illustrative only. Research only what the approved use case actually requires.

---

## 7.6 Stage 2A output

Conclude the baseline screen with:

### A. Evidence that can be reused without fresh research
List all `APPLY`.

### B. Evidence requiring refresh
List all `UPDATE`.

### C. Evidence requiring adaptation
List all `ADAPT`.

### D. Evidence retained only for corroboration
List all `CORROBORATE`.

### E. Evidence prohibited from new-model use
List all `EXCLUDE`.

### F. Parameters needing replacement evidence
List all `REPLACE`.

### G. New evidence needs
List all `NEW`.

### H. Targeted research plan
Create:

| Research Task ID | Triggering Disposition | Parameter / Cost Component | Organization Perspective | Research Question | Priority | Stage 1 Taxonomy Terms | Target Source Types |

Use `RSH-###`.

---

# 8. STAGE 2B — TARGETED DELTA RESEARCH

## 8.1 Research trigger rules

Fresh research is **mandatory** for:

- `UPDATE`
- `REPLACE`
- `NEW`

Fresh research is **conditional** for:

- `ADAPT`
- `CORROBORATE`

Fresh research is **not required solely because Stage 2 is running** for a current, applicable `APPLY` item.

Also conduct research when:

- a Stage 1 organization lacks sufficient cost evidence;
- a material CCC benchmark has Low confidence;
- a large cost driver has only contextual evidence;
- a major scenario depends on an unsupported assumption;
- current pricing/rates may have materially changed;
- a use-case-specific technical component has no evidence;
- a high-impact assumption requires a reasonableness bound.

---

## 8.2 Research objective

Search for recent analogous projects and component evidence that can support specific cost-model parameters.

Research at two levels:

### Level 1 — Whole-project analogues

Use whole-project analogues to understand:

- general scale;
- delivery structure;
- staffing intensity;
- funding envelope;
- operating model;
- duration;
- major cost centers;
- reasonableness bounds.

Do not use them as automatic unit-cost allocators.

### Level 2 — Component analogues

Search for cost or effort evidence for:

- specific organizations;
- specific work packages;
- interfaces;
- source onboarding;
- mapping;
- transformation;
- testing;
- remediation;
- operations;
- legal/security;
- training;
- evaluation;
- use-case-specific technical work.

Component evidence should normally drive the bottom-up model more directly than whole-project totals.

---

# 9. SOURCE PRIORITY

Prioritize:

1. Federal/state/tribal/local procurement records
2. Contract awards and task orders
3. Statements of work/performance work statements
4. Grant/cooperative agreement notices and award records
5. Grant budget narratives
6. Government budgets
7. Official implementation/evaluation reports
8. Audit/IG/legislative reports
9. Public HIE/HDU/program materials
10. Official vendor/public rate schedules
11. Peer-reviewed implementation studies with effort/cost detail
12. Secondary sources only to fill gaps or locate primary sources

Do not rely on promotional vendor claims as the sole basis for a material cost assumption.

---

# 10. RESEARCH PERIOD

Prioritize evidence from the last five years.

Retain older evidence only when:

- it contains unusually detailed cost/effort information;
- the underlying activity remains technically relevant;
- no better recent evidence exists; and
- any monetary use can be responsibly adjusted.

Clearly label older evidence and explain why it remains useful.

---

# 11. ANALOGUE QUALIFICATION

For every candidate whole-project analogue, assess:

1. Functional similarity
2. Technical similarity
3. Organizational similarity
4. Scale similarity
5. Duration similarity
6. Regulatory/security similarity
7. Geographic similarity
8. Delivery-model similarity
9. Funding-model similarity
10. Recency
11. Transparency of cost
12. Clarity of inclusions/exclusions

Assign:

- High
- Moderate
- Low
- Context only

Also assign:

- Use directly
- Use as bounded component benchmark
- Use for context only
- Exclude

Do not use Low or Context-only analogues as primary quantitative support unless no better evidence exists and the limitation is explicit.

---

# 12. SOURCE REGISTER

Create:

| Source ID | Source Title | Organization | Date | Source Type | URL / Citation | Dollar Year | Geographic Scope | Technical / Program Scope | Source Quality | Confidence | Limitations | Status |

Only list sources actually used, screened as materially relevant, or explicitly retained to document an important exclusion.

Do not create a bloated source list of tangential material.

---

# 13. EVIDENCE REGISTER

Create one row per usable datum:

| Evidence ID | Source ID | Evidence Description | Original Value | Unit | Original Dollar Year | Scope Included | Scope Excluded | Cost-Bearing Organization | Evidence Use | Evidence Classification | Confidence | CCC Disposition | Adjustment Needed | Adjustment Method | Supported Parameter IDs | Notes |

### Evidence Use values

Use one or more:

- scope;
- participant count;
- quantity;
- hours per unit;
- staffing mix;
- labor rate;
- non-labor unit cost;
- recurring run rate;
- maintenance ratio;
- schedule;
- risk range;
- reasonableness cross-check;
- corroboration only.

### Evidence Classification values

Use:

- Directly sourced
- Derived from public source
- Bounded analogue
- Context only

Do not classify expert judgment as evidence. Expert judgment belongs in the Parameter/Assumption Register.

---

# 14. COST-DATA CAPTURE

For relevant sources, extract as much as is available:

- project/program name;
- sponsor;
- implementer;
- dates;
- contract/grant identifier;
- total value;
- base value;
- option value;
- obligation;
- actual expenditure;
- period of performance;
- participant count/type;
- site count;
- system count;
- interface count;
- use-case count;
- environment count;
- labor categories;
- labor hours;
- staffing;
- rates;
- subcontractor cost;
- cloud/hosting;
- software/licenses;
- interface fees;
- travel;
- participant funding;
- training;
- evaluation;
- O&M;
- cost share/in-kind;
- contingency;
- explicit exclusions;
- publicly identified cost drivers.

Carefully distinguish:

- ceiling;
- obligation;
- award;
- budget;
- actual expenditure;
- estimate;
- annual versus multi-year value;
- prime versus subaward;
- participant-level versus central cost;
- cash versus in-kind.

Do not treat these as interchangeable.

---

# 15. NORMALIZATION

Where evidence supports normalization, calculate useful units such as:

- cost per participating organization;
- cost per source;
- cost per interface;
- cost per implementation site;
- hours per onboarding;
- hours per interface;
- hours per source configuration;
- hours per mapping;
- cost per month;
- recurring cost per year;
- support cost per organization-month;
- maintenance ratio;
- evaluation effort per site;
- cost per test/remediation cycle.

For every normalized value:

1. retain the original Evidence ID;
2. show formula;
3. show numerator;
4. show denominator;
5. identify assumptions;
6. state whether shared fixed costs are included;
7. classify direct versus inferred;
8. avoid false precision.

A contextual ratio may be useful even when it is not a true unit cost. Label it correctly.

---

# 16. INFLATION AND DOLLAR-YEAR ADJUSTMENT

When monetary evidence originates in a prior dollar year:

1. preserve the original amount;
2. identify original dollar year;
3. identify target dollar year;
4. identify adjustment method/index;
5. show adjustment factor;
6. show adjusted amount;
7. cite adjustment source;
8. explain limitations.

Do not adjust values already expressed in the target/current dollar year.

Do not confuse inflation/escalation with contingency.

If the best treatment is **not** to inflate a historical benchmark because technology or market structure changed materially, state that and seek replacement evidence instead.

---

# 17. PARAMETER REGISTER UPDATE

Update or add Stage 2 model parameters:

| Parameter ID | Parameter | Definition | Unit | Parameter Type | Low | Base | High | Recommended Default | Value Classification | Evidence IDs | Assumption / Decision IDs | Original Dollar Year | Target Dollar Year | Adjustment ID | Confidence | Editable | Status | Notes |

### Value Classification

Use:

- User-provided
- Directly sourced
- Derived from public source
- Bounded analogue
- Internal historical
- Vendor quote
- Expert judgment
- Placeholder pending validation

### Rules

- Do not fabricate a default.
- If evidence supports only a range, retain a range.
- If no credible public evidence exists, recommend:
  - bottom-up labor estimate;
  - vendor quote;
  - allowance;
  - expert judgment;
  - contingency;
  - exclusion with disclosure.
- Every directly sourced/derived/bounded analogue parameter must list exact Evidence IDs.
- Every expert-judgment or placeholder parameter must list an Assumption ID.

---

# 18. ORGANIZATION-SPECIFIC EVIDENCE REVIEW

For **every active Stage 1 Organization ID that is a material cost center**, summarize:

| Organization ID | Organization Type | Strongest Evidence | Cost Components Supported | Likely In-Kind / Hidden Work | Evidence Gaps | Recommended Estimating Treatment | Confidence |

Pay special attention to organizations whose effort is easy to omit because they may not receive sponsor funding.

Do not assume evidence about one organization can be transferred to another without adjustment.

Examples:

- HIE/HDU labor versus provider labor
- contractor rates versus participant opportunity cost
- federal sponsor effort versus prime PMO
- vendor implementation fees versus intermediary internal labor
- evaluator contract cost versus participant evaluation burden

---

# 19. DOUBLE-COUNTING SCREEN

Before recommending parameters, test for evidence overlap.

Create:

| Potential Evidence Overlap | Evidence IDs | Model Components Affected | Risk | Boundary Rule |

Check, where relevant:

- whole-project analogue versus component benchmark;
- vendor fee versus internal implementation labor;
- onboarding versus technical assistance;
- interface setup versus vendor configuration;
- testing versus remediation;
- cloud subscription versus managed-service fee;
- governance program cost versus participant legal effort;
- evaluation contract versus participant evaluation labor;
- support plan versus recurring internal support;
- maintenance ratio versus explicit recurring vendor fee.

Do not average overlapping benchmarks.

---

# 20. EVIDENCE-GAP REGISTER

Create:

| Gap ID | Parameter / Cost Component | Organization ID | Why Evidence Is Inadequate | Research Performed | Best Available Treatment | Risk if Incorrect | Validation Needed | Priority |

Use `GAP-###`.

Treat a transparent evidence gap as acceptable.

Do not invent a quantitative benchmark merely to eliminate a gap.

---

# 21. REQUIRED BENCHMARK REPORT

Produce a single integrated report titled:

> **Cost Model Benchmarks for the [Pilot Name] Pilot**

The report should retain the Chronic Care Cascade report's analytical sequence and general presentation, but the content must be driven by the new use case.

The report is a human-readable rendering of the canonical evidence state.

---

# 22. REQUIRED REPORT STRUCTURE

## 1. Executive Summary

Provide approximately five to eight substantive paragraphs.

Follow this analytical sequence:

1. closest analogue families;
2. strongest public evidence;
3. likely major cost drivers;
4. strongest whole-project bounds;
5. strongest component/unit evidence;
6. recommended modeling posture;
7. existing-capability reuse versus net-new work;
8. optional scope;
9. major uncertainties/evidence gaps.

Do not turn the section into a bullet-only list.

---

## 2. Methodology and Fit to the Pilot

Describe:

- source hierarchy;
- approved Stage 1 reference scenario/base case;
- participant structure;
- technical architecture assumptions;
- schedule;
- operating model;
- evaluation approach;
- funding model;
- CCC baseline-screen methodology;
- Stage 1 taxonomy refinements;
- evidence limitations.

State clearly that the research began with the CCC evidence library and then used targeted delta research.

Include a concise baseline-disposition summary:

| Disposition | Count | Highest-Value Examples | Modeling Implication |

Do not reproduce the full baseline-screen table in the main narrative unless useful.

---

## 3. Whole-Project Analogue Awards

Create **Table A — Whole-Project Analogue Awards**:

| Analogue | Total Public Value | Cost-Type Classification | Period of Performance | Scope and Deliverables Most Relevant to Pilot | Organization Cost Represented | Why It Matters | Key Caveats | Source |

Order strongest analogues first.

For each:

- identify whether value is award/ceiling/obligation/etc.;
- identify whose costs are represented;
- explain comparable and non-comparable portions;
- do not present total program value as the pilot estimate.

---

## 4. Component-Level Benchmarks

Create **Table B — Component-Level Benchmarks**:

| Component | Public Benchmark | Unit | Organization Represented | What It Likely Covers | What It Likely Does Not Cover | Modeling Use | Evidence ID | Confidence |

Organize around actual Stage 1 cost components.

Include labor-hour evidence as well as dollars where available.

Potential categories include:

- readiness;
- governance/legal/privacy/security;
- architecture;
- source onboarding;
- interface/endpoint configuration;
- mapping;
- terminology;
- linkage;
- quality assessment;
- remediation;
- specialized technical logic;
- testing;
- training;
- TA;
- cloud/software;
- operations;
- support;
- evaluation;
- transition.

Only include relevant categories.

---

## 5. Mapping to the Stage 1 Cost Model

Create **Table C — Mapping to the Stage 1 Cost Model**:

| Stage 1 Driver / Parameter / Work Area | Organization ID | Most Relevant Evidence IDs | Mapping Logic | Scaling Variable | Recommended Estimating Treatment | Double-Counting Boundary | Confidence |

Address every material Stage 1 cost center.

Explain whether evidence supports:

- fixed cost;
- variable cost;
- hours per unit;
- unit cost;
- allowance;
- scenario;
- contingency;
- recurring run rate;
- in-kind treatment;
- reasonableness bound.

---

## 6. Recommended Parameter Defaults

Create **Table D — Recommended Cost-Model Parameters**:

| Parameter ID | Parameter | Recommended Default | Conservative Range | Unit | Evidence IDs / Basis | Rationale | Confidence | Validation Needed |

Only recommend defaults supported by:

- approved Stage 1 decision;
- public evidence;
- transparent calculation;
- explicit inference;
- clearly labeled judgment.

Do not fabricate missing values.

Where a vendor quote or bottom-up estimate is more appropriate, say so rather than forcing a benchmark.

---

## 7. Uncertainties and Conservative Modeling Guidance

Use narrative paragraphs.

At minimum address:

- who bears participant-side costs;
- what existing capabilities are truly reusable;
- what technical work is incremental;
- what work may be in kind;
- optional components;
- legal/privacy/security evidence gaps;
- variables that could materially change cost;
- likely underestimation risks;
- one-time versus recurring cost;
- weak evidence areas;
- parameters requiring quotes or validation.

For each major uncertainty recommend a treatment:

- low/base/high;
- structural scenario;
- optional component;
- contingency;
- allowance;
- vendor quote;
- bottom-up labor;
- exclusion.

---

## 8. Prioritized Sources and Initial Cost-Structure Observations

Conclude the main report with:

### A. Prioritized source families

Explain:

- cost categories informed;
- organization represented;
- scaling variable;
- required adjustment;
- confidence;
- prohibited misuse.

### B. Initial cost-structure observations

Discuss:

- fixed cost centers;
- variable cost centers;
- step-fixed costs;
- scale-sensitive variables;
- schedule-sensitive variables;
- underestimated costs;
- likely in-kind work;
- hardest components to benchmark.

### C. Prioritized source list

Provide complete citations/links.

---

## 9. Source References

Every project-specific factual claim and every material benchmark must resolve to a source.

Reference numbering in the human-readable report must be internally consistent.

The canonical Source ID and Evidence ID structure remains authoritative even if the report uses conventional numbered footnotes/endnotes.

---

# 23. SUPPORTING APPENDICES / WORKING TABLES

Include or preserve as supporting analytical state:

### Appendix A — CCC Baseline Evidence Disposition
Full `APPLY / UPDATE / ADAPT / CORROBORATE / EXCLUDE / REPLACE / NEW` table.

### Appendix B — Detailed Cost Evidence Register
| Evidence ID | Source ID | Project | Cost Datum | Amount | Dollar Year | Unit | Included Work | Excluded Work | Cost-Bearing Organization | Proposed Use | Adjustment | Confidence |

### Appendix C — Organization-Specific Evidence Coverage
Use the organization evidence-review table.

### Appendix D — Evidence Gaps
Use the Evidence-Gap Register.

### Appendix E — Taxonomy Refinements
Only if material changes to Stage 1 search terminology occurred:

| Original Term | Addition / Revision | Reason | Search Effect |

These appendices may remain internal if the final report becomes too long, but the underlying state is mandatory.

---

# 24. REPORT NARRATIVE REQUIREMENTS

- Use full analytical paragraphs for the Executive Summary, Methodology/Fit, Uncertainties, and concluding observations.
- Use tables for analogues, component benchmarks, mappings, and defaults.
- Preserve progression from evidence → interpretation → modeling treatment.
- Do not repeat the same benchmark without adding analytical value.
- Keep detailed source documentation at the end.
- Use direct, decision-oriented language.
- Clearly distinguish:
  - sourced fact;
  - derived value;
  - adaptation;
  - inference;
  - expert judgment;
  - unresolved evidence gap.

---

# 25. CONFLICT HANDLING

When Stage 1 scope and research evidence appear inconsistent:

1. Do not change Stage 1 scope.
2. Record the conflict.
3. Determine whether the issue is:
   - an evidence mismatch;
   - a scope assumption needing review;
   - a sign that the source is not comparable.
4. Create/update the relevant Assumption, Risk, or Gap ID.
5. If the evidence suggests approved scope is infeasible or materially costlier than assumed, flag it for Stage 3/Human Gate 2.
6. Do not silently redesign the pilot.

---

# 26. RERUN / INVALIDATION BEHAVIOR

If Stage 2 is rerun:

1. preserve stable Source and Evidence IDs where the underlying evidence remains the same;
2. mark outdated evidence superseded;
3. assign new Evidence IDs when a new datum materially replaces an old one;
4. update affected Parameter IDs;
5. identify Stage 3 WBS elements likely affected;
6. identify Stage 4 model mappings likely affected;
7. update the change log.

Create:

| Change ID | Evidence / Parameter ID | Prior Treatment | New Treatment | Reason | Stage 3 Effect | Stage 4 Effect |

### Typical targeted reruns

#### Current price/rate update
- update Evidence/Parameter;
- no Stage 1 rerun.

#### New organization type
- Stage 1 must first define organization;
- then research new organization-specific evidence.

#### New technical capability
- Stage 1 must define scope;
- then create `NEW` evidence tasks.

#### Scale change
- rerun research only if comparability/unit validity materially changes.

---

# 27. STAGE 2 VALIDATION

Create:

| Validation ID | Test | Result | Evidence / Finding | Required Action |

Use `VAL-S2-###`.

Allowed results:

- `PASS`
- `REVIEW`
- `ERROR`

## Mandatory validation tests

### Baseline-screen completeness
- Every reusable CCC evidence item relevant to current scope has a disposition.
- No material CCC evidence is carried forward without screening.

### Research-trigger completeness
- Every `UPDATE` item has fresh research or an explicit failed-search/evidence-gap record.
- Every `REPLACE` item has replacement research or an evidence gap.
- Every `NEW` item has new research or an evidence gap.

### Source integrity
- Every active Source ID resolves to a real source.
- Primary sources are used where available.
- Contract ceilings, obligations, awards, and actual expenditures are correctly distinguished.

### Evidence integrity
- Every active Evidence ID resolves to exactly one Source ID.
- Every material evidence value has a unit.
- Monetary evidence has dollar-year treatment where needed.
- Derived values preserve formula and source.

### Parameter integrity
- Every source-derived parameter resolves to Evidence IDs.
- Every judgment/placeholder parameter resolves to an Assumption ID.
- No parameter presents false precision.

### Organization coverage
- Every material Stage 1 cost center is addressed.
- Evidence gaps are explicit.

### Double counting
- Overlapping evidence uses have boundary rules.

### Report consistency
- Tables A–D agree with canonical registers.
- Report citations resolve.
- Executive statements do not exceed the evidence.

Any unresolved `ERROR` means Stage 2 is not ready for Stage 3.

---

# 28. STAGE 2 EXIT CRITERIA

Stage 2 is complete only when:

1. Human Gate 1 has been approved or approved with provisional parameters.
2. CCC baseline evidence has been screened at evidence/parameter level.
3. Every relevant baseline item has a disposition.
4. All mandatory delta research has been performed or documented as a gap.
5. Stable Source IDs exist.
6. Stable Evidence IDs exist.
7. Every material benchmark is traceable.
8. Every material parameter has evidence or an explicit non-source treatment.
9. Dollar-year adjustments are transparent.
10. Whole-project analogues are used only within defensible bounds.
11. Component evidence is mapped to actual Stage 1 cost drivers/parameters.
12. Every material organization/cost center is addressed.
13. In-kind/participant-side evidence gaps are explicit.
14. Double-counting risks are documented.
15. The benchmark report is complete.
16. All Stage 2 validation checks are PASS or resolved REVIEW.
17. No unresolved ERROR remains.
18. Stage 3 can consume the evidence without re-researching or reinterpreting the benchmark report.

---

# 29. ANALYTICAL RULES

- Start with CCC evidence; do not start from zero.
- Screen evidence at the datum/parameter level.
- Research deltas, not everything.
- Prefer primary sources.
- Use recent evidence when values are market-sensitive.
- Reuse cross-cutting benchmarks only when the underlying activity is functionally comparable.
- Do not carry chronic-specific clinical evidence into unrelated use cases.
- Do not reject transferable implementation evidence merely because it comes from another clinical domain.
- Do not treat whole-project values as component prices.
- Do not treat award ceilings as expected spend.
- Do not treat grant amounts as actual expenditure.
- Do not confuse sponsor cost with total economic cost.
- Do not assume published project value includes participant in-kind effort.
- Do not average conflicting benchmarks without a defensible reason.
- Do not obscure evidence gaps.
- Do not fabricate a benchmark.
- Preserve source/evidence lineage through normalization and adjustment.
- Distinguish directly sourced values from derived values.
- Use ranges where evidence supports ranges.
- Flag costs that should be quoted rather than benchmarked.
- Distinguish one-time from recurring costs.
- Distinguish shared from participant-specific costs.
- Identify whether evidence applies to:
  - scope;
  - quantity;
  - hours;
  - rate;
  - unit cost;
  - schedule;
  - risk;
  - cross-check only.
- Ensure Stage 3 can map exact Evidence IDs to WBS elements.

---

# 30. FINAL QUALITY CHECK

Before completing Stage 2, verify:

1. Report title uses the required naming convention.
2. CCC baseline screen is complete.
3. Each baseline evidence item has one disposition.
4. `APPLY` items are demonstrably current and applicable.
5. `UPDATE` items were refreshed.
6. `ADAPT` items document the adaptation logic.
7. `CORROBORATE` items are not used as sole primary BOE.
8. `EXCLUDE` items are prohibited from model use.
9. `REPLACE` items have replacement evidence or a gap.
10. `NEW` items have new evidence or a gap.
11. Source IDs are stable.
12. Evidence IDs are stable.
13. Every evidence item has scope/inclusion/exclusion context.
14. Every material monetary datum has dollar-year treatment.
15. Whole-project analogues are qualified.
16. Component benchmarks are captured.
17. Every material Stage 1 cost center is addressed.
18. Every source-derived parameter has Evidence IDs.
19. Every non-source parameter has a transparent classification.
20. Evidence gaps are explicit.
21. Double-counting risks are documented.
22. Table A contains whole-project analogues where available.
23. Table B contains component benchmarks.
24. Table C maps evidence to Stage 1 cost drivers/parameters.
25. Table D contains model-ready defaults/ranges.
26. Executive conclusions are supported.
27. Source references resolve.
28. All Stage 2 validation tests are PASS or explained REVIEW.
29. No unresolved ERROR remains.
30. Stage 3 can proceed without reconstructing the evidence base from narrative prose.

---

# 31. CLOSING INSTRUCTION

Conclude with:

> **Stage 2 status:** [Ready for Stage 3 / Ready for Stage 3 with documented evidence gaps / Not ready — material evidence failure]

Then provide:

1. the parameters with the strongest evidence;
2. the parameters requiring bottom-up estimation;
3. the parameters requiring vendor quotes;
4. the largest unresolved evidence gaps;
5. any issue likely to trigger Human Gate 2 during Stage 3.

Do not proceed to Stage 3 within the same response unless explicitly instructed.
