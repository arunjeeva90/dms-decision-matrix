# 08 — Regulations, Mandates and Compliance

This module is the controlled regulatory gateway for the DMS platform. It separates **legal mandates**, **consumer-rating protocols**, **type-approval regulations**, **engineering standards**, and **OEM contractual requirements**.

> No requirement shall be marked compliant only because a regulation or standard is listed here. Compliance requires an approved applicability decision, controlled source copy, clause-level derivation, objective evidence and homologation/legal sign-off.

## Navigation

1. [India regulatory baseline](01_india_regulatory_baseline.md)
2. [EU and UNECE regulatory baseline](02_eu_unece_regulatory_baseline.md)
3. [Lifecycle, safety, cybersecurity and process standards](03_engineering_standards_baseline.md)
4. [Applicability decision tree](04_applicability_decision_tree.md)
5. [Regulatory evidence checklist](05_regulatory_evidence_checklist.md)
6. [Compliance matrix](compliance_matrix.csv)

## Requirement-source hierarchy

| Tier | Meaning | Examples | Repository treatment |
|---|---|---|---|
| 1 | Legally mandated vehicle requirement | CMVR Rule 125Q/AIS-184 for applicable Indian heavy-vehicle categories; EU GSR DDAW/ADDW | Mandatory when market/category/date gates are met |
| 2 | Type-approval regulation invoked by vehicle function | UN R171 for DCAS; UN R155/R156 where adopted | Mandatory only for applicable market/function/type approval |
| 3 | Voluntary consumer-rating protocol | Bharat NCAP/AIS-197 | Product target, not statutory homologation unless contractually required |
| 4 | Safety/security/process standard | ISO 26262, ISO 21448, ISO/SAE 21434, Automotive SPICE | Contractual/product-development obligation; not itself vehicle type approval |
| 5 | OEM/Tier-1 specification | Customer DMS performance, DBC, diagnostics, data governance | Mandatory by contract and programme baseline |

## Current programme baseline

| Market/use case | Primary DMS reference | Current repository position |
|---|---|---|
| India M2/M3/N2/N3 programmes | CMVR Rule 125Q with AIS-184 | Regulatory profile `INDIA_HDV_DDAW`; exact notified edition and exemptions require controlled-copy review |
| India M1 passenger cars | CMVR type approval + Bharat NCAP/AIS-197 where targeted | AIS-184 applicability shall not be assumed; maintain a separate passenger-car product/NCAP profile |
| EU M/N type approval | Regulation (EU) 2019/2144, Delegated Regulation (EU) 2021/1341 DDAW, Delegated Regulation (EU) 2023/2590 ADDW | Regulatory profiles `EU_DDAW` and `EU_ADDW` |
| SAE L2 / sustained longitudinal+lateral assistance | UN R171 DCAS where adopted | DMS/driver-engagement interface and transition behaviour shall be derived from the approved series/supplement |
| Cybersecurity and software update type approval | UN R155/R156 or Indian AIS-189/AIS-190 when legally invoked | Architecture-ready; applicability and final notified editions tracked separately |
| Cabin-data processing in India | DPDP Act 2023 and DPDP Rules 2025 | Privacy-by-design, purpose limitation, retention control and data-subject workflow required where personal data is processed |

## Mandatory review gates

Before releasing a market calibration or homologation build, the programme shall approve:

1. jurisdiction and vehicle category;
2. new-type versus existing-type effective date;
3. vehicle maximum design speed and stated exemptions;
4. DDAW, ADDW, DCAS and NCAP feature applicability;
5. controlled regulation/AIS revision and amendments;
6. technical-service interpretation and evidence plan;
7. privacy, cybersecurity and software-update obligations;
8. deviations, open interpretations and residual compliance risk.

## Status vocabulary

- `MANDATORY_NOW` — legally applicable to the selected vehicle programme today.
- `MANDATORY_FUTURE` — notified with a future application date.
- `VOLUNTARY_RATING` — consumer-rating target, not base type approval.
- `APPLICABLE_IF_FEATURED` — applies when the vehicle implements the referenced function.
- `CONTRACTUAL` — required by OEM/Tier-1 agreement.
- `MONITOR` — draft, proposed, under amendment or awaiting applicability confirmation.
- `NOT_APPLICABLE` — formally excluded with rationale and approval.
