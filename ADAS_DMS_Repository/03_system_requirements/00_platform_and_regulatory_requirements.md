# 03.00 — Platform and Regulatory System Requirements

This module preserves the platform-level and regulatory-profile requirements. Detailed behavioral requirements are decomposed in the following modules.

## Platform requirements

| ID | Requirement | Parent | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-0001 | The system shall determine whether a valid driver is present in the configured driver seating region at a nominal update rate of at least 15 Hz. | STK-DMS-0002 | Perception | Test |
| SYS-DMS-0002 | The system shall output drowsiness, distraction, driver availability and DMS confidence as independent state variables. | STK-DMS-0004 | Decision fusion | Interface test |
| SYS-DMS-0003 | The system shall classify driver risk using head pose, eye state, gaze zone, hand/phone cues, duration, vehicle context and sensing confidence. | STK-DMS-0003 | Decision fusion | Scenario test |
| SYS-DMS-0004 | The system shall apply a sanctioned-task pre-filter before issuing distraction warnings. | STK-DMS-0003 | Decision fusion | Scenario test |
| SYS-DMS-0005 | The system shall implement configurable persistence, cumulative-event and recovery hysteresis for each warning class. | STK-DMS-0003 | Decision fusion | Timing test |
| SYS-DMS-0006 | The system shall detect camera blocked, severe glare, low-light, NIR failure, face loss and camera misalignment conditions. | STK-DMS-0005 | Diagnostics | Fault injection |
| SYS-DMS-0007 | The system shall prevent a critical driver-state assertion based solely on low-confidence perception. | STK-DMS-0005 | Safety monitor | Safety test |
| SYS-DMS-0008 | The system shall provide an end-to-end sensor-to-output latency budget suitable for the allocated vehicle function, with the platform target not exceeding 100 ms at nominal load. | STK-DMS-0001 | Platform | Measurement |
| SYS-DMS-0009 | The system shall support 30 fps nominal camera acquisition and a defined degraded mode at 15 fps or lower. | STK-DMS-0002 | Camera/compute | Test |
| SYS-DMS-0010 | The system shall expose reason codes for primary driver risk and DMS degradation. | STK-DMS-0004 | Interface | Interface test |
| SYS-DMS-0011 | The system shall preserve deterministic safety decision behavior independently of optional generative or VLM functions. | STK-DMS-0008 | Safety architecture | Analysis |
| SYS-DMS-0012 | The system shall support secure, authenticated and rollback-capable software and model updates. | STK-DMS-0007 | Platform security | Penetration/update test |
| SYS-DMS-0013 | The system shall not retain raw cabin imagery in production unless explicitly enabled by an approved privacy and consent configuration. | STK-DMS-0007 | Data platform | Audit |
| SYS-DMS-0014 | The system shall support configurable market and vehicle calibration datasets without source-code modification. | STK-DMS-0001 | Calibration | Configuration test |
| SYS-DMS-0015 | The system shall timestamp camera frames, vehicle signals and output states using a common synchronized timebase. | STK-DMS-0008 | Interfaces | Timing test |

## Regulatory-profile requirements

Exact thresholds and clauses shall be populated from the approved controlled market-specific regulation profile.

| ID | Requirement | Regulatory source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-0100 | The system shall select a controlled regulatory profile using market, vehicle category, model status, effective date and fitted vehicle functions. | CMVR/EU/UNECE applicability | Configuration management | Inspection + configuration test |
| SYS-DMS-0101 | For an applicable India AIS-184 profile, the system shall assess driver drowsiness/attention and issue the required warning under the specified activation and operating conditions. | CMVR Rule 125Q / AIS-184 | Decision fusion + HMI | Homologation scenario test |
| SYS-DMS-0102 | For an applicable India AIS-184 profile, the system shall implement the controlled deactivation, automatic reactivation, failure indication and driver-information behaviour. | AIS-184 | HMI + diagnostics | State-transition test |
| SYS-DMS-0103 | The India AIS-184 release shall include traceable manufacturer validation evidence for applicable speed, road, day/night, driver and system-error conditions. | AIS-184 | V&V | Evidence review + vehicle test |
| SYS-DMS-0104 | For the EU DDAW profile, the system shall monitor driver drowsiness and provide an HMI warning at or before the applicable regulatory drowsiness threshold. | EU 2021/1341 | Decision fusion + HMI | Regulatory validation |
| SYS-DMS-0105 | The EU DDAW profile shall operate during day and night within the regulatory environmental and vehicle operating scope. | EU 2021/1341 | Camera + perception | Vehicle test |
| SYS-DMS-0106 | The EU DDAW profile shall perform core operation without requiring biometric identity or facial-recognition enrolment and shall retain only data necessary for closed-loop operation. | EU 2021/1341 | Perception + privacy | Inspection + privacy audit |
| SYS-DMS-0107 | For the EU ADDW profile, the system shall detect long visual distraction using the defined regulatory gaze regions, timing criteria and vehicle operating conditions. | EU 2023/2590 | Perception + decision fusion | Regulatory scenario test |
| SYS-DMS-0108 | The EU ADDW profile shall support the required range of driver characteristics and seating positions and shall provide traceable subgroup evidence. | EU 2023/2590 | Data/ML + V&V | Dataset audit + vehicle test |
| SYS-DMS-0109 | The EU ADDW profile shall implement the applicable activation, temporary-deactivation, automatic-reactivation, warning and failure behaviour. | EU 2023/2590 | HMI + diagnostics | State-transition test |
| SYS-DMS-0110 | When integrated with a DCAS subject to UN R171, the system shall provide driver-engagement, availability, warning and transition inputs with freshness, validity and integrity protection. | UN R171 selected series | Decision fusion + vehicle interface | Integration + type-approval test |
| SYS-DMS-0111 | The system shall maintain a SOTIF triggering-condition catalogue covering driver diversity, occlusion, illumination, eyewear, posture, sanctioned glances and foreseeable misuse. | ISO 21448 | SOTIF + data/ML | Analysis + scenario coverage review |
| SYS-DMS-0112 | Any market/customer overlay shall be prevented from weakening a legally mandatory warning, activation, privacy, failure or data-integrity behaviour. | Compliance governance | Configuration + safety monitor | Negative configuration test |
