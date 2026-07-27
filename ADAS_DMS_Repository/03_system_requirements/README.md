# 03 — System Requirements

## Core system requirements
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

## Driver-state ladder
`NORMAL → MONITOR → WARNING → DANGER → CRITICAL`, with `LIMITED / DEGRADED / UNAVAILABLE` represented separately as system confidence/availability states rather than mixed with behavioral risk.
