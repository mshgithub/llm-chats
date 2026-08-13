# Source Register Schema

## Purpose

Stores bibliographic/provenance metadata for research sources.

## ID

`SRC-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Source ID | Yes | ID | Stable identifier |
| Source Title | Yes | Text | Title |
| Organization | Yes | Text | Publisher/issuer |
| Date | Yes | Date/year | Publication/award date |
| Source Type | Yes | Text | Contract, grant, report, pricing page, study, etc. |
| URL / Citation | Yes | Text | Original source |
| Dollar Year | No | Year | If source reports monetary data |
| Geographic Scope | No | Text | Jurisdiction |
| Technical / Program Scope | Yes | Text | Scope represented |
| Source Quality | Yes | Enum | Primary / Secondary |
| Confidence | Yes | Enum | High / Moderate / Low / Context |
| Limitations | Yes | Text | What source does not establish |
| Status | Yes | Enum | Active / Unused / Superseded |

## Rules

- Do not renumber circulated Source IDs.
- A Source ID alone never proves a model value; Evidence IDs do.
