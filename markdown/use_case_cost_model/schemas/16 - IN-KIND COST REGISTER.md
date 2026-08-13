# In-Kind Cost Register Schema

## Purpose

Captures hidden/unreimbursed labor and contributed resources.

## ID

`INK-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| In-Kind ID | Yes | Stable ID |
| Organization ID | Yes | ORG |
| WBS ID | Yes | Related activity |
| Activity | Yes | Description |
| Labor / Non-Labor | Yes | Type |
| Likely Labor Category | No | Role |
| Scaling Unit | Yes | Hours/org/month/etc. |
| Quantity / Hours Parameter ID | No | PAR |
| Valuation Method | Yes | Opportunity cost / hours only / separate disclosure |
| Monetize? | Yes | Boolean |
| Include in Sponsor Cost? | Yes | Boolean, normally No |
| Include in Economic Cost? | Yes | Boolean |
| Evidence / Assumption IDs | Yes | Basis |
| Risk if Omitted | Yes | Why it matters |
| Status | Yes | Active/Superseded |

## Rules

- Do not double count reimbursed participant labor as in kind.
- Contributed infrastructure should not automatically be valued at replacement cost.
