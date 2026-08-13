# Shared Cost Register Schema

## Purpose

Controls treatment and optional allocation of costs supporting multiple participants/workstreams.

## ID

`SHR-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| Shared Cost ID | Yes | Stable ID |
| Shared Cost | Yes | Description |
| Related WBS IDs | Yes | WBS links |
| Natural Cost-Bearing Org ID | Yes | Where cost actually resides |
| Recommended Core Treatment | Yes | Retain centrally / etc. |
| Allocation Basis | No | Actual hours / participant type / interfaces / usage / benefit / equal |
| Alternative Treatment | No | Other view |
| Economic-Cost Treatment | Yes | How shown in total economic cost |
| Allocation Reconciliation Rule | Yes | Sum allocations = original shared cost |
| Rationale | Yes | Why method is appropriate |
| Status | Yes | Active/Superseded |
