# 00 — Governance

## Requirement object format
Every requirement shall contain:

| Attribute | Rule |
|---|---|
| ID | Unique, immutable identifier |
| Title | Concise noun phrase |
| Requirement | Atomic, testable “shall” statement |
| Rationale | Why it is needed |
| Source | Stakeholder, regulation, safety analysis, architecture |
| Allocation | System/subsystem/component |
| ASIL / Safety class | QM/A/B/C/D or TBD |
| Verification | Test, analysis, inspection, demonstration |
| Status | Draft, Reviewed, Approved, Obsolete |
| Traces | Parent, child, test, hazard, interface |

## ID taxonomy
- `STK-DMS-xxxx`: stakeholder requirement
- `SYS-DMS-xxxx`: system requirement
- `HWR-DMS-xxxx`: hardware requirement
- `SWR-DMS-xxxx`: software requirement
- `IFR-DMS-xxxx`: interface requirement
- `FSR-DMS-xxxx`: functional safety requirement
- `TSR-DMS-xxxx`: technical safety requirement
- `SEC-DMS-xxxx`: cybersecurity/privacy requirement
- `DAT-DMS-xxxx`: data/ML lifecycle requirement
- `TST-DMS-xxxx`: verification case

## Authoring rules
1. One obligation per requirement.
2. Use measurable limits and operating conditions.
3. Avoid “user-friendly”, “robust”, “fast” without acceptance criteria.
4. Separate feature behavior from calibration values.
5. Record uncertainty and degraded-state behavior explicitly.
6. Never cite a regulation as satisfied without evidence and applicability review.
