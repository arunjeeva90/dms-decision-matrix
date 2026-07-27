# 01 — Platform Definition

## Product intent
A scalable automotive DMS platform for L1–L2+ applications that estimates driver drowsiness, distraction, availability, restraint misuse, and sensor health, and supplies safety-qualified driver-state outputs to vehicle and ADAS functions.

## Product variants
| Variant | Functions | Typical deployment |
|---|---|---|
| DMS Core | Presence, drowsiness, distraction, camera health | Entry passenger/commercial |
| DMS Safety | Core + availability + degraded-state contract + safety monitor | NCAP / regulated programs |
| DMS Vision+ | Safety + phone + visual seatbelt + posture | Premium/fleet |
| DualSight Fusion | Vision+ + forward-ADAS risk fusion | Integrated ADAS ECU |

## Gen-1 scope
- Driver presence and face tracking
- Eye state, blink dynamics, PERCLOS and microsleep cues
- Head pose and gaze-zone classification
- Visual/manual phone distraction
- Driver availability state
- Camera blockage, glare, low-light, NIR and alignment diagnostics
- Visual seatbelt authenticity support where camera coverage permits
- HMI alert request and ADAS driver-state interface

## Out of scope unless separately approved
- Medical diagnosis
- Definitive alcohol/drug impairment determination without dedicated sensor
- Biometric identity enforcement
- Fully autonomous fallback solely from DMS
