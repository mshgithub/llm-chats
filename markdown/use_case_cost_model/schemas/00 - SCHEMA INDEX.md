# PHIG B4 Cost Modeling — Canonical Register Schemas

These schemas define the structured state used by the PHIG B4 deterministic cost-modeling workflow.

They are implementation-neutral. The same fields may later be represented in Markdown tables, JSON, relational tables, or another typed store.

## Core rules

1. IDs are stable and persistent.
2. Superseded objects retain their IDs and history.
3. Cross-register references must resolve.
4. Canonical state is authoritative over narrative prose.
5. Source-derived values must trace to Evidence IDs and Source IDs.
6. Material model rows must trace to WBS IDs and Parameters.
7. Human decisions override lower-precedence analytical assumptions.
8. Every register should include version/status metadata when implemented programmatically.

## Schema files

1. `01 - PROJECT REGISTER.md`
2. `02 - SCOPE REGISTER.md`
3. `03 - ORGANIZATION REGISTER.md`
4. `04 - ASSUMPTION DECISION REGISTER.md`
5. `05 - COST DRIVER REGISTER.md`
6. `06 - SCENARIO REGISTER.md`
7. `07 - PARAMETER REGISTER.md`
8. `08 - SOURCE REGISTER.md`
9. `09 - EVIDENCE REGISTER.md`
10. `10 - WBS REGISTER.md`
11. `11 - MODEL MAPPING REGISTER.md`
12. `12 - RISK UNCERTAINTY REGISTER.md`
13. `13 - EXCLUSION REGISTER.md`
14. `14 - VALIDATION REGISTER.md`
15. `15 - SHARED COST REGISTER.md`
16. `16 - IN-KIND COST REGISTER.md`
17. `17 - DOUBLE COUNTING REGISTER.md`
18. `18 - MODEL INPUT REGISTER.md`
19. `19 - CHANGE LOG.md`
20. `20 - HUMAN GATE REGISTER.md`

## Recommended ID prefixes

| Register | Prefix |
|---|---|
| Scope | `SCP-###` |
| Organization | `ORG-###` |
| Assumption | `ASM-###` |
| Decision | `DEC-###` |
| Question | `QST-###` |
| Cost Driver | `DRV-###` |
| Scenario | `SCN-###` |
| Parameter | `PAR-###` |
| Source | `SRC-###` |
| Evidence | `EVD-###` |
| WBS | `WBS-[ORG]-PP.WW.AA` |
| Model Mapping | `MAP-###` |
| Risk | `RSK-###` |
| Exclusion | `EXC-###` |
| Validation | `VAL-###` |
| Shared Cost | `SHR-###` |
| In-Kind Cost | `INK-###` |
| Double Counting | `OVR-###` |
| Model Input | `MIN-###` |
| Change | `CHG-###` |
| Human Gate | `GATE1-###` / `GATE2-###` |
