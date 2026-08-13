# Validation Register Schema

## Purpose

Records deterministic validation tests and dispositions.

## ID

`VAL-###` or stage-specific `VAL-S1-###`, etc.

## Fields

| Field | Required | Description |
|---|---:|---|
| Validation ID | Yes | Stable ID |
| Stage | Yes | S1/S2/S3/S4/Review |
| Category | Yes | Structural / Formula / Traceability / Reconciliation / Reasonableness / etc. |
| Test | Yes | Test description |
| Object Tested | Yes | Register/workbook object |
| Result | Yes | PASS / REVIEW / ERROR |
| Evidence / Finding | Yes | Result detail |
| Severity | Yes | Critical/High/Moderate/Low |
| Required Correction | No | Remediation |
| Status | Yes | Open/Closed/Waived |
| Waiver Decision ID | Conditional | DEC |
| Notes | No | Caveats |

## Rules

- Unresolved ERROR blocks final delivery.
- REVIEW requires disposition.
- Deterministic PASS does not replace independent review.
