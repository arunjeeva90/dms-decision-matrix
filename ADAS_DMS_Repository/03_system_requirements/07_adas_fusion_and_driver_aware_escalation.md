# 03.07 — ADAS Fusion and Driver-Aware Escalation Requirements

| ID | Requirement | Scenario source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1600 | The system shall provide drowsiness, distraction, availability, confidence, validity and reason codes to authorized ADAS functions through a versioned interface. | DualSight architecture | Vehicle interface | Interface test |
| SYS-DMS-1601 | The DMS-to-ADAS interface shall include timestamp, age, alive counter and end-to-end integrity protection for safety-relevant outputs. | Safety concept | Vehicle interface | Bus/fault test |
| SYS-DMS-1602 | The system shall receive forward-risk inputs only from an authenticated and configured ADAS source. | DMS-026, DMS-027 | Vehicle interface | Security/integration test |
| SYS-DMS-1603 | The system shall validate freshness, validity, confidence and plausibility of ADAS risk inputs before applying driver-aware escalation. | Safety concept | Safety monitor | Fault injection |
| SYS-DMS-1604 | The system shall support driver-aware escalation for forward-collision risk when the driver is distracted, drowsy or unavailable and the external risk input is valid. | DMS-026 | Fusion | HIL scenario test |
| SYS-DMS-1605 | The system shall support driver-aware escalation for lane-departure risk when the driver has valid off-road visual attention or is unavailable. | DMS-027 | Fusion | HIL scenario test |
| SYS-DMS-1606 | The system shall not independently command vehicle braking or steering solely from a DMS behavioral classification. | Safety boundary | Safety monitor | Architecture analysis |
| SYS-DMS-1607 | The system shall output a driver-aware escalation request that is distinct from the original ADAS warning or intervention request. | Architecture | Vehicle interface | Interface test |
| SYS-DMS-1608 | The system shall not de-escalate a valid external ADAS safety request because the driver appears attentive. | Safety concept | Fusion | Negative test |
| SYS-DMS-1609 | The system shall inhibit driver-aware escalation when DMS confidence is insufficient and shall provide `driver_state_unknown` to the receiving ADAS function. | DMS-028 | Fusion | Occlusion/fault test |
| SYS-DMS-1610 | The system shall support configurable driver-aware risk policies by ADAS function, including FCW, LDW, LKA/ELK, ACC, AEB, DCAS and minimum-risk transition where fitted. | Product variants | Configuration + fusion | Configuration test |
| SYS-DMS-1611 | The system shall preserve the independent original DMS states when creating a combined driver-aware ADAS risk. | Architecture | Fusion | Interface test |
| SYS-DMS-1612 | The system shall log the DMS state, ADAS risk input, escalation decision and output validity for each driver-aware escalation event. | Safety evidence | Diagnostics | Log audit |
| SYS-DMS-1613 | The system shall prevent stale or replayed ADAS risk messages from generating a new driver-aware escalation. | Cybersecurity/safety | Safety monitor | Replay/fault test |
| SYS-DMS-1614 | The system shall support a receiving-function timeout contract that defines ADAS fallback when DMS output is unavailable. | DMS-028 / safety | Interface | Integration test |
| SYS-DMS-1615 | The system shall provide a configurable response-monitoring window after a valid takeover or urgent warning request when the fitted function requires driver response assessment. | DMS-025 / R171 | Fusion | HIL timing test |
| SYS-DMS-1616 | The system shall distinguish `driver did not respond` from `response could not be observed` in all ADAS handoff outputs. | DMS-025, DMS-028 | Fusion | Interface test |
