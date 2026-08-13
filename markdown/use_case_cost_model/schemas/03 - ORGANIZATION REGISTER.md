# Organization Register Schema

## Purpose

Defines organization types/instances and separates participation, performance, cost bearing, funding, and reporting-cost-center roles.

## ID

`ORG-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Organization ID | Yes | ID | Stable identifier |
| Organization Type | Yes | Text | PHA, HIE/HDU, hospital, vendor, evaluator, etc. |
| Organization Name | No | Text | Actual entity when known |
| Required / Optional | Yes | Enum | Required / Optional / Conditional |
| Quantity | Yes | Number/parameter reference | Number of organizations of this type |
| Role | Yes | Text | Pilot role |
| Performing Organization | Yes | Boolean | Performs pilot work |
| Cost-Bearing Organization | Yes | Boolean | Incurs economic cost |
| Required Reporting Cost Center | Yes | Boolean | Must appear distinctly in model reporting |
| Funding Treatment | Yes | Enum | Sponsor-funded / Participant-funded / In-kind / Mixed / TBD |
| Likely In-Kind Effort | Yes | Enum/text | None / Low / Moderate / High / Description |
| Relationships / Dependencies | No | List/text | Other org dependencies |
| Source / Basis | Yes | Reference | Scope/decision source |
| Status | Yes | Enum | Active / Superseded |

## Rules

- Participation, performance, cost-bearing, funding, and reporting-cost-center status are independent attributes.
- Do not assume a participant is funded.
- Do not assume a performer bears the cost.
