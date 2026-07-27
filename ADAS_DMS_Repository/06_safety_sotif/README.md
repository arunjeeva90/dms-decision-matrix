# 06 — Functional Safety and SOTIF

## Preliminary hazards
| Hazard ID | Hazardous behavior | Example cause | Candidate safety mechanism |
|---|---|---|---|
| HAZ-DMS-001 | Driver unavailable but reported available | Eye occlusion, model error | Confidence gating, temporal plausibility |
| HAZ-DMS-002 | Unwarranted critical warning | Misclassified sanctioned glance | Context pre-filter, hysteresis |
| HAZ-DMS-003 | DMS unavailable but downstream assumes valid | Interface timeout not handled | Alive counter, validity, timeout fallback |
| HAZ-DMS-004 | Driver state delayed during urgent ADAS event | Compute overload | Deadline monitor, load shedding |
| HAZ-DMS-005 | Privacy breach of cabin data | Unauthorized storage/access | Encryption, minimization, access control |

## Candidate functional safety requirements
| ID | Requirement | Verification |
|---|---|---|
| FSR-DMS-0001 | The DMS shall communicate availability and confidence independently from behavioral state. | Interface test |
| FSR-DMS-0002 | The safety monitor shall reject stale, temporally inconsistent or integrity-failed perception outputs. | Fault injection |
| FSR-DMS-0003 | Loss of DMS communication shall cause the receiving function to enter its defined driver-state-unknown fallback. | Integration test |
| FSR-DMS-0004 | Optional AI reasoning shall not override deterministic safety arbitration. | Architecture analysis |

## SOTIF focus
- Sunglasses and NIR reflections
- Face/eye occlusion by hands, hair, scarf or mask
- Valid mirror/cluster/reverse glances
- Cabin diversity and unusual seating posture
- Night glare, dashboard reflections and phone-screen illumination
- Child/passenger confusion with driver ROI
- Long-tail phone and seatbelt misuse configurations
