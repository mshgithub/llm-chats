# Scenario Register Schema

## Purpose

Defines structural delivery scenarios. Low/base/high estimating cases are not automatically structural scenarios.

## ID

`SCN-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Scenario ID | Yes | ID | Stable identifier |
| Scenario Name | Yes | Text | Human-readable name |
| Structural Dimensions | Yes | Text/list | What fundamentally differs |
| Included Scope IDs | Yes | List[SCP] | Active scope |
| Excluded Scope IDs | No | List[SCP] | Scope excluded |
| Parameter Overrides | No | List[PAR:value] | Scenario-specific values |
| Optional Components | No | List[OPT] | Activated add-ons |
| Shared-Cost Treatment | No | Text | Any scenario-specific rule |
| Rationale | Yes | Text | Why scenario matters |
| Status | Yes | Enum | Active / Inactive / Superseded |

## Rules

- Structural scenarios must represent materially different delivery configurations.
- Do not create scenarios simply to express uncertainty in hours/rates.
