# 13 — Software Requirements

| ID | Requirement | Verification |
|---|---|---|
| SWR-DMS-0001 | Software components shall have explicit interfaces, execution periods, deadlines, memory budgets and failure behavior. | Architecture review |
| SWR-DMS-0002 | Perception and decision calibration parameters shall be versioned independently from executable code. | Configuration test |
| SWR-DMS-0003 | The decision layer shall use monotonic timestamps and reject out-of-order observations. | Unit test |
| SWR-DMS-0004 | Model runtime shall report initialization, inference, tensor-integrity and accelerator errors. | Fault injection |
| SWR-DMS-0005 | Logging shall support field diagnostics without retaining unnecessary cabin imagery. | Privacy/diagnostic test |
