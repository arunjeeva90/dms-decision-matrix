# 03.01 — Operating Modes and Activation Requirements

| ID | Requirement | Source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1000 | The system shall implement the mutually exclusive operating states `OFF`, `INIT`, `ACTIVE`, `LIMITED`, `DEGRADED`, `UNAVAILABLE` and `SERVICE`. | Platform architecture | State manager | State-transition test |
| SYS-DMS-1001 | The system shall enter `INIT` after each power-on, wake-up, software reset or controlled model restart. | Platform architecture | State manager | Test |
| SYS-DMS-1002 | The system shall enter `ACTIVE` only after camera communication, image quality, calibration validity, time synchronization and mandatory software-integrity checks have passed. | Safety concept | State manager + diagnostics | Fault injection |
| SYS-DMS-1003 | The system shall determine feature activation using vehicle speed, ignition/power mode, driver-seat occupancy, gear state and the selected regulatory profile. | Regulations + vehicle integration | State manager | HIL test |
| SYS-DMS-1004 | The system shall independently enable drowsiness, distraction, availability, phone, visual-belt and ADAS-fusion functions according to the configured product variant. | Product definition | Configuration manager | Configuration test |
| SYS-DMS-1005 | The system shall prevent a disabled optional feature from suppressing any mandatory function of the selected regulatory profile. | Compliance governance | Safety monitor | Negative configuration test |
| SYS-DMS-1006 | The system shall support a controlled temporary-deactivation request only where permitted by the selected regulatory profile. | AIS/EU profile | State manager + HMI | State-transition test |
| SYS-DMS-1007 | The system shall automatically reactivate a temporarily deactivated mandatory function at the next ignition cycle and under any additional reactivation conditions defined by the selected profile. | AIS/EU profile | State manager | Test |
| SYS-DMS-1008 | The system shall record the active regulatory profile, software version, model version and calibration version in diagnostic identification data. | Homologation evidence | Diagnostics | Inspection |
| SYS-DMS-1009 | The system shall distinguish `feature inactive by design`, `temporarily deactivated`, `limited`, `degraded` and `unavailable` in its output status. | HMI + safety | Interface | Interface test |
| SYS-DMS-1010 | The system shall not classify driver behaviour while no valid driver is present, except for presence-loss and availability diagnostics. | Scenario normalization | Decision fusion | Scenario test |
| SYS-DMS-1011 | The system shall reset short-term temporal evidence after a controlled driver change, seat vacancy or configured prolonged standstill, while preserving legally required diagnostic information. | Temporal logic | Decision fusion | Timing test |
| SYS-DMS-1012 | The system shall apply a defined startup inhibit interval to behavioral warnings while maintaining sensor-health and failure indication. | Nuisance prevention | Decision fusion + HMI | Timing test |
| SYS-DMS-1013 | The system shall declare its current operational design envelope using machine-readable validity flags for driver presence, face, eyes, gaze, head pose, hands/phone and torso/belt visibility. | Safety/SOTIF | Interface | Interface test |
| SYS-DMS-1014 | The system shall enter `SERVICE` mode only through authenticated diagnostic access and shall suppress customer-facing behavioral outputs while retaining required safety indications. | Cybersecurity + service | Diagnostics | Security test |
