# Engineering Standards Baseline

These standards support the OEM/Tier-1 development and assurance case. They do not replace market-specific vehicle type approval.

| Standard/process | Role in DMS programme | Mandatory treatment |
|---|---|---|
| ISO 26262 | malfunctioning-behaviour safety lifecycle, HARA, safety concept, HW/SW safety work products, confirmation measures | apply at the OEM/Tier-1 allocated ASIL and SEooC assumptions |
| ISO 21448 | SOTIF for performance limitations, triggering conditions, foreseeable misuse and validation completeness | apply to DMS perception and decision limitations |
| ISO/SAE 21434 | cybersecurity lifecycle, TARA, cybersecurity goals/claims, verification and post-development activities | apply to ECU, interfaces, model/update and data assets |
| Automotive SPICE | process capability for SYS/SWE/HWE/SUP/MAN processes | programme quality target defined by customer |
| ISO 24089 | software update engineering | use with customer SUMS/UN R156 or AIS-190 obligations |
| ISO 16750 | environmental conditions and testing for electrical/electronic equipment | allocate to ECU, camera and illumination hardware |
| ISO 7637 series | vehicle electrical transient immunity | allocate to power and vehicle-interface design |
| CISPR 25 / ISO 11452 series | emissions and immunity | allocate to EMC design and validation |
| AEC-Q100/Q104/Q102 as applicable | component qualification | component-selection evidence, not system qualification |
| ISO 14229 / ISO 15765 | UDS diagnostics over CAN | diagnostic services, DTCs, DID and update support |
| AUTOSAR E2E / ISO 26262 communication mechanisms | safety-related communication protection | alive counter, CRC, timeout and data-ID design |

## AI/ML assurance work products

The programme shall maintain, at minimum:

- intended function and ODD definition;
- dataset specification, provenance, consent and licence register;
- subgroup/diversity coverage and known limitations;
- annotation specification and quality acceptance;
- training configuration and reproducibility record;
- model card and release note;
- calibration and confidence assessment;
- scenario-based performance evidence;
- robustness, perturbation and fault-injection evidence;
- change-impact analysis for model/data updates;
- field-monitoring and incident-response plan.

## Rule

A requirement may cite a standard only after the programme records the exact edition, clause, applicability rationale, allocated work product and verification evidence in `compliance_matrix.csv`.
