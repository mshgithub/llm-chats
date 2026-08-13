# Model Mapping Register Schema

## Purpose

Maps canonical WBS/parameter state into the Excel workbook.

## ID

`MAP-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| Mapping ID | Yes | Stable identifier |
| WBS ID / Parameter ID | Yes | Source state object |
| Workbook Sheet | Yes | Destination sheet |
| Table / Range | Yes | Destination object |
| Row / Cell / Named Range | Yes | Exact location |
| Template Element | No | CCC baseline element |
| Action | Yes | PRESERVE / UPDATE / ADD / REMOVE / REPLACE |
| Formula Family | No | Formula pattern |
| Evidence IDs | No | Evidence basis |
| Source IDs | No | Source basis |
| Assumption / Decision IDs | No | Non-source basis |
| Validation Status | Yes | PASS / REVIEW / ERROR |
| Notes | No | Transformation logic |

## Rules

- Every material model row should map to canonical state.
- Workbook location changes do not change WBS/Parameter IDs.
