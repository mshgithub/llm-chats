# Change Log Schema

## Purpose

Records changes to canonical state and model implementation across versions.

## ID

`CHG-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| Change ID | Yes | Stable ID |
| Date | Yes | Date |
| Stage | Yes | Workflow stage |
| Object ID(s) | Yes | Changed canonical IDs/workbook objects |
| Prior Treatment | Yes | Previous state |
| New Treatment | Yes | New state |
| Change | Yes | Concise description |
| Reason | Yes | Why changed |
| Initiator | Yes | User / agent / reviewer |
| Upstream Effect | No | Earlier state affected |
| Downstream Effect | No | Later state affected |
| Rerun Required | Yes | None / S1 / S2 / S3 / S4 / targeted |
| Validation Required | Yes | Tests |
| Status | Yes | Open/Implemented/Validated/Superseded |

## Change classification

Recommended classifications:

- scope
- organization/cost center
- quantity
- evidence/value
- formula/scaling
- rate
- allocation
- scenario
- optional component
- correction
