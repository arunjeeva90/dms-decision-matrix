# 03.05 — Driver Availability and Responsiveness Requirements

| ID | Requirement | Scenario source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1400 | The system shall output driver availability independently from drowsiness, distraction and DMS confidence. | Architecture | Decision fusion | Interface test |
| SYS-DMS-1401 | The driver-availability state set shall include at minimum `AVAILABLE`, `PARTIALLY_AVAILABLE`, `UNAVAILABLE`, `UNCONFIRMED` and `NOT_APPLICABLE`. | DMS-025, DMS-029 | Decision fusion | State-coverage test |
| SYS-DMS-1402 | The system shall determine availability using valid driver presence, gaze/attention evidence, posture, response to warning and applicable vehicle context. | DMS-025, DMS-029 | Decision fusion | Scenario test |
| SYS-DMS-1403 | The system shall not classify the driver as available solely because a face is detected. | Safety concept | Decision fusion | Negative test |
| SYS-DMS-1404 | The system shall monitor for attention recovery following a DMS or ADAS warning when the selected product profile requires responsiveness assessment. | DMS-025 | Temporal fusion | HIL scenario test |
| SYS-DMS-1405 | The system shall classify the driver as `PARTIALLY_AVAILABLE` when attention is impaired but recoverable within the configured response window. | DMS-025 | Decision fusion | Timing test |
| SYS-DMS-1406 | The system shall classify the driver as `UNAVAILABLE` only after the configured non-response criteria, confidence criteria and temporal confirmation are satisfied. | DMS-025 | Safety monitor + fusion | Timing/fault test |
| SYS-DMS-1407 | The system shall distinguish `driver unavailable` from `DMS unable to assess driver availability`. | DMS-028 normalization | Interface | Interface test |
| SYS-DMS-1408 | The system shall report `UNCONFIRMED` when sensing confidence is insufficient to determine driver availability. | DMS-028 | Decision fusion | Occlusion test |
| SYS-DMS-1409 | The system shall detect abnormal sustained posture or motionlessness as an availability cue only when the configured camera coverage and posture model are valid. | DMS-029 | Perception + fusion | Scenario test |
| SYS-DMS-1410 | The system shall describe DMS-029 as `driver unresponsiveness or possible incapacitation` and shall not diagnose a medical condition. | DMS-029 normalization | HMI + diagnostics | Inspection |
| SYS-DMS-1411 | The system shall require multi-cue confirmation before issuing a possible-incapacitation output, including valid driver presence and at least one approved responsiveness or abnormal-posture cue. | DMS-029 | Decision fusion | Positive/negative test |
| SYS-DMS-1412 | The system shall support a configurable external driver-response input, such as steering interaction, button acknowledgement or pedal activity, when provided by the vehicle architecture. | DCAS/OEM safety concept | Vehicle interface | HIL test |
| SYS-DMS-1413 | The system shall validate freshness and plausibility of external driver-response signals before using them to restore availability. | Safety concept | Safety monitor | Fault injection |
| SYS-DMS-1414 | The system shall provide availability reason codes including attentive, distracted-recoverable, no-response, abnormal-posture, driver-not-present, sensing-insufficient and interface-invalid. | HMI/interface | Decision fusion | Interface test |
| SYS-DMS-1415 | The system shall maintain availability-state hysteresis to prevent oscillation between available and unavailable during intermittent gaze or face loss. | Temporal stability | Decision fusion | Sequence test |
| SYS-DMS-1416 | The system shall clear an unavailable state only after the configured recovery evidence has remained valid for the required recovery duration. | DMS-025 recovery | Decision fusion | Recovery test |
