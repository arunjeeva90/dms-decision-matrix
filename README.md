# IND-VIAS DualSight DMS v0.2 — Driver-State Decision Matrix

An interactive engineering reference for defining, reviewing, and aligning the Driver Monitoring System decision logic for **IND-VIAS DualSight DMS**.

## Interactive Webpage

Open the live interactive driver-state decision matrix here:

[Launch DMS Decision Matrix Webpage](https://arunjeeva90.github.io/dms-decision-matrix/)

---

## Purpose

Before implementing Driver Monitoring System logic in software, we need one common reference that clearly defines how the system interprets driver behavior.

DMS is not only about detecting drowsiness, distraction, or phone usage. The real challenge is deciding:

- when a driver state is normal
- when the system should silently monitor
- when it should warn the driver
- when it becomes safety-critical
- when the DMS output itself is degraded or unavailable

This webpage converts raw cabin observations such as eye closure, gaze direction, head pose, phone use, camera confidence, and driver response into clear system-level outputs:

**Normal → Monitor → Warning → Danger → Critical / DMS Degraded**

The page acts as a version-controlled system-definition artifact for engineering review before software implementation, validation planning, CAN interface definition, HMI design, ADAS fusion logic, and partner discussions.

---

## Why This Matrix Is Important

Most DMS descriptions stop at a feature level, such as drowsiness detection, distraction detection, phone detection, or driver availability.

This matrix goes one level deeper. It defines the decision logic behind those features.

For example:

- A short downward glance may be a valid instrument-cluster check.
- A sustained downward gaze may become a distraction warning.
- A phone object with downward gaze may become a danger-level event.
- A camera-blocked condition should not be treated as normal.
- A high forward ADAS risk combined with driver inattention should escalate earlier.

This helps avoid false alerts, unstable warnings, and unclear system behavior.

---

## What This Webpage Provides

The webpage provides:

- Interactive driver-state use-case cards
- Compact and expanded view for each use case
- Full table view for engineering traceability
- CSV download for requirements and validation work
- Risk-level definitions
- Threshold guidance
- Cumulative and recovery logic
- DMS confidence and degraded-mode handling
- ADAS readiness output contract
- Compliance traceability anchors

---

## Intended Users

This reference is useful for:

- ADAS system engineering
- DMS software development
- AI perception development
- Validation and test teams
- Functional safety teams
- HMI teams
- ADAS fusion teams
- Partner and supplier alignment

---

## Business Value

- Faster partner alignment
- Clearer requirements
- Fewer rework cycles
- Better validation traceability
- Stronger system-definition maturity
- Cleaner transition from concept to software implementation

---

## Page Structure

### 1. Purpose and Intent

Explains why the webpage exists and positions it as an engineering decision-logic reference, not a marketing feature list.

### 2. Risk Levels

Defines the five-level driver-state ladder:

**Normal → Monitor → Warning → Danger → Critical / Degraded**

The **Monitor** state is important because it reduces alert fatigue by preventing every short glance or head movement from becoming an immediate warning.

### 3. Classification Inputs

Explains that DMS classification should not rely on head pose alone.

The decision logic combines:

- Head pose
- Eye state
- Gaze zone
- Phone or hand activity
- Duration
- Vehicle context
- DMS confidence

### 4. Interactive Matrix

The core section of the webpage.

Each card represents one driver-state use case. Cards remain compact by default, lift on hover, and expand on click to show the full logic.

Each use case defines:

- Scenario
- Head state
- Eye state
- Gaze context
- Driver state
- Classification
- Alert level
- Primary type
- Trigger condition
- Recommended HMI behavior
- Compliance mapping

### 5. Full Table View

Provides a spreadsheet-style traceability view of the full decision matrix.

This is useful for:

- Requirement tracking
- Validation planning
- Test-case creation
- Version comparison
- Partner review

A CSV download option is provided for use in Excel, Jira, GitHub, validation sheets, or requirements tools.

### 6. Threshold Guidance

Defines prototype timing defaults for DMS logic.

Examples include:

- Off-road gaze duration
- Eye closure duration
- PERCLOS trend
- No-face / no-eye timeout
- No-response-after-warning behavior

These are engineering defaults only. Final values must be calibrated using real Indian cabin-road data and homologation evidence.

### 7. Cumulative and Recovery Logic

Defines how the system handles repeated short events and warning recovery.

This prevents unstable alert behavior such as:

**Normal → Warning → Normal → Warning**

Recovery requires stable road gaze, open eyes, no phone cue, and restored confidence.

### 8. Processing Flow / Decision Architecture

Defines the correct DMS decision flow:

- DMS confidence check
- Sanctioned-task pre-filter
- Independent driver-state heads
- Risk fusion
- Alert arbitration + hysteresis
- CAN / HMI / ADAS output

This structure separates observation, interpretation, confidence, and final action.

### 9. ADAS Readiness Output Contract

Defines how DMS supports the forward ADAS stack.

Forward ADAS understands outside risk such as TTC, pedestrian risk, cut-in risk, and lane-departure risk.

DMS understands whether the driver is ready to respond.

Together, they enable driver-aware ADAS behavior.

Example:

**Forward TTC risk high + driver not looking at road → Earlier warning escalation**

### 10. Compliance Mapping and Final Architecture

Maps the matrix to safety, validation, and regulatory traceability anchors such as:

- AIS-184 / DDAW direction
- AIS-197 / Bharat NCAP safety assist alignment
- EU DDAW / ADDW expectations
- UNECE R171 driver engagement relevance
- ISO 26262 functional safety
- ISO 21448 / SOTIF
- ISO/SAE 21434 cybersecurity

The final architecture exposes four independent DMS outputs:

- Drowsiness State
- Distraction State
- Driver Availability State
- DMS Confidence State

These outputs are fused into the final driver-risk decision.

---

## Summary

This webpage is an interactive engineering reference for IND-VIAS DualSight DMS driver-state logic.

It defines how raw cabin observations are converted into ADAS-ready driver-state outputs.

The key value is that it defines:

- when to alert
- when not to alert
- how to suppress false alerts
- how to handle degraded DMS confidence
- how to support forward ADAS decisions
- how to provide traceability for validation and safety-case preparation

In simple terms:

**The camera detects the driver.**  
**This matrix defines how the vehicle should interpret the driver.**
