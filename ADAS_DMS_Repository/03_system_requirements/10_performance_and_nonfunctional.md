# 03.10 — Performance and Non-Functional Requirements

| ID | Requirement | Source | Allocation | Verification |
|---|---|---|---|---|
| SYS-DMS-1900 | The system shall provide nominal driver-state outputs at a configured rate of at least 15 Hz, with camera acquisition nominally at 30 fps. | Platform target | Platform | Measurement |
| SYS-DMS-1901 | The system shall meet the allocated sensor-to-output latency for each function and shall not exceed 100 ms at the 99th percentile under nominal validated load unless a stricter regulatory value applies. | Platform target | Platform | Profiling |
| SYS-DMS-1902 | The system shall detect missed deadlines and report output age and validity rather than publishing stale behavioral states as current. | Safety concept | Runtime monitor | Load/fault test |
| SYS-DMS-1903 | The system shall maintain deterministic safety-decision execution under the validated worst-case compute, memory, temperature and bus-load conditions. | Functional safety | Platform + safety monitor | Stress test |
| SYS-DMS-1904 | The system shall define and verify maximum startup time from wake-up to `ACTIVE` or declared degraded/unavailable state. | Vehicle integration | State manager | Timing test |
| SYS-DMS-1905 | The system shall define per-function detection, confirmation, warning and recovery timing budgets. | Scenario requirements | System architecture | Timing analysis + test |
| SYS-DMS-1906 | The system shall support day and night operation across the approved cabin illumination envelope. | AIS/EU DDAW | Camera + perception | Vehicle/cabin test |
| SYS-DMS-1907 | The system shall define validated operating ranges for temperature, supply voltage, vibration, camera contamination and electromagnetic environment. | Automotive environment | Hardware/platform | Qualification test |
| SYS-DMS-1908 | The system shall provide performance evidence across driver diversity dimensions including skin tone, age band, sex, spectacles, sunglasses, facial hair, head coverings, seating position and body posture, subject to privacy governance. | ADDW/SOTIF | Data/ML + V&V | Dataset audit + subgroup test |
| SYS-DMS-1909 | The system shall define minimum acceptable subgroup performance and shall document unresolved subgroup limitations as SOTIF residual risk. | SOTIF | Data/ML + safety | Statistical review |
| SYS-DMS-1910 | The system shall measure false-warning, missed-warning, invalid-output and unavailable-time rates by scenario family. | V&V | Analytics | Statistical test |
| SYS-DMS-1911 | The system shall maintain separate performance metrics for normal sanctioned tasks, drowsiness, visual distraction, manual distraction, availability and degraded sensing. | Scenario matrix | V&V | Metrics audit |
| SYS-DMS-1912 | The system shall support deterministic replay of recorded synchronized cabin and vehicle-context data for regression testing. | ASPICE/V&V | Tooling | Replay test |
| SYS-DMS-1913 | The system shall uniquely identify software, model, calibration, dataset and test-suite versions in every qualification report. | Configuration management | Platform/V&V | Audit |
| SYS-DMS-1914 | The system shall support secure update of software, models and calibration with authenticity, integrity, rollback and post-update health verification. | R156/21434 | Update manager | Update test |
| SYS-DMS-1915 | The system shall minimize production storage of raw cabin imagery and shall use derived event data by default for diagnostics and field monitoring. | Privacy | Data platform | Privacy audit |
| SYS-DMS-1916 | The system shall define resource budgets for CPU, accelerator, memory, bandwidth, storage, power and thermal headroom for each product variant. | Platform architecture | Hardware/software architecture | Profiling + analysis |
| SYS-DMS-1917 | The system shall enter a controlled load-shedding mode before compute or thermal overload can violate safety-relevant deadlines. | Safety concept | Runtime manager | Stress test |
| SYS-DMS-1918 | Load shedding shall preserve mandatory regulatory and safety-monitor functions before optional phone, belt, posture, visualization or logging functions. | Product prioritization | Runtime manager | Stress/configuration test |
| SYS-DMS-1919 | The system shall maintain time synchronization within the allocated tolerance between camera frames, vehicle signals, ADAS risk inputs and DMS outputs. | Fusion architecture | Time service | Timing test |
| SYS-DMS-1920 | The system shall provide availability and diagnostic evidence sufficient to calculate field reliability and safety-monitor coverage for the production safety case. | Functional safety | Diagnostics + field analytics | Evidence audit |
