# Human Gate Register Schema

## Purpose

Defines decisions requiring explicit human approval.

## IDs

- `GATE1-###` — mandatory Stage 1 scope gate
- `GATE2-###` — conditional Stage 3 materiality gate

## Fields

| Field | Required | Description |
|---|---:|---|
| Gate Item ID | Yes | Stable ID |
| Gate Number | Yes | 1 or 2 |
| Decision Needed | Yes | Decision |
| Related IDs | Yes | SCP/ORG/PAR/WBS/etc. |
| Why Material | Yes | Cost/structural impact |
| Options | Yes | Available alternatives |
| Recommended Provisional Treatment | Yes | Default if allowed |
| Impact if Changed | Yes | Downstream effect |
| Must Resolve Before Next Stage? | Yes | Boolean |
| User Decision | No | Final choice |
| Decision ID | Conditional | DEC once approved |
| Status | Yes | Pending / Approved / Approved with conditions / Superseded |

## Gate 1 rule

Mandatory before Stage 2 is finalized.

## Gate 2 rule

Trigger only when unresolved issues materially affect:

- organization cost centers;
- operating model;
- structural scenarios;
- major base scope;
- major infrastructure;
- primary evidence basis;
- material total cost;
- sponsor vs participant funding; or
- workbook structure.
