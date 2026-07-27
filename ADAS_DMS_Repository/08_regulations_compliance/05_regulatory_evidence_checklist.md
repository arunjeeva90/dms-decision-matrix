# Regulatory Evidence Checklist

## A. Applicability and source control

- [ ] Market, vehicle category and type-approval route identified
- [ ] New-type/new-model/existing-model status documented
- [ ] Effective dates checked against SOP and homologation dates
- [ ] Controlled regulation/AIS text and all amendments stored in approved document system
- [ ] Clause-level applicability reviewed by homologation/legal
- [ ] Exemptions and non-applicable clauses approved with rationale
- [ ] Technical-service interpretation recorded

## B. Product and architecture evidence

- [ ] DMS functional description and system boundary
- [ ] Sensor/camera/NIR specifications and installation envelope
- [ ] Regulatory profile/configuration identification
- [ ] Activation, deactivation and reactivation behaviour
- [ ] Warning strategy, modalities, priorities and tell-tales
- [ ] Failure, degraded and unavailable behaviour
- [ ] Vehicle-signal and HMI interface specification
- [ ] Privacy/data-flow architecture
- [ ] Cybersecurity and software-update architecture

## C. Validation evidence

- [ ] Regulatory test procedure mapped to executable test cases
- [ ] Vehicle speed, road, day/night and environmental conditions covered
- [ ] Driver characteristics, seating positions and anthropometric range covered
- [ ] Drowsiness reference/ground-truth method approved
- [ ] Gaze-zone and distraction timing ground truth approved
- [ ] False-positive and false-negative acceptance criteria defined
- [ ] Camera blockage, occlusion, sunglasses and NIR failure tested
- [ ] HMI audibility/visibility/haptic behaviour verified
- [ ] Data integrity, timeout and stale-data behaviour verified
- [ ] Repeatability and reproducibility evidence available
- [ ] Technical-service witness plan approved

## D. Safety, SOTIF and security evidence

- [ ] HARA and functional/technical safety concepts complete
- [ ] SOTIF triggering-condition catalogue and scenario coverage argument complete
- [ ] TARA and cybersecurity claims complete
- [ ] Update compatibility and rollback evidence complete
- [ ] Freedom-from-interference and resource-overload evidence complete
- [ ] Known limitations and driver information approved

## E. Production and post-release evidence

- [ ] Conformity-of-production controls defined
- [ ] Calibration/model/software configuration traceable to vehicle VIN/type
- [ ] End-of-line camera alignment and health checks defined
- [ ] Field diagnostics and DTC handling defined
- [ ] Incident monitoring and regulatory reporting responsibilities assigned
- [ ] Data-retention, deletion and service-access controls audited
- [ ] Change-control process triggers re-homologation assessment

## Approval rule

A compliance row may move to `COMPLIANT` only when all required evidence links are populated, reviewed and approved. “Test passed” without source, configuration, vehicle and clause traceability is insufficient.
