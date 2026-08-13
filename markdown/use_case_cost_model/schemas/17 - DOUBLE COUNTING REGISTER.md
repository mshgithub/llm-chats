# Double-Counting Register Schema

## Purpose

Defines explicit boundaries where work/cost/evidence could overlap.

## ID

`OVR-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| Overlap ID | Yes | Stable ID |
| Potential Overlap | Yes | Description |
| WBS IDs Affected | Yes | WBS links |
| Evidence IDs Affected | No | Evidence links |
| Risk of Double Counting | Yes | High/Moderate/Low |
| Boundary Rule | Yes | Conceptual rule |
| Stage 4 Implementation Rule | Yes | Spreadsheet control |
| Validation Test | Yes | How checked |
| Status | Yes | Active/Resolved/Superseded |

## Common checks

- sponsor vs prime PM
- shared vs local architecture
- legal templates vs negotiation
- onboarding vs TA
- testing vs remediation
- vendor fee vs internal labor
- stabilization vs operations
- monitoring vs evaluation
- high-case uncertainty vs contingency
- natural vs allocated shared-cost views
