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

## Scenario families
| Family | Examples |
|---|---|
| Normal sanctioned tasks | Mirror, cluster, junction, parking/reverse |
| Drowsiness | Long blink, microsleep, nodding, PERCLOS trend |
| Distraction | Phone ear/hand/lap, infotainment, passenger, rearward gaze |
| Availability | No response, slumped posture, face loss |
| Camera health | Blocked, glare, low light, NIR fault, misalignment |
| Diversity | Spectacles, sunglasses, masks, facial hair, head coverings |
| Vehicle context | Speed, steering, indicator, reverse, ADAS TTC risk |

See `test_catalog.csv`.
