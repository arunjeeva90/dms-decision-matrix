# 03.06 — Temporal Decision, Arbitration and HMI Requirements

| ID | Requirement | Scenario source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1500 | The system shall process behavioral evidence using calibrated persistence, debounce, cumulative-event and recovery timers. | DMS-002 to DMS-025 | Decision fusion | Timing test |
| SYS-DMS-1501 | The system shall maintain independent temporal evidence for drowsiness, distraction, availability and DMS confidence. | Architecture | Temporal fusion | Interface/sequence test |
| SYS-DMS-1502 | The system shall preserve evidence timestamps and source validity for each state transition. | Safety traceability | Temporal fusion | Log inspection |
| SYS-DMS-1503 | The system shall prevent a single-frame behavioral detection from directly producing a danger or critical state unless an approved emergency exception is defined and verified. | Safety/SOTIF | Safety monitor | Fault injection |
| SYS-DMS-1504 | The system shall arbitrate simultaneous drowsiness and distraction states without discarding either independent state. | DMS-007, DMS-012 | Decision fusion | Combination test |
| SYS-DMS-1505 | The system shall calculate a final HMI request from behavioral severity, confidence, persistence, vehicle context, selected regulatory profile and current HMI escalation stage. | Decision architecture | HMI arbiter | Scenario test |
| SYS-DMS-1506 | The system shall keep behavioral severity and sensing availability as separate output dimensions. | DMS-028 normalization | Interface | Interface test |
| SYS-DMS-1507 | The system shall not use `DEGRADED` or `UNAVAILABLE` as a behavioral-risk level. | DMS-028 normalization | Decision fusion | Negative test |
| SYS-DMS-1508 | The system shall support at minimum HMI requests `NONE`, `INFORMATION`, `WARNING_STAGE_1`, `WARNING_STAGE_2`, `URGENT`, `TAKEOVER` and `SYSTEM_UNAVAILABLE`, subject to product profile. | DMS-001 to DMS-029 | HMI manager | Interface test |
| SYS-DMS-1509 | The system shall map regulatory-mandated warning behaviour independently from OEM comfort or coaching notifications. | Regulation/OEM separation | HMI manager | Configuration inspection |
| SYS-DMS-1510 | The system shall suppress audible warnings for valid normal blink, attentive baseline, short cluster glance, short mirror check and short compensated posture variation. | DMS-001, 002, 009, 013, 017 | HMI arbiter | Scenario test |
| SYS-DMS-1511 | The system shall support warning escalation when the triggering condition persists or worsens after the initial warning. | DMS-007, 011, 023, 025 | HMI arbiter | Timing test |
| SYS-DMS-1512 | The system shall support de-escalation only after the configured recovery criteria are satisfied. | Recovery logic | HMI arbiter | Recovery test |
| SYS-DMS-1513 | The system shall prevent repeated warning chattering by applying minimum on-time, minimum off-time and re-alert criteria. | HMI quality | HMI manager | Timing test |
| SYS-DMS-1514 | The system shall output the primary and secondary reason codes when multiple driver-state risks coexist. | Combined scenarios | Interface | Interface test |
| SYS-DMS-1515 | The system shall identify whether an HMI request originated from regulatory drowsiness, regulatory distraction, OEM extension, ADAS fusion, availability or system-failure logic. | Compliance traceability | Interface | Interface test |
| SYS-DMS-1516 | The system shall allow vehicle-specific HMI realization to be external while retaining ownership of DMS warning request, urgency, reason and validity. | Architecture | HMI interface | Integration test |
| SYS-DMS-1517 | The system shall receive HMI acknowledgement/status where required and shall detect missing or implausible acknowledgement. | Safety architecture | HMI interface | HIL/fault test |
| SYS-DMS-1518 | The system shall log state transitions, warnings and recovery events using privacy-minimized derived data for engineering and homologation evidence. | Evidence/privacy | Diagnostics | Audit |
| SYS-DMS-1519 | The system shall use calibrated speed-dependent or function-dependent thresholds only when allowed by the selected regulatory profile. | Regulations | Calibration + fusion | Configuration test |
| SYS-DMS-1520 | The system shall provide deterministic conflict resolution when regulatory and OEM-extension HMI requests occur simultaneously, with regulatory mandatory behaviour taking precedence. | Compliance governance | HMI arbiter | Combination test |
