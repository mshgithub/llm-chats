# WBS Register Schema

## Purpose

Defines the authoritative cost-estimating structure.

## ID

`WBS-[ORGCODE]-PP.WW.AA`

## Fields

| Field | Required | Description |
|---|---:|---|
| WBS ID | Yes | Stable ID |
| Parent WBS ID | No | Hierarchy parent |
| Organization ID | Yes | Primary organizational perspective |
| Organization Type | Yes | Type |
| Reporting Cost Center | Yes | Reporting category |
| Project Phase | Yes | Phase |
| Workstream | Yes | Workstream |
| Deliverable / Work Package | Yes | Package |
| Activity | Yes | Estimating activity |
| Subactivity | No | Further decomposition |
| Description | Yes | Work definition |
| Accountable Org ID | Yes | Accountability |
| Performing Org ID | Yes | Performer |
| Supporting Org IDs | No | Support |
| Reviewing / Approving Org IDs | No | Review |
| Cost-Bearing Org ID | Yes | Economic burden |
| Funding Treatment | Yes | Sponsor / participant / in-kind / mixed |
| Entry Criteria | No | Start condition |
| Output / Deliverable | Yes | Result |
| Completion / Acceptance Criteria | Yes | Done definition |
| Dependencies | No | Dependencies |
| Predecessors | No | WBS links |
| Successors | No | WBS links |
| Scaling Classification | Yes | Fixed/shared/variable/etc. |
| Scaling Unit | Yes | Unit |
| Quantity Parameter ID | Conditional | PAR |
| Fixed / Variable / Step-Fixed | Yes | Classification |
| One-Time / Recurring | Yes | Classification |
| Scenario IDs | No | Applicable scenarios |
| Optional / Base | Yes | Base/Optional |
| Lead Labor Category | No | Lead role |
| Supporting Labor Categories | No | Roles |
| Participant Labor | No | Roles |
| Vendor Labor | No | Roles |
| Non-Labor Inputs | No | Items |
| Estimating Method ID | Yes | EMT |
| Primary Evidence IDs | Conditional | EVD |
| Corroborating Evidence IDs | No | EVD |
| Evidence Use | No | What evidence supports |
| Source Confidence | Yes | High/Moderate/Low |
| Assumption / Decision IDs | No | ASM/DEC |
| Risk IDs | No | RSK |
| Notes | No | Caveats |
| Status | Yes | Active/Superseded |

## Rules

- Each estimable activity must have a scaling unit.
- Split work when scaling, funding, cost bearer, recurrence, or evidence basis differs materially.
