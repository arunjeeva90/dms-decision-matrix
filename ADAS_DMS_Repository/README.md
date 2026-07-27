# ADAS DMS Platform Requirements Repository

OEM/Tier-1 style, version-controlled requirements baseline for a scalable Driver Monitoring System (DMS) platform.

## Purpose
This repository structures DMS product definition, stakeholder requirements, system requirements, architecture, hardware/software requirements, safety, SOTIF, cybersecurity, interfaces, regulations, verification, data/AI lifecycle, and bidirectional traceability in a DOORS-like hierarchy.

## Navigation
1. [Governance and authoring rules](00_governance/README.md)
2. [Platform definition](01_platform_definition/README.md)
3. [Stakeholder requirements](02_stakeholder_requirements/README.md)
4. [System requirements](03_system_requirements/README.md)
5. [System architecture: BDD, IBD, behavior](04_architecture/README.md)
6. [Subsystem requirements](05_subsystems/README.md)
7. [Functional safety and SOTIF](06_safety_sotif/README.md)
8. [Cybersecurity and privacy](07_cybersecurity_privacy/README.md)
9. [Regulations and compliance](08_regulations_compliance/README.md)
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
       └── System Requirements (SYS-DMS-xxxx)
            ├── Hardware Requirements (HWR-DMS-xxxx)
            ├── Software Requirements (SWR-DMS-xxxx)
            ├── Interface Requirements (IFR-DMS-xxxx)
            ├── Safety Requirements (FSR/TSR-DMS-xxxx)
            └── Verification Cases (TST-DMS-xxxx)
```

## Baseline status
**v0.1 — Concept and system-definition baseline.** Regulatory thresholds remain subject to formal legal/homologation review and market-specific calibration.
