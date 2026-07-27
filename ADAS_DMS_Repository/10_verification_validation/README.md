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
| Normal sanctioned tasks | Mirror, cluster, junction, parking/reverse |
| Drowsiness | Long blink, microsleep, nodding, PERCLOS trend, regulatory reference sleepiness level |
| Distraction | Phone ear/hand/lap, infotainment, passenger, rearward gaze, defined regulatory gaze zones |
| Availability | No response, slumped posture, face loss, driver engagement during DCAS |
| Camera health | Blocked, glare, low light, NIR fault, misalignment, timing loss |
| Diversity | Spectacles, sunglasses, masks, facial hair, head coverings, skin tones, anthropometry and seating positions |
| Vehicle context | Speed, steering, indicator, reverse, ADAS TTC risk, DCAS mode and transition state |
| Privacy/data | raw-frame disabled default, retention expiry, access/deletion, consent-gated optional logging |
| Configuration | correct market profile, prohibition of weakened mandatory behaviour, version/traceability checks |

## Evidence quality rules

Each regulatory test result shall identify:

- source regulation/AIS edition, clause and amendment;
- vehicle type, configuration, calibration, software and model versions;
- camera/lens/NIR and mounting configuration;
- driver participant/subgroup and seating position;
- environment, speed, route and lighting conditions;
- ground-truth method and synchronisation;
- objective pass/fail criteria and uncertainty;
- raw evidence location, reviewer and approval status;
- deviations, anomalies and retest rationale.

A dataset-level accuracy value alone is not homologation evidence.

See `test_catalog.csv` and `../08_regulations_compliance/05_regulatory_evidence_checklist.md`.
