# 03 — DMS System Requirements Specification

## Purpose

This folder is the system-requirements baseline between stakeholder needs and subsystem/HW/SW allocation. It follows a DOORS-style modular decomposition and contains **220 atomic system requirements** plus explicit mapping of all 29 scenarios from the live DMS decision matrix.

## Requirement modules

| Module | ID range | Scope |
|---|---:|---|
| [Platform and regulatory](00_platform_and_regulatory_requirements.md) | 0001–0112 | Platform contract and market profiles |
| [Operating modes and activation](01_operating_modes_and_activation.md) | 1000–1014 | State management, activation and configuration |
| [Sensing quality and driver geometry](02_sensing_quality_and_driver_geometry.md) | 1100–1118 | Presence, face, eye, gaze, head, phone, observability |
| [Drowsiness monitoring](03_drowsiness_monitoring.md) | 1200–1220 | Blink, closure, PERCLOS, microsleep, nodding, fatigue cues |
| [Distraction monitoring](04_distraction_monitoring.md) | 1300–1325 | Gaze, sanctioned tasks, phone, visual/manual/cognitive outputs |
| [Driver availability](05_driver_availability_and_responsiveness.md) | 1400–1416 | Responsiveness, availability and possible incapacitation |
| [Temporal arbitration and HMI](06_temporal_arbitration_and_hmi.md) | 1500–1520 | Persistence, hysteresis, arbitration and warning requests |
| [ADAS fusion](07_adas_fusion_and_driver_aware_escalation.md) | 1600–1616 | FCW/LDW/DCAS driver-aware escalation and interface contract |
| [Degraded operation and diagnostics](08_degraded_operation_and_diagnostics.md) | 1700–1719 | Limited/degraded/unavailable, faults, DTC and recovery |
| [Configuration and calibration](09_configuration_and_calibration.md) | 1800–1814 | Vehicle, market and camera calibration governance |
| [Performance and non-functional](10_performance_and_nonfunctional.md) | 1900–1920 | Latency, update rate, diversity, robustness and resources |
| [Scenario review and normalization](11_scenario_review_and_normalization.md) | — | Senior engineering disposition of DMS-001…DMS-029 |
| [Scenario mapping CSV](scenario_requirement_mapping.csv) | — | Scenario → requirement → verification traceability |

## Independent system outputs

The system shall not collapse all observations into one label. It exposes:

```text
Drowsiness State
Distraction State
Driver Availability State
DMS Sensing Availability / Confidence
HMI Request
ADAS Driver-Aware Escalation Request
```

Behavioral severity is represented as:

```text
NORMAL → MONITOR → WARNING → DANGER → CRITICAL
```

Sensing/system availability is represented separately as:

```text
OK → LIMITED → DEGRADED → UNAVAILABLE
```

## Scenario coverage conclusion

All live-page scenarios `DMS-001` through `DMS-029` are considered. They are not copied as one-line requirements; each is decomposed into sensing, context, temporal, decision, HMI, interface, safety, degraded and verification obligations.

Important normalized decisions:

- normal blink, cluster glance, mirror check and compensated posture shall not create nuisance warnings;
- head pose alone shall not determine distraction or drowsiness;
- fixed stare and yawning are supporting cues only;
- phone-manual distraction is separated from regulatory long visual distraction;
- camera blocked produces `DMS_UNAVAILABLE`, not `critical driver risk`;
- possible incapacitation means unresponsiveness assessment, not medical diagnosis;
- DMS may request driver-aware escalation but shall not command steering or braking by itself.

## Requirement quality gate

Every requirement shall be reviewed for:

1. atomic “shall” obligation;
2. defined preconditions and output;
3. measurable acceptance criterion or calibration reference;
4. parent/source and subsystem allocation;
5. safety, SOTIF, regulatory, privacy and cybersecurity impact;
6. linked verification case;
7. positive, negative, boundary, degraded and recovery coverage.
