# Evidence Register Schema

## Purpose

Stores one usable datum or discrete evidence claim per row.

## ID

`EVD-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Evidence ID | Yes | ID | Stable identifier |
| Source ID | Yes | SRC | Parent source |
| Evidence Description | Yes | Text | Exact datum/claim |
| Original Value | No | Value/range | Original value |
| Unit | No | Text | Unit |
| Original Dollar Year | Conditional | Year | Monetary evidence |
| Scope Included | Yes | Text | What evidence covers |
| Scope Excluded | Yes | Text | What it does not cover |
| Cost-Bearing Organization | No | ORG/type | Whose cost is represented |
| Evidence Use | Yes | Enum/list | Scope / Quantity / Hours per unit / Staffing / Rate / Non-labor / Run rate / Schedule / Risk / Cross-check / Corroboration |
| Evidence Classification | Yes | Enum | Directly sourced / Derived from public source / Bounded analogue / Context only |
| Confidence | Yes | Enum | High / Moderate / Low / Context |
| CCC Baseline Disposition | Conditional | Enum | APPLY / UPDATE / ADAPT / CORROBORATE / EXCLUDE / REPLACE / NEW |
| Adjustment Needed | Yes | Boolean |
| Adjustment Method | No | Text | Normalization/adaptation/inflation |
| Supported Parameter IDs | No | List[PAR] | Parameter links |
| Supported WBS IDs | No | List[WBS] | Added Stage 3 |
| Limitations | Yes | Text | Boundaries |
| Status | Yes | Enum | Active / Excluded / Superseded |

## Rules

- One Evidence ID should represent one distinct datum/claim.
- EXCLUDE evidence may not support active model values.
- Derived evidence must preserve formula and source.
