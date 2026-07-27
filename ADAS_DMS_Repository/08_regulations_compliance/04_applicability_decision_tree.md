# Regulatory Applicability Decision Tree

```mermaid
flowchart TD
    A[Define market and vehicle programme] --> B{India or EU/UNECE?}
    B -->|India| C{Vehicle category M2/M3/N2/N3?}
    C -->|Yes| D{New model on/after 2027-10-01 or existing model on/after 2028-01-01?}
    D -->|Yes| E[Apply CMVR Rule 125Q + controlled AIS-184 edition]
    D -->|No| F[Monitor future mandate; customer requirement may still apply]
    C -->|No| G{M1 Bharat NCAP target?}
    G -->|Yes| H[Apply controlled AIS-197 protocol as voluntary/contractual target]
    G -->|No| I[Apply customer DMS specification and general CMVR obligations]

    B -->|EU/UNECE| J{M/N type approval under EU GSR?}
    J -->|Yes| K[Apply EU 2019/2144 + DDAW 2021/1341 + ADDW 2023/2590 as applicable]
    J -->|No| L[Check national adoption and customer specification]
    K --> M{Sustained longitudinal + lateral assistance/DCAS fitted?}
    M -->|Yes| N[Apply adopted UN R171 series/supplement]
    M -->|No| O[No R171 claim]

    E --> P[Select regulatory profile and clause matrix]
    H --> P
    I --> P
    N --> P
    O --> P
    L --> P
    P --> Q[Derive SYS/HW/SW/IF/Safety requirements]
    Q --> R[Approve evidence plan with homologation/legal]
    R --> S[Freeze market calibration and release baseline]
```

## Decision record attributes

| Attribute | Required content |
|---|---|
| Programme ID | vehicle platform/model/variant |
| Market | country/type-approval territory |
| Vehicle category | M1/M2/M3/N1/N2/N3 etc. |
| Model status | new type/new model/existing model |
| SOP and type-approval dates | exact calendar dates |
| Feature set | DDAW, ADDW, DCAS, AEBS, LDWS, fleet features |
| Regulation edition | regulation/AIS series, supplement and amendment |
| Applicability status | mandatory now/future, voluntary, feature-triggered, contractual, N/A |
| Interpretation owner | homologation/legal/system/safety |
| Evidence owner | responsible function/team |
| Open points | ambiguity, exemption, pending amendment, technical-service decision |
| Approval | named approvers and date |
