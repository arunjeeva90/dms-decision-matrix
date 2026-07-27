# ADAS DMS Platform Requirements Repository

OEM/Tier-1 style, version-controlled requirements baseline for a scalable Driver Monitoring System (DMS) platform.

## Purpose
This repository structures DMS product definition, stakeholder requirements, system requirements, architecture, hardware/software requirements, safety, SOTIF, cybersecurity, interfaces, regulations, verification, data/AI lifecycle, and bidirectional traceability in a DOORS-like hierarchy.

## Current baseline scope

- **220 atomic system requirements** across platform, sensing, drowsiness, distraction, availability, temporal/HMI, ADAS fusion, degraded operation, calibration and non-functional domains.
- Explicit senior-engineering review of all live decision-matrix scenarios `DMS-001` through `DMS-029`.
- Scenario-to-requirement-to-verification traceability with dedicated CSV catalogues.
- Independent drowsiness, distraction, driver-availability and DMS-sensing-availability outputs.
- Mandate-driven India, EU and UNECE regulatory profiles.

## Navigation
1. [Governance and authoring rules](00_governance/README.md)
2. [Platform definition](01_platform_definition/README.md)
3. [Stakeholder requirements](02_stakeholder_requirements/README.md)
4. [System requirements](03_system_requirements/README.md)
5. [System architecture: BDD, IBD, behavior](04_architecture/README.md)
6. [Subsystem requirements](05_subsystems/README.md)
7. [Functional safety and SOTIF](06_safety_sotif/README.md)
8. [Cybersecurity and privacy](07_cybersecurity_privacy/README.md)
9. [Regulations, mandates and compliance](08_regulations_compliance/README.md)
10. [Interfaces](09_interfaces/README.md)
11. [Verification and validation](10_verification_validation/README.md)
12. [Data and AI lifecycle](11_data_ai_lifecycle/README.md)
13. [Hardware requirements](12_hardware/README.md)
14. [Software requirements](13_software/README.md)
15. [Calibration requirements](14_calibration/README.md)
16. [Traceability matrix](15_traceability/README.md)
17. [Change control](16_change_control/README.md)

## Requirements hierarchy

```text
Business / Product Objectives
  └── Stakeholder Requirements (STK-DMS-xxxx)
       ├── Regulatory Sources (REG-IND/EU/UNECE-xxxx)
       └── System Requirements (SYS-DMS-xxxx)
            ├── Hardware Requirements (HWR-DMS-xxxx)
            ├── Software Requirements (SWR-DMS-xxxx)
            ├── Interface Requirements (IFR-DMS-xxxx)
            ├── Safety Requirements (FSR/TSR-DMS-xxxx)
            └── Verification Cases (TST-DMS-xxxx)
```

## Governing output architecture

```text
Behavioral severity: NORMAL → MONITOR → WARNING → DANGER → CRITICAL
DMS availability:      OK → LIMITED → DEGRADED → UNAVAILABLE
```

These axes shall remain independent. A blocked camera is a system-availability failure, not a critical driver-behaviour classification.

## Regulatory structure

The compliance module distinguishes:

- legally mandatory requirements;
- future notified mandates;
- type-approval regulations triggered by fitted functions;
- voluntary NCAP/rating targets;
- engineering standards and customer-contractual requirements.

The current baseline includes India CMVR/AIS-184 applicability for M2/M3/N2/N3 programmes, Bharat NCAP/AIS-197 tracking, EU DDAW and ADDW, UNECE R171 DCAS integration, cybersecurity/software-update references, and India DPDP privacy obligations.

## Baseline status
**v0.3 — Scenario-decomposed system-requirements baseline.** Exact calibration thresholds, controlled regulatory clauses, subsystem performance allocations and technical-service interpretations remain subject to formal OEM design review, safety analysis and homologation approval.
