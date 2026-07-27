# 09 — Interfaces

## Recommended logical signals
| Signal | Type | Semantics |
|---|---|---|
| DMS_DrowsinessState | enum | NORMAL, EARLY, DROWSY, MICROSLEEP, UNKNOWN |
| DMS_DistractionState | enum | NONE, MONITOR, VISUAL, MANUAL, COMBINED, UNKNOWN |
| DMS_DriverAvailability | enum | AVAILABLE, PARTIAL, UNAVAILABLE, UNCONFIRMED |
| DMS_Confidence | enum | HIGH, MEDIUM, LOW, UNAVAILABLE |
| DMS_PrimaryReason | enum/bitfield | Dominant behavior reason |
| DMS_DegradedReason | enum/bitfield | Camera, illumination, timing, calibration or model reason |
| DMS_AlertRequest | enum | NONE, VISUAL, AUDIBLE, HAPTIC, ESCALATED |
| DMS_AliveCounter | counter | Freshness monitoring |
| DMS_E2E | checksum/profile | Integrity protection |

Signal cycle, bit allocation, E2E profile and timeout shall be allocated per vehicle architecture.
