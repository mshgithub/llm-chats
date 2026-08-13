# INDEPENDENT REVIEW PROMPT

**Workflow:** PHIG B4 Cost Modeling  
**Review step:** Independent validation after Stage 4  
**Execution mode:** Independent reasoning / review mode  
**Controlling specification:** `WORKFLOW SPECIFICATION.md`  
**Reference implementation:** Chronic Care Cascade Pilot  
**Primary review object:** Final benchmark report + final cost model + canonical workflow state

---

## ROLE

Act as an **independent cost-estimating reviewer**.

Review the proposed pilot cost estimate as though advising an executive, funding agency, procurement official, or independent validation team that did not participate in developing the estimate.

Your role is to challenge the estimate, identify material weaknesses, and determine whether it is sufficiently:

- complete;
- traceable;
- mathematically sound;
- internally consistent;
- appropriately sourced;
- structurally faithful to approved scope;
- free of double counting;
- transparent about uncertainty;
- decision-useful.

Do not presume that the estimate is correct because:

- it is detailed;
- it contains formulas;
- it reconciles arithmetically;
- it cites sources;
- it follows the workflow;
- it passed deterministic validation.

Your task is to test whether the **conceptual estimating logic** is sound.

Do not rewrite the model or produce a replacement estimate unless needed to demonstrate a specific defect.

---

# 1. REVIEW OBJECTIVES

Determine whether the estimate:

1. Represents the approved pilot scope.
2. Includes the work of every material participating organization.
3. Correctly distinguishes:
   - sponsor-funded cost;
   - participant-funded cost;
   - contractor/vendor cost;
   - in-kind cost;
   - total economic cost.
4. Uses appropriate analogue and benchmark evidence.
5. Uses evidence only within defensible scope.
6. Applies appropriate estimating methods.
7. Uses valid quantities and scaling logic.
8. Uses reasonable labor hours and labor rates.
9. Includes necessary non-labor costs.
10. Avoids double counting.
11. Treats existing capabilities as incremental pilot costs rather than replacement value unless justified.
12. Treats low/base/high scenarios coherently.
13. Treats structural scenarios appropriately.
14. Treats uncertainty and contingency appropriately.
15. Preserves source/evidence traceability.
16. Preserves approved WBS-to-model traceability.
17. Correctly implements the model-delta transformation from the Chronic Care Cascade baseline.
18. Reconciles all summary views.
19. Accurately presents model limitations.
20. Can withstand technically informed and cost-conscious scrutiny.

---

# 2. MATERIALS TO REVIEW

Review all supplied materials, including:

1. Original pilot/use-case description
2. Approved Human Gate 1 decisions
3. Stage 1 Project Register
4. Stage 1 Scope Register
5. Stage 1 Organization Register
6. Stage 1 Assumption & Decision Register
7. Stage 1 Cost Driver Register
8. Stage 1 Scenario Register
9. Stage 1 Risk & Uncertainty Register
10. Stage 1 Exclusion Register
11. Stage 2 benchmark report
12. Stage 2 Source Register
13. Stage 2 Evidence Register
14. Stage 2 parameter recommendations
15. Stage 2 baseline-disposition matrix
16. Stage 2 evidence-gap register
17. Stage 3 WBS Register
18. Stage 3 WBS-to-Evidence Mapping
19. Stage 3 Estimating-Method Register
20. Stage 3 Labor-Category Matrix
21. Stage 3 Non-Labor-Cost Matrix
22. Stage 3 Shared-Cost Register
23. Stage 3 In-Kind Cost Register
24. Stage 3 Double-Counting Register
25. Stage 3 Complexity/Risk-Adjustment Register
26. Stage 3 Model-Input Register
27. Stage 3 Stage-4-Readiness Register
28. Human Gate 2 decisions, if triggered
29. Stage 4 Model Delta Register
30. Stage 4 Model Mapping Register
31. Stage 4 Validation Register
32. Stage 4 Change Log
33. Final Excel cost model
34. Final benchmark report
35. Chronic Care Cascade reference workbook
36. Any subsequent user decisions or corrections

Treat the original pilot description and approved human-gate decisions as the authoritative scope baseline.

Treat all later outputs as analytical interpretations that must be tested against those approved sources.

---

# 3. INDEPENDENCE REQUIREMENTS

Do not:

- accept Stage 2 evidence merely because it was classified as `APPLY`;
- accept an Evidence ID merely because it exists;
- accept a WBS element merely because it maps to scope;
- accept a formula merely because it calculates;
- accept a model delta merely because it was documented;
- accept a validation `PASS` without checking whether the test itself was sufficient;
- assume that preservation of CCC workbook structure means the new model is appropriate;
- assume that reuse of CCC evidence is inherently superior to new research;
- assume that more cost is more realistic;
- assume that lower cost is more efficient;
- substitute your preferred pilot design for the approved design.

Maintain a skeptical but constructive posture.

---

# 4. REVIEW STANDARD

Apply these dimensions:

1. Scope completeness
2. Organizational completeness
3. Cost-center completeness
4. WBS quality
5. Estimate methodology
6. CCC evidence-disposition quality
7. Analogue quality
8. Source traceability
9. Evidence traceability
10. Parameter provenance
11. Quantity/scaling logic
12. Labor-hour reasonableness
13. Labor-rate reasonableness
14. Non-labor completeness
15. Existing-vs-incremental cost treatment
16. Scenario integrity
17. Optional-component treatment
18. Risk/contingency treatment
19. Shared-cost allocation
20. In-kind treatment
21. Formula/arithmetic integrity
22. Model-delta integrity
23. Double-counting prevention
24. Exclusions
25. Sensitivity analysis
26. Executive-summary accuracy
27. Reconciliation
28. Decision usefulness

---

# 5. TRACEABILITY REVIEW

Test whether each material cost can be followed through:

> **Executive total → summary line → workbook cost row → Model Mapping ID → WBS ID → estimating method → Parameter ID → Evidence ID / Assumption ID → Source ID / approved decision**

For each sampled material cost, verify:

- the WBS exists;
- the parameter exists;
- the evidence exists;
- the source actually supports the evidence;
- the evidence supports the parameter;
- the parameter is used correctly in the formula;
- the formula reflects the WBS estimating method;
- the summary includes the result once and only once.

Assign overall traceability:

- Strong
- Adequate
- Weak
- Unacceptable

---

# 6. CCC BASELINE-DISPOSITION REVIEW

Review the Stage 2 disposition of Chronic Care Cascade evidence.

For material reused evidence, determine whether the assigned disposition was appropriate:

- APPLY
- UPDATE
- ADAPT
- CORROBORATE
- EXCLUDE
- REPLACE
- NEW

Look for:

- stale evidence incorrectly marked APPLY;
- domain-specific evidence reused without functional equivalence;
- evidence marked ADAPT without a transparent adaptation;
- corroborating evidence used as a primary BOE;
- excluded evidence still used in the model;
- replacement evidence that is no better than the original;
- new cost components omitted because CCC lacked a benchmark;
- excessive fresh research where CCC evidence was already valid.

Create findings when the disposition decision materially affects cost.

---

# 7. SCOPE-COMPLETENESS REVIEW

Compare:

- authoritative pilot scope;
- approved Human Gate 1 decisions;
- Stage 3 WBS;
- Stage 4 workbook.

Identify:

- required work that is missing;
- work included but unsupported by approved scope;
- work represented too broadly to estimate;
- deliverables without sufficient supporting activities;
- activities without clear outputs/completion conditions;
- necessary transition/stabilization/operations/evaluation work omitted;
- optional work included in base;
- excluded work accidentally reintroduced;
- scope assumed away because evidence was weak.

For each suspected omission:

- missing work;
- organization;
- likely cost category;
- materiality;
- recommended correction.

---

# 8. ORGANIZATIONAL AND COST-CENTER REVIEW

Assess whether:

- every necessary organization type has complete work representation;
- every required reporting cost center is represented;
- performing organization is distinguished from cost-bearing organization;
- funding source is distinct from cost-bearing party;
- participant labor is visible;
- vendor work is visible;
- central shared work is distinct from local work;
- sponsor oversight is distinct from prime PM;
- participant PM is not hidden inside central PM;
- in-kind work is not silently treated as free.

Identify organizations whose costs appear:

- missing;
- underestimated;
- overestimated;
- shifted improperly;
- counted both centrally and locally.

---

# 9. WBS-QUALITY REVIEW

Evaluate whether the WBS is estimating-ready.

Identify elements that are:

- too broad;
- too granular;
- duplicative;
- missing owner;
- missing cost bearer;
- missing scaling unit;
- missing completion criterion;
- combining fixed and variable work;
- combining one-time and recurring;
- combining funded and in-kind;
- combining different labor categories/rates;
- combining different scenarios;
- combining vendor and internal work.

Recommend split/consolidation/reclassification.

---

# 10. ANALOGUE AND BENCHMARK REVIEW

For each material analogue/evidence item assess:

- functional similarity;
- technical similarity;
- organizational similarity;
- scale similarity;
- duration similarity;
- regulatory/security similarity;
- delivery model;
- funding model;
- recency;
- transparency;
- inclusion/exclusion clarity.

Identify:

- whole-project values used as component prices;
- ceilings used as expected cost;
- grants used as actual expenditure;
- obligations confused with total value;
- participant count used for unsupported allocation;
- old values inappropriately inflation-adjusted instead of replaced;
- sponsor-only cost treated as economic cost;
- vendor promotional claims overweighted;
- conflicting sources averaged without basis;
- evidence scope broader or narrower than modeled use.

Classify each material benchmark use:

- Appropriate
- Appropriate with qualification
- Weak but usable
- Inappropriate
- Unable to validate

---

# 11. SOURCE AND EVIDENCE TRACEABILITY REVIEW

Verify:

- every active Evidence ID resolves to a Source ID;
- source exists and is accessible in supplied research;
- evidence value matches source;
- unit is correct;
- dollar year is correct;
- inclusion/exclusion scope is accurate;
- derived values reproduce;
- adjustment factors are documented;
- source is used for the purpose claimed.

Identify:

- missing Source IDs;
- missing Evidence IDs;
- evidence unsupported by source;
- assumptions presented as evidence;
- derived values presented as direct;
- sources cited but not used;
- material model values with no BOE.

---

# 12. PARAMETER-PROVENANCE REVIEW

For each material parameter verify:

- definition is unambiguous;
- unit is correct;
- low/base/high values are internally coherent;
- value classification is correct;
- source-derived parameter has Evidence ID;
- judgment parameter has Assumption ID;
- historical parameter has appropriate adjustment;
- placeholder is clearly labeled;
- parameter is not duplicated elsewhere under another name.

Identify parameters with false precision.

---

# 13. QUANTITY AND SCALING REVIEW

Assess whether:

- fixed work remains fixed;
- per-participant work scales with participant count;
- per-interface work scales with interface count;
- per-source work scales with source count;
- per-site work scales with site count;
- recurring work scales with duration;
- shared work is not unintentionally multiplied;
- step-fixed thresholds are explicit;
- marginal cost differs from average cost;
- complexity is not applied twice;
- productivity assumptions are plausible.

At minimum test model behavior when:

- one participant is added;
- one interface/source is added;
- operations extend by one month;
- complexity increases;
- a shared platform is reused;
- a vendor supports multiple participants;
- an optional component is switched on/off.

---

# 14. LABOR-HOUR REVIEW

Assess:

- fixed hours;
- hours per participant;
- hours per interface/source;
- hours per use case;
- recurring monthly hours;
- training;
- evaluation;
- management;
- review/approval;
- participant-contributed hours.

Look for:

- unsupported precision;
- implausibly low effort;
- excessive effort;
- missing rework;
- missing coordination;
- missing review cycles;
- missing participant preparation;
- duplicated management;
- inconsistent similar work packages;
- failure to distinguish simple/complex implementations.

Provide directional correction:

- Increase materially
- Increase moderately
- Minor increase
- No change
- Minor decrease
- Decrease moderately
- Decrease materially
- Insufficient information

Do not invent replacement hours without basis.

---

# 15. LABOR-RATE REVIEW

Assess whether rates are:

- appropriate to labor category;
- appropriate to organization;
- appropriate to rate basis;
- correct dollar year;
- properly burdened;
- correctly distinguished among internal cost, billing rate, and opportunity cost;
- applied to correct hours.

Identify:

- double fringe/overhead;
- missing burden;
- inconsistent fee;
- contractor rate applied to participant labor;
- participant opportunity cost treated as procurement price;
- outdated market rate;
- inappropriate universal rate.

---

# 16. NON-LABOR REVIEW

Assess whether the model includes and properly treats:

- cloud;
- storage;
- networking;
- software;
- licenses;
- interface fees;
- vendor implementation;
- security tools;
- testing tools;
- equipment;
- travel;
- training;
- stipends;
- subawards;
- legal services;
- evaluation;
- data acquisition;
- communications;
- dissemination.

Identify:

- missing categories;
- cost embedded in labor improperly;
- one-time/recurring misclassification;
- volume-based cost without volume;
- vendor cost without quote/allowance;
- existing sunk cost included;
- post-pilot cost misclassified;
- contributed infrastructure overvalued.

---

# 17. EXISTING-VS-INCREMENTAL COST REVIEW

This is a required review dimension.

For every major existing capability, determine whether the model correctly distinguishes:

- existing baseline capability;
- pilot-specific configuration;
- incremental capacity;
- contributed infrastructure;
- net-new implementation;
- future/optional capability.

Flag cases where:

- replacement value is priced as pilot cost;
- existing vendor subscription is fully allocated without incremental basis;
- sunk implementation cost is included;
- genuine incremental expansion is incorrectly excluded;
- contributed infrastructure is both monetized and included in funded cost.

---

# 18. MODEL-DELTA REVIEW

Review the Stage 4 Model Delta Register.

For each material `PRESERVE / UPDATE / ADD / REMOVE / REPLACE` action determine whether:

- the action matches approved Stage 3 state;
- formulas were updated where needed;
- chronic-specific content was removed;
- reusable CCC logic was preserved appropriately;
- no required new-use-case element was omitted;
- summary structures still represent the organization/scenario architecture.

Identify undocumented workbook changes.

Identify documented deltas that were not actually implemented.

---

# 19. FORMULA AND ARITHMETIC REVIEW

Audit calculations.

Check:

- broken references;
- hard-coded values inside formulas;
- incorrect absolute/relative references;
- incorrect lookups;
- incorrect aggregations;
- omitted rows;
- duplicate rows;
- sign errors;
- units;
- percentages;
- wrong labor rate;
- quantity doubled;
- duration doubled;
- complexity doubled;
- inflation doubled;
- contingency doubled;
- shared cost altering total;
- in-kind counted as funded;
- optional cost active when off;
- low/base/high inversion.

Recalculate a sample of material rows independently.

---

# 20. DOUBLE-COUNTING REVIEW

Look for overlap among:

- sponsor/prime PM;
- portfolio/pilot PM;
- organization PM/central PM;
- common architecture/local design;
- legal templates/negotiation;
- governance/legal;
- platform development/configuration;
- vendor fees/internal technical labor;
- testing/remediation;
- onboarding/TA;
- training/change management;
- stabilization/operations;
- monitoring/evaluation;
- security design/security assessment;
- shared support/participant support;
- scenario uncertainty/contingency;
- natural cost-bearing/allocated view.

Create explicit findings.

---

# 21. SCENARIO REVIEW

Assess whether:

- structural scenarios are genuinely distinct;
- scenario dimensions come from approved scope;
- low/base/high cases are driver-based;
- base is most plausible;
- low retains required scope;
- high represents plausible adverse conditions;
- correlated assumptions are coherent;
- scenario logic does not double count uncertainty;
- scenario-specific exclusions are applied consistently.

Identify assumptions unlikely to occur together.

---

# 22. OPTIONAL-COMPONENT REVIEW

Assess whether optional components are genuinely separable.

Flag:

- base scope hidden as optional;
- ordinary scaling variables implemented as add-ons;
- optional components sharing base costs without boundary rules;
- optional cost included in base despite switch off;
- necessary optional-component dependencies omitted.

---

# 23. RISK AND CONTINGENCY REVIEW

Determine whether:

- known scope is in base;
- uncertain quantities are in ranges/scenarios;
- discrete risks are in contingency;
- management reserve is separate if used;
- risk is not counted in high case and contingency;
- risk impacts map to WBS;
- mitigation assumptions are reflected.

Assess contingency:

- Insufficient
- Reasonable
- Excessive
- Unable to validate

---

# 24. SHARED-COST REVIEW

Check whether:

- natural cost-bearing view is preserved;
- allocation is transparent;
- allocation does not change total;
- allocation basis reflects causation/benefit;
- equal allocation is justified;
- fixed shared costs are not multiplied by participant count;
- participant views distinguish direct from allocated cost.

---

# 25. IN-KIND REVIEW

Assess:

- participant leadership;
- internal PM;
- clinical/public health SMEs;
- legal/privacy/security;
- workflow redesign;
- vendor coordination;
- validation/testing;
- training;
- production support;
- evaluation submissions;
- governance;
- opportunity cost.

Determine whether in-kind costs are:

- properly identified;
- reasonably monetized;
- separately reported;
- included only in economic cost;
- not overstated through replacement-value logic.

---

# 26. EXCLUSIONS REVIEW

For each material exclusion classify:

- Appropriate
- Appropriate with stronger disclosure
- Should be in base
- Should be a sensitivity
- Should be a separate future cost
- Unable to assess

Identify exclusions likely to materially change affordability/sustainability.

---

# 27. SENSITIVITY REVIEW

Assess whether:

- major cost drivers are tested;
- tested alternatives are plausible;
- ranges reflect uncertainty;
- interactions matter;
- results calculate correctly;
- ranking is credible;
- marginal vs total effects are distinguished.

Identify omitted material drivers.

---

# 28. EXECUTIVE-SUMMARY REVIEW

Compare workbook executive summary with detail.

Check:

- low/base/high;
- sponsor-funded;
- participant-funded;
- in-kind;
- economic total;
- one-time;
- recurring;
- contingency;
- organization totals;
- workstream totals;
- evidence quality;
- major assumptions;
- limitations;
- unit costs;
- sustainability implications.

Identify unsupported/overstated/misleading statements.

---

# 29. RECONCILIATION REVIEW

Review reconciliation to CCC and prior model versions.

Determine whether major cost changes are correctly attributed to:

- scope;
- participant architecture;
- organization/cost center;
- quantity;
- evidence/value update;
- formula/scaling;
- allocation;
- optional component;
- correction.

Flag unexplained deltas.

A major reallocation should not be presented as an economic-cost change if total cost is unchanged.

---

# 30. REASONABLENESS CROSS-CHECKS

Where possible test:

- total labor hours ÷ duration;
- implied FTE staffing;
- monthly burn rate;
- cost per participant;
- cost per interface/source;
- cost per implementation month;
- cost per operating month;
- contractor vs participant labor;
- PM percentage;
- evaluation percentage;
- technology percentage;
- recurring vs implementation;
- comparison with whole-project analogues;
- component benchmark bounds.

Cross-checks identify values needing explanation; they are not definitive estimates.

---

# 31. SEVERITY CLASSIFICATION

Classify findings:

- **Critical** — estimate should not be relied on until corrected.
- **High** — could materially change cost/scope/decision.
- **Moderate** — affects accuracy/traceability/interpretation.
- **Low** — minor improvement/documentation issue.
- **Observation** — noteworthy, no correction required.

Also classify finding type:

- Scope omission
- Scope overstatement
- Organization issue
- Cost-center issue
- Double counting
- Formula error
- Quantity error
- Labor-hour issue
- Labor-rate issue
- Non-labor issue
- Existing/incremental treatment
- Analogue issue
- Source issue
- Evidence issue
- Parameter issue
- Scenario issue
- Risk issue
- Allocation issue
- In-kind issue
- Exclusion issue
- Model-delta issue
- Documentation issue
- Executive-summary issue
- Reconciliation issue

---

# 32. REQUIRED OUTPUTS

## 32.1 Independent Review Conclusion

Rate:

- Suitable for decision-making
- Suitable with minor revisions
- Suitable with material qualifications
- Requires substantial revision
- Not suitable for decision-making

Explain basis.

---

## 32.2 Executive Review Summary

Summarize:

- overall quality;
- strengths;
- weaknesses;
- directional bias;
- principal uncertainty;
- base estimate assessment;
- funding/economic-cost distinction;
- contingency;
- decision readiness.

---

## 32.3 Findings Log

| Finding ID | Severity | Finding Type | Workbook / Register / Section | WBS / Parameter / Evidence / Model Mapping ID | Finding | Evidence | Potential Cost Effect | Recommended Correction | Priority |

Be specific.

---

## 32.4 Quantified-Impact Table

| Finding ID | Current Treatment | Corrected / Alternative Treatment | Low Impact | Likely Impact | High Impact | Basis | Confidence |

Do not invent precision.

---

## 32.5 Missing-Work Register

| Missing Work | Organization ID | Phase | Likely Labor Categories | Fixed / Variable | Suggested Estimating Method | Materiality | Rationale |

---

## 32.6 Double-Counting Register

| Overlapping Elements | IDs | Reason | Likely Duplicate Direction | Boundary Rule | Severity |

---

## 32.7 Analogue / Evidence Validation Table

| Evidence ID | Source ID | Cost Element Supported | Developer Use | Reviewer Assessment | Appropriate Use | Limitation | Required Correction |

---

## 32.8 Formula Validation Log

| Sheet | Cell / Row | Formula Purpose | Test | Result | Error / Concern | Correction |

Review material calculations first.

---

## 32.9 Parameter Challenge Table

| Parameter ID | Parameter | Current Value / Treatment | Evidence IDs / Assumption IDs | Reviewer Assessment | More Defensible Treatment | Cost Direction | Validation Needed |

---

## 32.10 Scenario Integrity Table

| Scenario / Driver | Low | Base | High / Alternate | Internally Consistent | Concern | Recommended Revision |

---

## 32.11 CCC Disposition Review Table

| Baseline Evidence ID | Stage 2 Disposition | Reviewer Assessment | Correct Disposition | Model Impact | Required Action |

Focus on material items.

---

## 32.12 Model Delta Review Table

| Delta ID | Template Element | Stage 4 Action | Reviewer Assessment | Implemented Correctly | Concern | Required Correction |

---

## 32.13 Contingency Assessment

State:

- methodology;
- sufficiency;
- double counting;
- missing risks;
- risks to remove/revise;
- management reserve treatment.

---

## 32.14 Cost-Bias Assessment

Rate:

- Low
- Slightly low
- Approximately balanced
- Slightly high
- High
- Unable to determine

Explain.

---

## 32.15 Required Corrections Before Use

Group:

- Must correct before decision use
- Should correct before final approval
- Useful enhancements
- Documentation improvements

---

## 32.16 Residual Uncertainties

Identify uncertainties requiring:

- vendor quotes;
- participant interviews;
- technical discovery;
- legal review;
- security review;
- internal historical data;
- sponsor decision;
- pilot-design decision.

---

## 32.17 Final Validation Checklist

Rate:

- Pass
- Partial pass
- Fail
- N/A

For:

- Scope completeness
- Organizational completeness
- Cost-center completeness
- WBS quality
- Source traceability
- Evidence traceability
- CCC disposition quality
- Analogue appropriateness
- Parameter provenance
- Formula accuracy
- Labor-hour reasonableness
- Labor-rate reasonableness
- Non-labor completeness
- Existing/incremental treatment
- Scenario integrity
- Optional-component treatment
- Contingency
- Shared cost
- In-kind
- Exclusions
- Sensitivity
- Model-delta integrity
- Reconciliation
- Summary reconciliation
- Decision usefulness

---

# 33. REVIEWER RULES

- Be specific.
- Be evidence-based.
- Distinguish factual error from judgment.
- State uncertainty.
- Do not inflate findings with trivial observations.
- Prioritize material defects.
- Identify overestimation as rigorously as underestimation.
- Do not substitute a preferred design for approved scope.
- Do not reject judgment merely because no public benchmark exists.
- Evaluate transparency and reasonableness of judgment.
- Do not recommend arbitrary percentage adjustments.
- Do not calculate an alternative grand total unless evidence supports it.
- Preserve sponsor-vs-economic-cost distinction.
- Evaluate whether a new reviewer can understand the model without reconstructing prior conversations.
- State when a conclusion cannot be validated.
- Check whether deterministic validations were conceptually sufficient.
- Challenge the evidence-disposition decisions.
- Challenge the model-delta decisions.
- Verify traceability independently.

---

# 34. REVIEW OF DETERMINISTIC VALIDATION

Do not merely repeat Stage 4 validation results.

For material validation tests:

1. inspect what the test actually checked;
2. determine whether it could produce a false PASS;
3. independently test a sample;
4. identify missing validations;
5. identify conceptual defects not detectable by formulas.

Create:

| Validation ID | Stage 4 Result | Reviewer Re-Test | Reviewer Result | Concern | Additional Test Needed |

---

# 35. FINAL REVIEW QUESTION

Conclude by answering:

> **If an executive relied on this estimate to decide whether to fund, procure, or proceed with the pilot, what are the three most important things they should understand about its reliability, uncertainty, and likely cost exposure?**

Then state:

> **Independent review status:** [Suitable for decision-making / Suitable with minor revisions / Suitable with material qualifications / Requires substantial revision / Not suitable for decision-making]
