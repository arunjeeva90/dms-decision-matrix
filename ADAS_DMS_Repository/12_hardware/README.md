# 12 — Hardware Requirements

| ID | Requirement | Verification |
|---|---|---|
| HWR-DMS-0001 | The production camera shall support automotive temperature, EMC, lifetime and diagnostic requirements allocated by the vehicle program. | Qualification review |
| HWR-DMS-0002 | The optical design shall cover the driver eye, face, upper torso and required hand/seatbelt ROIs throughout the declared seating envelope. | Optical/cabin test |
| HWR-DMS-0003 | The NIR subsystem shall control exposure without exceeding applicable eye-safety limits. | Analysis/test |
| HWR-DMS-0004 | The compute platform shall provide deadline, temperature, memory and accelerator health monitoring. | Fault injection |
| HWR-DMS-0005 | The system shall support synchronized capture of image and vehicle context signals. | Timing test |

Prototype recommendation: 1–2 MP RGB-IR/NIR-sensitive camera, 70–80° HFOV, 30 fps nominal, 940 nm NIR preferred. Final selection requires cabin geometry and eye-pixel analysis.
