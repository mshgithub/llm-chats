# Assumption & Decision Register Schema

## Purpose

Stores approved decisions, provisional assumptions, and unresolved questions.

## IDs

- `ASM-###` — assumption
- `DEC-###` — approved/user decision
- `QST-###` — unresolved question

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| ID | Yes | ID | Stable identifier |
| Type | Yes | Enum | Assumption / Decision / Question |
| Statement | Yes | Text | Exact issue/treatment |
| Category | Yes | Text | Scope / Technical / Participation / Schedule / Funding / Legal / Security / Evaluation / etc. |
| Basis | Yes | Text/reference | Why treatment exists |
| Effect on Scope / Cost | Yes | Text | Direction/materiality |
| Low | No | Value | If ranged |
| Base | No | Value | If ranged |
| High | No | Value | If ranged |
| Confidence | Yes | Enum | High / Moderate / Low |
| Validation Needed | No | Text | What would resolve it |
| Owner | No | Text/ORG | Decision owner |
| Recommended Model Treatment | Yes | Enum/text | Fixed / Editable / Range / Scenario / Optional / Contingency / Exclusion / Unresolved |
| Status | Yes | Enum | Active / Resolved / Superseded |
| Affected IDs | No | List | Cross-register dependencies |

## Rules

- Never present an assumption as sourced evidence.
- User decisions outrank analytical assumptions.
- Unresolved questions should not block progress when safe parameterization is possible.
