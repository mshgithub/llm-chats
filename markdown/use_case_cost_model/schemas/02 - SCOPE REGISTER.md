# Scope Register Schema

## Purpose

Stores every material requirement, boundary, option, exclusion, and approved interpretation of pilot scope.

## ID

`SCP-###`

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Scope ID | Yes | ID | Stable identifier |
| Scope Statement | Yes | Text | Exact requirement/boundary |
| Classification | Yes | Enum | Explicit requirement / Reasonable implication / Approved decision / Analyst assumption / Optional scope / Exclusion / Unresolved question |
| Scope Area | Yes | Enum/text | Functional / Organizational / Technical / Schedule / Funding / Evaluation / Operations / Transition / Other |
| Source or Basis | Yes | Reference/text | Proposal section, decision, or assumption |
| Confidence | Yes | Enum | High / Moderate / Low |
| Materiality | Yes | Enum | Critical / High / Moderate / Low |
| Status | Yes | Enum | Active / Superseded / Unresolved |
| Related Organization IDs | No | List[ORG] | Organizations implicated |
| Related Parameter IDs | No | List[PAR] | Cost/quantity parameters |
| Related WBS IDs | No | List[WBS] | Populated in Stage 3 |
| Related Risk IDs | No | List[RSK] | Related uncertainty |
| Notes | No | Text | Interpretation/limits |

## Rules

- Every material pilot objective and deliverable should resolve to at least one Scope ID.
- Optional and excluded scope must be explicit.
- A Scope ID may not be silently changed after approval; supersede if the meaning materially changes.
