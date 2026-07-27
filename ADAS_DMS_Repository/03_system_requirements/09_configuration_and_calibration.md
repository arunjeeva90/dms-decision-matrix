# 03.09 — Configuration and Calibration Requirements

| ID | Requirement | Source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1800 | The system shall use a version-controlled calibration dataset separate from executable software and model weights. | Platform governance | Calibration manager | Inspection |
| SYS-DMS-1801 | The calibration dataset shall identify vehicle programme, cabin geometry, camera/lens variant, mounting location, regulatory profile and product variant. | OEM integration | Calibration manager | Configuration audit |
| SYS-DMS-1802 | The system shall validate calibration integrity, compatibility and authenticity before activation. | Safety/cybersecurity | Calibration manager | Negative configuration test |
| SYS-DMS-1803 | The system shall reject a calibration dataset that is incompatible with the software, model, camera or regulatory profile. | Safety concept | Calibration manager | Negative test |
| SYS-DMS-1804 | The system shall support calibration parameters for gaze-zone boundaries, sanctioned-task timing, drowsiness thresholds, warning persistence, recovery hysteresis and feature observability. | Scenario matrix | Calibration manager | Configuration test |
| SYS-DMS-1805 | Calibration parameters that implement mandatory regulatory behaviour shall be access-controlled and protected from unauthorized service or customer modification. | Compliance governance | Security + calibration | Security test |
| SYS-DMS-1806 | The system shall record the active calibration identifier and checksum in diagnostic identification data and event evidence. | Traceability | Diagnostics | Inspection |
| SYS-DMS-1807 | The system shall support camera intrinsic, distortion, orientation and cabin-reference calibration required by the selected perception functions. | Camera geometry | Calibration + perception | Calibration test |
| SYS-DMS-1808 | The system shall detect calibration drift or mounting change beyond the validated tolerance and shall enter the appropriate limited/degraded state. | DMS-028 | Calibration monitor | Misalignment test |
| SYS-DMS-1809 | The system shall support production end-of-line verification of camera alignment, NIR illumination, driver ROI and basic perception health. | Manufacturing | EOL diagnostics | EOL test |
| SYS-DMS-1810 | The system shall support service replacement and recalibration without requiring uncontrolled changes to behavioral thresholds. | Service | Calibration + diagnostics | Service test |
| SYS-DMS-1811 | The system shall support market overlays only through an approved inheritance hierarchy in which legal requirements override OEM and vehicle-programme parameters. | Regulatory profiles | Configuration manager | Configuration analysis |
| SYS-DMS-1812 | The system shall provide rollback to the last approved calibration when an update fails integrity, compatibility or post-installation validation. | OTA safety | Update manager | Update fault test |
| SYS-DMS-1813 | Calibration release records shall trace each parameter group to requirement IDs, validation evidence and approval authority. | ASPICE/DOORS governance | Configuration management | Audit |
| SYS-DMS-1814 | The system shall prevent calibration values from creating overlapping or unreachable driver-state transitions. | State-machine integrity | Calibration validation | Static/negative test |
