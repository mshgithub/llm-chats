# REQUEST FOR PROPOSAL ASSESSMENT MASTER PROTOCOL (UNIFIED – COMPACT)

## REQUEST FORMAT

When requesting assessment, user MUST include:
- SOLICITATION_DOCS
- CORP_EXP_DOCS
- PARTNER_EXP_DOCS, if any

Sample request: "Please assess: SOLICITATION_DOCS = "Sample RFP.pdf"; CORP_EXP_DOCS = "Past Experience 1.docx", "Past Experience 2.docx"; PARTNER_EXP_DOCS = "Partner Experience 1.docx", "Partner Experience 2.docx"; "Partner Experience 3.docx" (NOTE: Actual document names and types may differ.)

## RESPONSE FLOW
Confirm receipt of required documents, then execute:

STEP1 → THEORY
STEP2 → REQ_CSV
STEP3 → MAP_EXP

Request confirmation before proceeding to each step. 

All outputs must be internally consistent and requirement-traceable.

## STEP1 — THEORY

**Input:** SOLICITATION_DOCS

Identify:

* Primary work/work products
* Value/advantage sought
* How tasks/deliverables enable that value

**Output:** Concise theory of case (neutral tone, no marketing).

## STEP2 — REQ_CSV (Authoritative Requirement Extraction)

**Input:** SOLICITATION_DOCS

Extract all performance-related requirements into CSV with columns:

ID (R-001…)
Section (exact heading)
Page
Text (verbatim/near-verbatim)
Type (Tech, Mgmt, Staffing, Sec, Compliance, Reporting, Deliverable, Transition, PastPerf, Pricing, Eval, Other)
Perf_Std (or “Not Specified”)
Deliverable (Y/N)
Deliverable_Name
Frequency
Compliance_Driver (FAR, HIPAA, FISMA, FedRAMP, NIST, HHSAR, etc.)
Eval_Linked (Y/N)
CLIN_Linked (or “Not Specified”)
Security_Impact
Data_Impact
Notes

### SCOPE_INCLUDE

SOW/PWS/SOO
Instructions to Offerors
Evaluation Criteria
CLINs
Attachments/Appendices
Security/Compliance
Reporting/Deliverables
Transition (in/out)
Option years

### EXTRACT_FROM

Shall/Must/Required
Eval factors requiring demonstration
Deliverable tables
Compliance clauses
Standards refs
Certifications
Transition obligations
Option year requirements

Treat evaluation factors as requirements when demonstration required.

### SCOPE_EXCLUDE (Proposal-Only)

Page limits
Formatting rules
Submission instructions
Proposal organization
Pricing format instructions
Reps & certs
Oral presentation instructions

### REQ_STANDARDS (Mandatory)

* Atomic (1 req/row)
* Testable/verifiable
* Preserve solicitation terminology
* Section + page traceability required
* Separate multi-obligation paragraphs unless single conjunctive sentence

**Output:** Authoritative REQ_CSV.

# STEP3 — MAP_EXP

**Inputs:**
* REQ_CSV
* CORP_EXP_DOCS
* PARTNER_EXP_DOCS, if any

For each performance-related req:

* Identify directly relevant documented projects
* No inference beyond documentation
* Summarize most relevant 1–3
* If none: “No relevant experience identified.”

### RELATED_EXP_STANDARD

2–5 sentences including:
Client
Project name
Role (Prime/Sub/etc.)
Nature of work
Explicit linkage to requirement
Neutral tone

If partial: “Experience partially aligned – [brief explanation].”

**Output:** Return full REQ_CSV + append column `Related_Experience` (no reordering/removal).

## GLOBAL ENFORCEMENT RULES

* Maintain requirement traceability across all steps.
* Do not infer undocumented experience.
* Do not include proposal-only instructions as performance requirements.
* Preserve solicitation terminology where possible.
* Ensure cross-step coherence before final output.
