# EU and UNECE Regulatory Baseline

## 1. EU General Safety Regulation

Regulation (EU) 2019/2144 requires advanced safety systems for applicable M and N vehicles. The DMS platform shall maintain separate regulatory profiles for drowsiness and distraction because they are covered by different delegated regulations and test procedures.

## 2. Driver Drowsiness and Attention Warning — EU 2021/1341

Commission Delegated Regulation (EU) 2021/1341 defines type-approval requirements and validation procedures for DDAW systems.

### Architecture-driving themes

- monitor the driver's drowsiness level and warn through the vehicle HMI;
- minimise system error under real driving conditions;
- operate during day and night within the defined environmental scope;
- validate against the regulatory sleepiness reference method and controlled manufacturer evidence;
- avoid a core dependency on biometric identity/facial recognition;
- retain only data necessary for closed-loop system operation;
- implement the required activation, reactivation, warning and failure behaviour;
- provide technical documentation and technical-service evidence.

The exact KSS threshold, test-route conditions, vehicle speed conditions, warning modality and validation statistics shall be copied from the controlled legal text into the clause matrix before a compliance baseline is approved.

## 3. Advanced Driver Distraction Warning — EU 2023/2590

Commission Delegated Regulation (EU) 2023/2590 defines type-approval requirements and validation procedures for ADDW systems and applies from 7 July 2024 for the applicable vehicle types.

### Architecture-driving themes

- detect long visual distraction using defined gaze regions and timing criteria;
- support the regulatory range of driver characteristics and seating positions;
- issue the required driver warning through the HMI;
- manage activation, temporary deactivation where permitted, and automatic reactivation;
- detect and communicate relevant system failure or unavailability;
- preserve privacy and data minimisation;
- provide manufacturer evidence and technical-service validation artefacts.

Intermittent distraction, cognitive distraction and additional body-movement cases may be addressed by future regulatory evolution. These shall remain product features unless and until a controlled amendment makes them homologation requirements.

## 4. UN Regulation No. 171 — Driver Control Assistance Systems

UN R171 applies to Driver Control Assistance Systems that provide sustained longitudinal and lateral control assistance while the driver remains responsible for the driving task.

DMS relevance exists only when the vehicle function falls within the adopted market's R171 scope. In that case the programme shall derive requirements for:

- driver engagement and availability monitoring;
- driver information and warning strategy;
- transition and response expectations;
- system override and driver intervention;
- failure/degraded behaviour;
- data recording and approval documentation where required by the applicable series/supplement.

The repository shall track the exact series of amendments and supplements selected by the homologation programme. A generic reference to “R171” is not sufficient for compliance.

## 5. Adjacent UNECE regulations

| Regulation | Applicability trigger | DMS impact |
|---|---|---|
| UN R155 | vehicle cybersecurity type approval in adopting markets | CSMS evidence, threat analysis, incident/field monitoring inputs |
| UN R156 | software update management in adopting markets | SUMS, update compatibility, rollback and post-update verification |
| UN R10 | EMC type approval | camera/NIR/ECU immunity and emissions evidence |
| UN R121 | controls, tell-tales and indicators where applicable | HMI symbols, identification and driver information |
| UN R79 / R171 | steering/DCAS feature fitted | driver engagement and warning interface |
| UN R152 / R131 | AEBS feature fitted | DMS-aware risk fusion may be used, but AEB compliance shall remain independently demonstrated |

## 6. Regulatory profile separation

The software/configuration baseline shall not use one universal “EU mode”. It shall support at least:

- `EU_DDAW_2021_1341`;
- `EU_ADDW_2023_2590`;
- `UNECE_DCAS_R171_<series>`;
- customer-specific overlays that cannot weaken mandatory behaviour.

## Official source register

- EU DDAW: https://eur-lex.europa.eu/eli/reg_del/2021/1341/oj
- EU ADDW: https://eur-lex.europa.eu/eli/reg_del/2023/2590/oj
- EU General Safety Regulation: https://eur-lex.europa.eu/eli/reg/2019/2144/oj
- UNECE R171 register: https://unece.org/transport/standards/transport/vehicle-regulations-wp29/addenda-1958-agreement-regulations-161-180
- UNECE GRVA ADAS overview: https://unece.org/transport/road-transport/working-party-automatedautonomous-and-connected-vehicles-introduction
