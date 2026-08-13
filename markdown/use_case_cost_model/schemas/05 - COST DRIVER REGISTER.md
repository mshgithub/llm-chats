# Cost Driver Register Schema

## Purpose

Defines variables that materially drive cost or schedule.

## ID

`DRV-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Driver ID | Yes | ID | Stable identifier |
| Cost Driver | Yes | Text | Driver name |
| Description | Yes | Text | Definition |
| Cost Category | Yes | Text | Labor / Non-labor / Shared / Operations / etc. |
| Primary Scaling Unit | Yes | Text | Per org, interface, month, etc. |
| Known Quantity | No | Value/PAR | Known value |
| Potential Range | No | Text/values | Plausible range |
| Organizations Affected | Yes | List[ORG] | Cost centers affected |
| Cost / Schedule Effect | Yes | Text | Impact direction |
| Fixed / Variable / Step-Fixed | Yes | Enum/list | Classification |
| One-Time / Recurring | Yes | Enum/list | Classification |
| Source / Assumption ID | Yes | Reference | Basis |
| Materiality | Yes | Enum | Critical / High / Moderate / Low |
| Related Parameter IDs | No | List[PAR] | Parameter representation |
| Notes | No | Text | Caveats |
