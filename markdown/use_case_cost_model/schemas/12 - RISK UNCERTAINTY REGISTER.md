# Risk & Uncertainty Register Schema

## Purpose

Separates uncertainty already reflected in model ranges from discrete risks used for contingency.

## ID

`RSK-###`

## Fields

| Field | Required | Description |
|---|---:|---|
| Risk ID | Yes | Stable ID |
| Risk / Uncertainty | Yes | Description |
| Related Scope / Driver / Parameter / WBS IDs | Yes | Dependencies |
| Base Position | Yes | Base assumption |
| Adverse Condition | Yes | Risk event/state |
| Probability / Likelihood | No | Quantitative or qualitative |
| Cost Impact Basis | No | Amount/range/method |
| Schedule Impact | No | Impact |
| Cost Direction | Yes | Increase/decrease/mixed |
| Materiality | Yes | Critical/High/Moderate/Low |
| Mitigation | No | Planned response |
| Validation Needed | No | What resolves uncertainty |
| Model Treatment | Yes | Range / Scenario / Contingency / Optional / Exclusion / Monitor |
| Double-Counting Check | Yes | How duplication is avoided |
| Status | Yes | Active/Closed/Superseded |

## Rules

- Known scope belongs in base cost, not contingency.
- Risks already fully represented in high-case assumptions should not also be fully priced in contingency.
