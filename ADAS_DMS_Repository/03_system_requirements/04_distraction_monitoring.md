# 03.04 — Distraction Monitoring Requirements

| ID | Requirement | Scenario source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1300 | The system shall output distraction state independently from drowsiness, availability and DMS confidence. | Architecture | Decision fusion | Interface test |
| SYS-DMS-1301 | The distraction state set shall include at minimum `NONE`, `MONITOR`, `VISUAL`, `MANUAL`, `COGNITIVE_SUSPECTED`, `COMBINED` and `UNKNOWN`. | DMS-005 to DMS-022 | Decision fusion | State-coverage test |
| SYS-DMS-1302 | The system shall classify a short instrument-cluster glance as a sanctioned task when gaze region, vehicle context and duration satisfy the calibrated criteria. | DMS-009 | Sanctioned-task filter | Scenario test |
| SYS-DMS-1303 | The system shall classify a short mirror glance as a sanctioned task when the observed gaze region and duration satisfy the calibrated criteria. | DMS-017 | Sanctioned-task filter | Scenario test |
| SYS-DMS-1304 | The system shall support sanctioned-task rules for junction scan, overtake scan, reverse and parking manoeuvres when the required vehicle-context signals are valid. | DMS-017, DMS-020 | Sanctioned-task filter | HIL scenario test |
| SYS-DMS-1305 | The system shall not suppress a distraction event as sanctioned when the required vehicle-context signal is stale, missing or implausible. | Safety concept | Safety monitor | Fault injection |
| SYS-DMS-1306 | The system shall detect sustained downward visual attention outside the configured road-forward region. | DMS-010 | Gaze + fusion | ADDW scenario test |
| SYS-DMS-1307 | The system shall detect sustained side-window or passenger-region visual attention outside sanctioned-task limits. | DMS-014, DMS-018, DMS-019 | Gaze + fusion | Scenario test |
| SYS-DMS-1308 | The system shall detect rearward visual attention and shall distinguish driving-context-valid rearward observation from non-driving rearward distraction where vehicle context permits. | DMS-020 | Gaze + context | HIL scenario test |
| SYS-DMS-1309 | The system shall detect a phone-near-ear candidate using phone-object, hand and face/ear spatial relationship with temporal persistence. | DMS-005 | Perception + fusion | Scenario test |
| SYS-DMS-1310 | The system shall classify phone-near-ear as an OEM manual/cognitive distraction extension unless explicitly included by the selected regulatory profile. | DMS-005 normalization | Configuration + fusion | Inspection |
| SYS-DMS-1311 | The system shall detect phone-in-hand with road-forward gaze as a manual-distraction candidate when phone and hand confidence satisfy calibrated criteria. | DMS-006 | Perception + fusion | Scenario test |
| SYS-DMS-1312 | The system shall not classify phone-in-hand with road-forward gaze as regulatory long visual distraction unless the applicable gaze-duration criterion is also met. | DMS-006 normalization | Decision fusion | Negative test |
| SYS-DMS-1313 | The system shall detect combined visual/manual distraction when a phone or approved handheld-device cue coincides with downward or off-road gaze. | DMS-007, DMS-011 | Fusion | Scenario test |
| SYS-DMS-1314 | The system shall detect texting-posture candidates using head-down, lap/phone-zone, hand/phone and duration evidence. | DMS-011 | Fusion | Scenario test |
| SYS-DMS-1315 | The system shall classify short lateral head tilt with compensated road gaze as normal or monitor-only posture variation. | DMS-013 | Sanctioned/posture filter | Scenario test |
| SYS-DMS-1316 | The system shall classify prolonged lateral head posture as distraction only when off-road gaze or equivalent attention evidence is present. | DMS-014 | Decision fusion | Positive/negative test |
| SYS-DMS-1317 | The system shall distinguish visual distraction from manual distraction so downstream functions can apply function-specific HMI and risk fusion. | DMS-005 to DMS-011 | Interface + fusion | Interface test |
| SYS-DMS-1318 | The system shall accumulate repeated short off-road glances within a configurable rolling window. | DMS-022 | Temporal fusion | Sequence test |
| SYS-DMS-1319 | The system shall support configurable metrics for maximum single-glance duration, cumulative off-road duration, glance frequency and recovery duration. | DMS-010, DMS-018, DMS-022 | Calibration + fusion | Configuration test |
| SYS-DMS-1320 | The system shall not infer cognitive distraction from head pose or gaze alone. | DMS-005, DMS-019 normalization | Decision fusion | Negative test |
| SYS-DMS-1321 | The system shall report `COGNITIVE_SUSPECTED` only when an approved multi-cue algorithm and product profile are enabled. | OEM extension | Decision fusion | Configuration test |
| SYS-DMS-1322 | The system shall output `UNKNOWN` rather than `NONE` when gaze observability is insufficient to evaluate visual distraction. | DMS-028 | Decision fusion | Occlusion test |
| SYS-DMS-1323 | The system shall apply recovery hysteresis before clearing a distraction warning after road gaze resumes. | Temporal recovery | Decision fusion | Recovery test |
| SYS-DMS-1324 | The system shall expose dominant distraction reason codes including long-down, long-side, rearward, phone-ear, phone-hand, phone-gaze-down, cumulative-glance and unknown. | HMI/interface | Decision fusion | Interface test |
| SYS-DMS-1325 | The system shall support market-specific enablement of OEM distraction extensions without altering mandatory ADDW gaze logic. | Product/regulation separation | Configuration | Negative configuration test |
