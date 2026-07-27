# 03.02 — Sensing Quality and Driver Geometry Requirements

| ID | Requirement | Source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1100 | The system shall detect the configured driver seating region and distinguish the driver from other visible occupants. | DMS-001 / platform | Perception | Cabin-rig test |
| SYS-DMS-1101 | The system shall provide driver-presence validity and confidence independently from identity. | Privacy + architecture | Perception | Interface test |
| SYS-DMS-1102 | The system shall estimate head yaw, pitch and roll with validity and confidence for each output sample. | DMS-009 to DMS-021 | Perception | Ground-truth rig test |
| SYS-DMS-1103 | The system shall estimate left-eye and right-eye visibility and openness independently. | DMS-002 to DMS-024 | Perception | Annotated-video test |
| SYS-DMS-1104 | The system shall estimate gaze zone and gaze validity without requiring biometric driver enrolment. | ADDW / privacy | Perception | Scenario test |
| SYS-DMS-1105 | The system shall distinguish at minimum road-forward, instrument-cluster, centre-console, left-mirror, right-mirror, rear-view-mirror, side-window, passenger, lap/phone and unknown gaze zones where supported by the configured camera geometry. | DMS-005 to DMS-022 | Perception | Gaze-zone test |
| SYS-DMS-1106 | The system shall maintain a driver-head reference frame that compensates for seat position, nominal torso position and approved camera mounting tolerance. | Architecture | Calibration + perception | Calibration test |
| SYS-DMS-1107 | The system shall detect when face or eye geometry is outside the validated seating/head-position envelope. | SOTIF | Perception | Boundary test |
| SYS-DMS-1108 | The system shall estimate image-quality indicators for illumination, contrast, blur, saturation, glare, shadow, NIR reflection and occlusion. | DMS-028 | ISP + diagnostics | Fault injection |
| SYS-DMS-1109 | The system shall detect complete and partial camera blockage and provide severity, persistence and confidence. | DMS-028 | Diagnostics | Occlusion test |
| SYS-DMS-1110 | The system shall detect loss or malfunction of active NIR illumination where NIR is required for the selected operating profile. | Night operation | Camera + diagnostics | Electrical/fault test |
| SYS-DMS-1111 | The system shall detect camera misalignment beyond the calibrated tolerance or declare calibration confidence insufficient. | Safety concept | Calibration monitor | Misalignment test |
| SYS-DMS-1112 | The system shall distinguish eye occlusion caused by sunglasses, spectacles reflection, hand, hair, head covering or other obstruction when that distinction is technically supported; otherwise it shall report generic eye occlusion. | Diversity/SOTIF | Perception | Diversity test |
| SYS-DMS-1113 | The system shall not infer open or closed eye state when eye visibility is below the configured minimum validity threshold. | Safety/SOTIF | Perception | Negative test |
| SYS-DMS-1114 | The system shall provide hand and phone-object detections with ROI validity for face/ear, steering, torso, lap and centre-console regions where visible. | DMS-005 to DMS-011 | Perception | Detection test |
| SYS-DMS-1115 | The system shall provide torso and shoulder-region visibility required for posture and visual seatbelt functions independently from face/eye visibility. | Product variant | Perception | Cabin-rig test |
| SYS-DMS-1116 | The system shall report per-function observability so that unavailable phone, belt or posture cues do not invalidate otherwise usable drowsiness or gaze outputs. | Architecture | Perception + interface | Interface test |
| SYS-DMS-1117 | The system shall use synchronized vehicle signals to contextualize camera observations, including speed, gear, steering, indicator, yaw rate and brake state when available. | DMS-009, DMS-017, DMS-020 | Fusion | HIL test |
| SYS-DMS-1118 | The system shall detect stale, missing, implausible or time-inconsistent vehicle-context signals and shall prevent their use in sanctioned-task suppression. | Safety concept | Interface + safety monitor | Fault injection |
