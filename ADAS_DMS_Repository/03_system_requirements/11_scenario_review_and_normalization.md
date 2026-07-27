# 03.11 — Live Decision-Matrix Scenario Review and Normalization

## Review conclusion

All 29 scenarios from the live `dms-decision-matrix` are retained as use cases, but they are normalized into independent output dimensions:

1. **Drowsiness state**
2. **Distraction state**
3. **Driver availability state**
4. **DMS sensing availability/confidence**
5. **HMI request**
6. **ADAS driver-aware escalation request**

A scenario is not itself a single requirement. Each scenario decomposes into perception, context, temporal, decision, HMI, interface, degraded and verification requirements.

## Architectural corrections

- `DEGRADED/UNAVAILABLE` is a sensing/system-availability axis, not a driver-risk severity.
- Fixed stare and yawning are supporting cues, not standalone critical decisions.
- Head pose alone shall not determine distraction or drowsiness.
- Phone-in-hand with road gaze is an OEM manual-distraction extension, not automatically regulatory long visual distraction.
- `Medical event` is replaced by **driver unresponsiveness / possible incapacitation**; the DMS shall not diagnose.
- Backward look must use reverse/parking/junction context before warning.
- ADAS fusion may request earlier/stronger warning but DMS alone shall not command steering or braking.

## Scenario disposition

| Scenario | Normalized engineering interpretation | Primary requirement modules | Disposition |
|---|---|---|---|
| DMS-001 Attentive baseline | Valid driver, road gaze, no behavioral risk | 1100, 1200, 1300, 1500 | Accepted |
| DMS-002 Normal blink | Blink suppression and closure-duration discrimination | 1202, 1203, 1510 | Accepted |
| DMS-003 Slow eyelid closure | Early drowsiness from temporal eyelid dynamics/PERCLOS | 1204, 1205, 1215 | Accepted |
| DMS-004 Microsleep | Prolonged closure with valid eye observability | 1203, 1207, 1503 | Accepted |
| DMS-005 Phone on ear | Manual/cognitive-suspected OEM extension | 1309, 1310, 1321 | Accepted with regulatory reclassification |
| DMS-006 Phone in hand + road gaze | Manual distraction; not ADDW unless gaze criteria met | 1311, 1312, 1317 | Accepted with correction |
| DMS-007 Phone + gaze down | Combined visual/manual distraction | 1313, 1504, 1511 | Accepted |
| DMS-008 Fixed stare | Secondary drowsiness/inattention evidence only | 1214, 1215 | Accepted with false-positive guard |
| DMS-009 Short cluster glance | Sanctioned driving task | 1302, 1510 | Accepted |
| DMS-010 Sustained head-down task | Long visual distraction based on gaze/duration | 1306, 1319 | Accepted |
| DMS-011 Texting posture | Multi-cue combined distraction | 1313, 1314, 1511 | Accepted |
| DMS-012 Head-down drowsiness | Drowsiness only with eye/nod evidence | 1208, 1209 | Accepted with correction |
| DMS-013 Short posture variation | Monitor or normal when gaze remains road-forward | 1315, 1510 | Accepted |
| DMS-014 Prolonged side posture | Distraction only with off-road attention evidence | 1307, 1316 | Accepted with correction |
| DMS-015 Tilt + slow closure | Early drowsiness temporal evidence | 1204, 1215 | Accepted |
| DMS-016 Tilt + closed eyes | Severe drowsiness after blink/validity exclusion | 1210, 1217 | Accepted |
| DMS-017 Mirror check | Sanctioned task within calibrated duration | 1303, 1510 | Accepted |
| DMS-018 Prolonged side gaze | Long visual distraction | 1307, 1319 | Accepted |
| DMS-019 Passenger conversation | Visual distraction if sustained; cognitive only with approved multi-cue logic | 1307, 1320, 1321 | Accepted with correction |
| DMS-020 Backward look | Context-dependent rearward attention; suppress in valid reverse/parking use | 1304, 1308 | Accepted with context requirement |
| DMS-021 Side turn + closed eyes | Severe drowsiness after transient-blink exclusion | 1211, 1217 | Accepted |
| DMS-022 Cumulative short glances | Rolling-window visual-distraction evidence | 1318, 1319, 1500 | Accepted |
| DMS-023 Repeated micro-nods | Progressive drowsiness with sequence confirmation | 1208, 1215, 1511 | Accepted |
| DMS-024 Yawning + slow blink | Cumulative fatigue; yawn cannot independently trigger critical state | 1212, 1213 | Accepted with false-positive guard |
| DMS-025 Driver ignores warning | Responsiveness monitoring and availability transition | 1404 to 1407, 1615 | Accepted |
| DMS-026 TTC risk + distracted | Validated driver-aware FCW escalation request | 1602 to 1609 | Accepted |
| DMS-027 Lane departure + off-road gaze | Validated driver-aware LDW escalation request | 1602, 1603, 1605 | Accepted |
| DMS-028 Camera blocked | DMS availability failure, not behavioral critical state | 1700 to 1719, 1609 | Accepted with axis separation |
| DMS-029 Medical-event suspicion | Driver unresponsiveness/possible incapacitation; no medical diagnosis | 1409 to 1411, 1615 | Accepted with terminology correction |

## Requirement interpretation rule

For every scenario, verification shall demonstrate:

- positive detection or classification under defined preconditions;
- negative cases and sanctioned-task suppression;
- confidence/validity behavior;
- temporal persistence and recovery;
- HMI output and reason code;
- degraded sensing behavior;
- applicable market-profile behavior;
- traceability to objective pass criteria.
