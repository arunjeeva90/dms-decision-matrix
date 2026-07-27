# 03.08 — Degraded Operation and Diagnostics Requirements

| ID | Requirement | Source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1700 | The system shall output DMS sensing availability independently from all behavioral states. | DMS-028 | Diagnostics + interface | Interface test |
| SYS-DMS-1701 | The sensing-availability state set shall include at minimum `OK`, `LIMITED`, `DEGRADED` and `UNAVAILABLE`. | Architecture | State manager | State-coverage test |
| SYS-DMS-1702 | The system shall enter `LIMITED` when one or more functions are unavailable but at least one configured mandatory DMS function remains valid. | DMS-028 normalization | State manager | Fault test |
| SYS-DMS-1703 | The system shall enter `DEGRADED` when mandatory function performance or observability is below nominal but a defined reduced-capability behaviour remains available. | Safety concept | State manager | Fault test |
| SYS-DMS-1704 | The system shall enter `UNAVAILABLE` when no valid mandatory behavioral assessment can be provided. | DMS-028 | State manager | Fault test |
| SYS-DMS-1705 | The system shall detect and debounce camera communication loss, frame freeze, frame corruption, excessive frame drop and timestamp discontinuity. | Diagnostics | Camera + platform monitor | Fault injection |
| SYS-DMS-1706 | The system shall detect and debounce complete blockage, partial blockage, severe glare, low light, NIR failure, lens contamination and camera misalignment. | DMS-028 | Image-quality diagnostics | Fault injection |
| SYS-DMS-1707 | The system shall monitor software task execution, deadline overrun, memory integrity, model load integrity and safety-monitor communication. | Functional safety | Platform diagnostics | Fault injection |
| SYS-DMS-1708 | The system shall provide a function-level degradation mask identifying which outputs remain valid. | Architecture | Interface | Interface test |
| SYS-DMS-1709 | The system shall provide a primary degradation reason and, where applicable, secondary degradation reasons. | DMS-028 | Diagnostics | Interface test |
| SYS-DMS-1710 | The system shall prevent behavioral warning escalation based on an invalid or unavailable sensing channel. | Safety concept | Safety monitor | Negative test |
| SYS-DMS-1711 | The system shall continue valid unaffected functions when another optional function becomes unavailable, subject to safety analysis. | Graceful degradation | State manager | Combination fault test |
| SYS-DMS-1712 | The system shall request the configured DMS-unavailable tell-tale or message within the allocated fault-tolerant time interval. | DMS-028 / regulation | HMI + diagnostics | Timing test |
| SYS-DMS-1713 | The system shall store diagnostic trouble information for persistent sensor, illumination, calibration, compute, communication and software-integrity faults. | Service | Diagnostics | UDS test |
| SYS-DMS-1714 | The system shall distinguish transient environmental limitation from persistent hardware or software failure. | SOTIF/safety | Diagnostics | Scenario/fault test |
| SYS-DMS-1715 | The system shall define automatic recovery criteria for each degraded reason and shall re-enter `INIT` before restoring `ACTIVE` after safety-relevant faults. | Safety concept | State manager | Recovery test |
| SYS-DMS-1716 | The system shall prevent rapid oscillation between availability states using calibrated debounce and recovery hysteresis. | Stability | State manager | Timing test |
| SYS-DMS-1717 | The system shall expose diagnostic snapshots containing privacy-minimized derived signals, software/model/calibration version and relevant fault context. | Service/privacy | Diagnostics | Audit |
| SYS-DMS-1718 | The system shall support authenticated service routines for camera/NIR, alignment, image-quality, communication and model-integrity checks. | Service architecture | Diagnostics | Security/service test |
| SYS-DMS-1719 | The system shall communicate DMS timeout and unavailable fallback expectations to each receiving vehicle function in the interface specification. | Safety integration | Vehicle interface | Inspection + integration test |
