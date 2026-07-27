# 03.03 — Drowsiness Monitoring Requirements

| ID | Requirement | Scenario source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1200 | The system shall output a drowsiness state independently from distraction, availability and DMS confidence. | Architecture | Decision fusion | Interface test |
| SYS-DMS-1201 | The drowsiness state set shall include at minimum `NORMAL`, `MONITOR`, `DROWSY_WARNING`, `SEVERE_DROWSY`, `MICROSLEEP` and `UNKNOWN`. | DMS-001 to DMS-024 | Decision fusion | State-coverage test |
| SYS-DMS-1202 | The system shall identify a normal blink when eye closure duration is below the calibrated blink threshold and shall not issue a drowsiness warning for that event alone. | DMS-002 | Eye-state + fusion | Timing test |
| SYS-DMS-1203 | The system shall distinguish prolonged eye closure from a normal blink using calibrated closure-duration and confidence criteria. | DMS-002, DMS-004 | Decision fusion | Timing test |
| SYS-DMS-1204 | The system shall detect a slow-eyelid-closure trend using closure and reopening dynamics over a configurable temporal window. | DMS-003, DMS-015 | Perception + fusion | Recorded-sequence test |
| SYS-DMS-1205 | The system shall calculate PERCLOS or an approved equivalent eyelid-closure metric over controlled short and long temporal windows. | DMS-003 | Decision fusion | Algorithm test |
| SYS-DMS-1206 | The system shall expose the validity and confidence of each PERCLOS or equivalent metric. | Safety/SOTIF | Interface | Interface test |
| SYS-DMS-1207 | The system shall detect a microsleep candidate when prolonged eye closure exceeds the calibrated threshold with valid eye observability. | DMS-004 | Decision fusion | Scenario test |
| SYS-DMS-1208 | The system shall detect repeated head-nod cycles using head-pitch trajectory, eye dynamics and recovery behaviour. | DMS-012, DMS-023 | Temporal fusion | Sequence test |
| SYS-DMS-1209 | The system shall classify head-down posture as drowsiness only when supported by eye-closure, head-nod, eyelid-dynamics or other approved fatigue evidence. | DMS-012 | Decision fusion | Negative/positive test |
| SYS-DMS-1210 | The system shall classify lateral head drop with closed eyes as a severe drowsiness candidate when eye and head-pose confidence satisfy the calibrated criteria. | DMS-016 | Decision fusion | Scenario test |
| SYS-DMS-1211 | The system shall classify head turn with closed eyes as a severe drowsiness candidate only after excluding transient blink and sensing-invalid conditions. | DMS-021 | Decision fusion | Scenario test |
| SYS-DMS-1212 | The system shall treat yawn detection as a supporting fatigue cue and shall not issue a critical drowsiness state based on a yawn alone. | DMS-024 | Decision fusion | Negative test |
| SYS-DMS-1213 | The system shall combine yawn, slow blink, blink-rate change and eyelid-closure trend as configurable cumulative evidence. | DMS-024 | Temporal fusion | Sequence test |
| SYS-DMS-1214 | The system shall treat reduced saccade or fixed-stare behaviour as a supporting cue only and shall not issue a drowsiness warning from fixed stare alone. | DMS-008 | Decision fusion | Negative test |
| SYS-DMS-1215 | The system shall require temporal persistence or multi-cue confirmation before escalating from drowsiness `MONITOR` to `DROWSY_WARNING`. | DMS-003, DMS-008 | Temporal fusion | Timing test |
| SYS-DMS-1216 | The system shall support independent warning thresholds for early drowsiness, severe drowsiness and microsleep according to the selected market profile. | AIS-184 / DDAW | Calibration + fusion | Configuration test |
| SYS-DMS-1217 | The system shall downgrade drowsiness confidence or output `UNKNOWN` when both eyes are not sufficiently observable for the selected algorithm. | DMS-028 | Perception + fusion | Occlusion test |
| SYS-DMS-1218 | The system shall avoid resetting accumulated drowsiness evidence due to a single valid blink or short sanctioned glance. | DMS-002, DMS-009 | Temporal fusion | Sequence test |
| SYS-DMS-1219 | The system shall implement a calibrated recovery condition requiring sustained valid eye opening and recovered alertness evidence before clearing a drowsiness warning. | Temporal recovery | Decision fusion | Recovery test |
| SYS-DMS-1220 | The system shall provide a drowsiness reason code that identifies the dominant evidence family without exposing raw biometric imagery. | HMI/interface | Decision fusion | Interface test |
