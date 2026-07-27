# India Regulatory Baseline

## 1. CMVR mandate path for heavy vehicles

Government communications published in 2026 state that Advanced Driver Assistance Systems for **M2, M3, N2 and N3** vehicles include Driver Drowsiness and Attention Warning Systems and become effective for:

- **new models:** 1 October 2027;
- **existing models:** 1 January 2028.

The DDAW technical reference is **AIS-184**, invoked through the CMVR ADAS provisions. The programme shall obtain the controlled Gazette notification and the final applicable AIS-184 edition before freezing homologation requirements.

### Programme classification

| Item | Baseline |
|---|---|
| Legal status | `MANDATORY_FUTURE` for applicable M2/M3/N2/N3 programmes |
| Product profile | `INDIA_HDV_DDAW` |
| First programme gate | vehicle category and new/existing model classification |
| Core feature | driver drowsiness/attention assessment and driver warning |
| Evidence route | Rule 126 test agency / technical service as applicable |
| Open item | reconcile the currently published AIS listing, amendments and controlled final text |

## 2. AIS-184 requirement themes

The controlled AIS-184 clause map shall be the source of truth. Until that review is completed, the architecture shall support the following themes without claiming clause compliance:

- DDAW activation and operating conditions;
- drowsiness assessment and warning strategy;
- day/night operation within the specified ODD;
- driver HMI warning and failure indication;
- system deactivation/reactivation rules;
- vehicle speed and category applicability;
- manufacturer validation and technical-service testing;
- false-warning/error-rate management;
- privacy and closed-loop processing expectations where carried over from the aligned European approach;
- documentation, identification and conformity-of-production evidence.

## 3. Related Indian ADAS mandates

The DMS platform may exchange context with adjacent mandated heavy-vehicle systems. These are not DMS requirements by themselves, but they influence system interfaces and driver-warning arbitration.

| Reference | Function | Programme relevance |
|---|---|---|
| AIS-162 | braking, stability and AEBS provisions for applicable heavy vehicles | driver-response and AEB escalation interface |
| AIS-186 | blind-spot information system | coordinated HMI and VRU warning strategy |
| AIS-187 | moving-off information system | coordinated HMI and driver-attention state |
| AIS-188 | lane-departure warning system | DMS-aware LDW escalation and nuisance-warning control |
| IS 11852:2019 | braking performance for applicable vehicles | vehicle dynamics and warning-response validation context |

The programme shall not infer compliance with one system from compliance with another.

## 4. Bharat NCAP / AIS-197

Bharat NCAP is a **voluntary consumer-rating programme** under CMVR Rule 126E for applicable M1 vehicles, not the same as a base DMS homologation mandate. The repository shall therefore use status `VOLUNTARY_RATING` unless an OEM programme makes the target contractual.

- Current programme: AIS-197 for eligible M1 vehicles.
- Revision path: AIS-197 (Rev. 1) has been published as a draft/revision programme and is tracked for future application.
- DMS relevance: only requirements explicitly included in the controlled protocol or customer target shall be derived; DMS shall not be claimed as Bharat NCAP-mandated without clause evidence.

## 5. Cybersecurity and software updates

| Reference | Current treatment |
|---|---|
| AIS-189 | Indian vehicle cybersecurity/CSMS reference; track notified status and applicable vehicle categories |
| AIS-190 | Indian software-update/SUMS reference; track notified status and applicable vehicle categories |
| ISO/SAE 21434 | engineering lifecycle baseline for cybersecurity work products |
| Secure boot/update requirements | mandatory by product baseline even before a specific Indian type-approval invocation |

## 6. Privacy and personal data

Where cabin imagery or derived driver data identifies or can identify a person, the programme shall assess applicability of the **Digital Personal Data Protection Act, 2023** and **Digital Personal Data Protection Rules, 2025**.

The product baseline shall implement:

- purpose limitation and data minimisation;
- local closed-loop processing by default;
- no biometric identity requirement for core DDAW/ADDW operation;
- configurable retention with raw imagery disabled by default;
- access control, encryption, audit and deletion controls;
- consent/notice and data-principal workflows for optional recording or fleet analytics;
- processor/sub-processor governance for cloud annotation and support.

## 7. India release checklist

A market release cannot be approved until the compliance owner records:

- controlled CMVR/Gazette source;
- applicable AIS edition and amendments;
- category, speed, exemption and effective-date decision;
- test-agency interpretation;
- homologation test plan and pass criteria;
- HMI language/symbol requirements;
- conformity-of-production controls;
- privacy and cybersecurity applicability;
- approved deviations and open risks.

## Public source register

- MoRTH AIS register: https://www.morth.gov.in/en/ais
- PIB heavy-commercial-vehicle mandate summary: https://www.pib.gov.in/PressReleasePage.aspx?PRID=2227148&lang=1&reg=3
- PIB ADAS effective-date summary: https://www.pib.gov.in/PressReleasePage.aspx?PRID=2223329&lang=9&reg=1
- Bharat NCAP programme summary: https://www.pib.gov.in/PressReleasePage.aspx?PRID=1950593&lang=2&reg=48
- MeitY DPDP Rules 2025: https://www.meity.gov.in/documents/act-and-policies/digital-personal-data-protection-rules-2025-gDOxUjMtQWa
