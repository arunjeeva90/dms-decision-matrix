# Normalized Driver-State Decision Architecture

This architecture is the system-requirements interpretation of the live scenario matrix.

```mermaid
flowchart TD
    A[Cabin frame + sensor status] --> B[Image quality and observability]
    V[Vehicle context] --> C[Context validity and sanctioned-task logic]
    B --> P[Perception evidence]
    P --> D1[Drowsiness evidence]
    P --> D2[Distraction evidence]
    P --> D3[Presence posture responsiveness evidence]
    C --> D2
    C --> D3

    D1 --> T1[Drowsiness temporal fusion]
    D2 --> T2[Distraction temporal fusion]
    D3 --> T3[Availability temporal fusion]
    B --> AV[DMS sensing availability]

    T1 --> O1[Drowsiness State]
    T2 --> O2[Distraction State]
    T3 --> O3[Driver Availability State]
    AV --> O4[DMS Availability Confidence]

    O1 --> ARB[HMI and ADAS arbitration]
    O2 --> ARB
    O3 --> ARB
    O4 --> ARB
    R[Validated external ADAS risk] --> ARB

    ARB --> H[HMI Request + reason + urgency]
    ARB --> F[Driver-aware ADAS escalation request]
    ARB --> I[Versioned vehicle interface]
```

## Architectural rules

1. Drowsiness, distraction, driver availability and DMS sensing availability are independent outputs.
2. `DEGRADED/UNAVAILABLE` is not part of behavioral severity.
3. Sanctioned-task classification uses valid vehicle context before distraction arbitration.
4. Temporal fusion precedes warning escalation.
5. Low observability produces `UNKNOWN/UNCONFIRMED`, not a confident normal state.
6. External ADAS risk is validated before fusion.
7. DMS may request escalation but does not independently command vehicle motion.
8. HMI arbitration preserves mandatory regulatory behavior over optional OEM coaching.
