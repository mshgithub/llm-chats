# Parameter Register Schema

## Purpose

Stores every model input or calculated parameter used by Stage 3/4.

## ID

`PAR-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Parameter ID | Yes | ID | Stable identifier |
| Parameter | Yes | Text | Name |
| Definition | Yes | Text | Exact meaning |
| Unit | Yes | Text | Hours, months, %, dollars, etc. |
| Parameter Type | Yes | Enum | Quantity / Effort / Rate / Unit cost / Factor / Switch / Duration / Frequency / Volume |
| Low | No | Value | Low case |
| Base | No | Value | Base case |
| High | No | Value | High case |
| Selected Value | No | Value/formula | Active scenario value |
| Value Classification | Yes | Enum | User-provided / Directly sourced / Derived from public source / Bounded analogue / Internal historical / Vendor quote / Expert judgment / Placeholder |
| Evidence IDs | Conditional | List[EVD] | Required for source-based values |
| Assumption / Decision IDs | Conditional | List[ASM/DEC] | Required for judgment/decision values |
| Original Dollar Year | Conditional | Year | For historical money |
| Target Dollar Year | Conditional | Year | For adjusted money |
| Adjustment ID | Conditional | ADJ | Inflation/escalation |
| Confidence | Yes | Enum | High / Moderate / Low |
| Editable | Yes | Boolean | User-editable input? |
| Status | Yes | Enum | Active / Superseded |
| Workbook Location | No | Reference | Populated Stage 4 |
| Notes | No | Text | Caveats |

## Rules

- Source-derived parameters require Evidence IDs.
- Judgment/placeholder parameters require Assumption IDs.
- Do not fabricate defaults where evidence is inadequate.
