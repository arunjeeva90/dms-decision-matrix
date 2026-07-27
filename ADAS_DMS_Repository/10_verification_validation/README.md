# 10 — Verification and Validation

## V-model coverage
- Requirement inspection and quality checks
- MIL/SIL algorithm tests
- Recorded-video regression
- Processor-in-loop and target profiling
- HIL with vehicle-signal manipulation
- Cabin rig testing across seating/lighting/occlusion
- Vehicle testing across road, driver and environment matrices
- Fault injection and degraded-mode validation
- Cybersecurity and OTA tests
- Homologation-specific evidence packs

## Test catalogues

- [`test_catalog.csv`](test_catalog.csv): platform, safety and regulatory-profile tests.
- [`scenario_test_catalog.csv`](scenario_test_catalog.csv): explicit verification of live scenarios `DMS-001` through `DMS-029`.

Every scenario verification shall include, where applicable:

1. positive detection/classification;
2. negative and confusing-neighbour cases;
3. threshold boundary and timing tolerance;
4. valid and invalid confidence/observability;
5. sanctioned-task context;
6. persistence, escalation and recovery;
7. HMI request, reason code and interface validity;
8. degraded sensing and fallback;
9. subgroup/diversity coverage;
10. market-profile and calibration configuration.

## Regulatory validation streams

| Stream | Primary source | Required evidence pattern |
|---|---|---|
| India heavy-vehicle DDAW | CMVR Rule 125Q + controlled AIS-184 edition | applicability decision, manufacturer validation, technical-service test, HMI/failure evidence, conformity-of-production controls |
| EU DDAW | EU 2021/1341 | regulatory drowsiness reference method, day/night and road conditions, warning evidence, error-rate evidence, privacy/data-retention inspection |
| EU ADDW | EU 2023/2590 | gaze-region/timing ground truth, seating/driver diversity, warning and failure behaviour, technical-service validation |
| UNECE DCAS | selected UN R171 series/supplement | driver engagement/availability interface, transition/warning tests, stale/invalid input handling, vehicle-level type-approval evidence |
| Bharat NCAP | controlled AIS-197 protocol | voluntary/contractual rating evidence only for explicitly applicable clauses |
| Cybersecurity/update | UN R155/R156, AIS-189/AIS-190 or customer baseline | CSMS/SUMS linkage, TARA, secure update, rollback, compatibility and incident-response evidence |

## Scenario families
| Family | Examples |
|---|---|
| Normal sanctioned tasks | Attentive baseline, blink, mirror, cluster, junction, parking/reverse, compensated posture |
| Drowsiness | Slow closure, long closure, microsleep, head nod, PERCLOS, lateral head drop, yawn plus slow blink |
| Distraction | Long down/side gaze, phone ear/hand/lap, texting posture, passenger gaze, rearward gaze, cumulative short glances |
| Availability | No response after warning, abnormal posture, possible incapacitation, face loss |
| ADAS fusion | TTC/FCW risk plus inattention, lane-departure risk plus off-road gaze, DCAS handoff |
| Camera health | Blocked, partial blockage, glare, low light, NIR fault, misalignment, timing loss |
| Diversity | Spectacles, sunglasses, masks, facial hair, head coverings, skin tones, anthropometry and seating positions |
| Vehicle context | Speed, steering, indicator, reverse, ADAS risk, DCAS mode and transition state |
| Privacy/data | raw-frame disabled default, retention expiry, access/deletion, consent-gated optional logging |
| Configuration | correct market profile, prohibition of weakened mandatory behaviour, version/traceability checks |

## Evidence quality rules

Each test result shall identify:

- requirement IDs and scenario IDs;
- source regulation/AIS edition, clause and amendment where applicable;
- vehicle type, configuration, calibration, software and model versions;
- camera/lens/NIR and mounting configuration;
- driver participant/subgroup and seating position;
- environment, speed, route and lighting conditions;
- ground-truth method and synchronisation;
- objective pass/fail criteria and uncertainty;
- raw evidence location, reviewer and approval status;
- deviations, anomalies and retest rationale.

A dataset-level accuracy value alone is not homologation or system-validation evidence.
