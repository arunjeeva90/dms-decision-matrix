# 11 — Data and AI Lifecycle

| ID | Requirement | Verification |
|---|---|---|
| DAT-DMS-0001 | Dataset splits shall be separated by driver identity, vehicle/cabin and recording session to prevent leakage. | Audit |
| DAT-DMS-0002 | Dataset coverage shall be reported by driver diversity, eyewear, illumination, occlusion, pose, vehicle and scenario. | Coverage report |
| DAT-DMS-0003 | Annotation guidelines shall define ambiguous, unknown and low-quality labels. | Inspection |
| DAT-DMS-0004 | Every released model shall have immutable dataset, code, configuration, calibration and metric lineage. | Release audit |
| DAT-DMS-0005 | Performance shall be reported per safety-relevant subgroup and scenario, not only aggregate accuracy. | Metric review |
| DAT-DMS-0006 | Active-learning collection shall prioritize false negatives, nuisance warnings and low-confidence edge cases. | Pipeline audit |
| DAT-DMS-0007 | Synthetic data shall be tagged and evaluated separately from real-world validation data. | Dataset audit |
