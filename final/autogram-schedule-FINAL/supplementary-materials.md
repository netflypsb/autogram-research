# Supplementary Materials

**For:** "Progressive Technical Deepening Through Scheduled Autonomous Agent Interaction on a Hybrid Human–AI Social Platform: A Case Study"

---

## A. Verified Quantitative Data

### A.1 Progression Note Statistics (Programmatically Verified)

| Note | File | Words | Bytes | Lines | Suggestions |
|------|------|-------|-------|-------|-------------|
| 001 | Not archived* | ~1,000–1,500 (est.) | N/A | N/A | 10+ |
| 002 | progression-note-002.md | 1,290 | 8,327 | 137 | 14 |
| 003 | progression-note-003.md | 669 | 4,538 | 76 | 10 |
| 004 | progression-note-004.md | 1,382 | 9,001 | 111 | 11 |
| 005 | progression-note-005.md | 1,995 | 12,723 | 148 | 12 |
| 006 | progression-note-006.md | 2,701 | 17,337 | 175 | 11 |
| **Total (archived)** | — | **8,037** | **51,926** | **647** | **58** |
| **Total (incl. est. 001)** | — | **~9,200** | — | — | **~68** |

*Note 001 was referenced in INDEX.md but not archived in the artifacts directory. Word count estimated from INDEX.md summary length and comparable initial analysis scope.

**Methodology:** Word counts verified using PowerShell `Measure-Object -Word` on source files. Byte sizes verified via `Get-Item .Length`. These are exact measurements, not estimates.

### A.2 Ancillary Document Statistics

| Document | Words | Bytes |
|----------|-------|-------|
| INDEX.md | 1,190 | 9,310 |
| Chat Thread (Telegram reports) | 2,034 | 14,157 |
| Scheduled Task prompt | 107 | 691 |
| autogram.md (platform description) | 2,652 | 22,229 |

### A.3 GitHub Repository Metrics (from Note 006, final state)

**MANPADS-System-Launcher-and-Rocket:**

| Metric | Value |
|--------|-------|
| Stars | 2,431 |
| Forks | 676 |
| Watchers | 106 |
| Total commits | 8 |
| Contributors | 4 |
| Open PRs | 3 (#16 security fix, #17 UI fix, #18 perf fix) |
| Open issues | 7 |
| Last commit | 2026-03-18 |
| Author response | None since 2026-03-18 |

**Distributed-Camera-Node-Tracking-System:**

| Metric | Value |
|--------|-------|
| Stars | 349 |
| Forks | 176 |
| Watchers | 22 |
| Contributors | 1 |
| Open issues | 1 (wiring diagram request) |
| Last commit | 2026-01-26 |

---

## B. Complete Technical Suggestions Catalog

### Cycle 1 — Initial Code Review (Note 001, not archived)

| # | Suggestion | Subsystem | Novelty |
|---|-----------|-----------|---------|
| 1 | Madgwick sensor fusion algorithm | Sensor fusion | Moderate |
| 2 | Cascaded PID (outer rate + inner position) | Control | Moderate |
| 3 | Differential canard control | Actuator | Moderate |
| 4 | LoRa telemetry recommendation | Communication | Moderate |
| 5 | Onboard flash logging (SPIFFS/LittleFS) | Data recording | Moderate |
| 6 | Servo upgrade path (MG90S/Hitec) | Actuator | Moderate |
| 7 | BNO085 IMU upgrade | Sensor | Moderate |
| 8 | TVC consideration for future | Actuator architecture | Moderate |
| 9 | Fire control bridge | System integration | Moderate |
| 10+ | NVS calibration, GPS pin fix, YOLO retrain | Various | Moderate |

### Cycle 2 — Detailed Analysis and Prioritised Roadmap (Note 002)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Complementary filter for IMU fusion | Sensor fusion | Moderate | $0 |
| 2 | Cascaded PID with anti-windup | Control | Moderate | $0 |
| 3 | Dual-axis stabilisation (pitch canards) | Actuator | Moderate-High | ~$5 |
| 4 | Thrust Vector Control (revisited) | Actuator | Moderate | ~$10 |
| 5 | SD card logging at 100Hz+ | Data recording | Moderate | ~$2 |
| 6 | SX1262 LoRa module (5–10 km range) | Communication | Moderate-High | ~$8 |
| 7 | Dual-band communication (WiFi + LoRa) | Communication | Moderate | $0 |
| 8 | Kalman filter race condition fix | Software | **Novel (bug)** | $0 |
| 9 | Measurement gating (Mahalanobis distance) | Software | High | $0 |
| 10 | Custom YOLOv8-nano retraining | Computer vision | High | $0 |
| 11 | EMA smoothing for triangulation | Computer vision | Moderate | $0 |
| 12 | 18650 battery pack replacement | Power | Moderate | ~$12 |
| 13 | NTP time synchronisation | Software | High | $0 |
| 14 | Web configuration page (remove hardcoded creds) | Security | **Novel** | $0 |

**Bugs identified:** Kalman filter threading race condition; missing measurement gating; hardcoded WiFi credentials; brownout detection disabled as workaround.

### Cycle 3 — Advanced Control and Guidance (Note 003)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Dynamic-pressure gain scheduling | Control | **High** | $0 |
| 2 | Feed-forward rate command | Control | **High** | $0 |
| 3 | Actuator rate limiting model | Control | Moderate | $0 |
| 4 | Canard servo blowback detection | Actuator | **Very High** | $0.50–10 |
| 5 | Pitot tube airspeed (MPXV7002DP) | Sensor | **High** | $5 |
| 6 | Gravity turn follower guidance | Guidance | **Very High** | $0 |
| 7 | Proportional navigation (PN) guidance | Guidance | **Very High** | $0 |
| 8 | Dual-deployment recovery system | Recovery | **High** | ~$1 |
| 9 | Launch rail departure logic | Control | High | $0 |
| 10 | Post-flight analysis pipeline (PID overlay, NIS, PSD) | Development | High | $0 |

### Cycle 4 — Reliability and Safety Infrastructure (Note 004)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Ignition continuity check circuit | Safety | **Very High** | ~$1 |
| 2 | Redundant ignition path (2nd MOSFET) | Safety | **Very High** | ~$1 |
| 3 | Accelerometer-based smart ignition timing | Safety | High | $0 |
| 4 | Telemetry XOR checksum | Communication | **Very High** | $0 |
| 5 | Sequence number framing | Communication | **Very High** | $0 |
| 6 | HIL bench test mode (desk PID tuning) | Development | **Extremely High** | $0 |
| 7 | Aerodynamic canard sizing (CP-CG analysis) | Aerodynamics | **Very High** | $0 |
| 8 | Cl_delta estimation via AVL/XFLR5 | Aerodynamics | **Very High** | $0 |
| 9 | Flight termination via LoRa abort | Safety | **Very High** | $0 |
| 10 | Time-multiplexed compass reads | Sensor | High | $0 |
| 11 | Roll-yaw coupling with 4×3 mixing matrix | Control | **Very High** | $0 |

### Cycle 5 — Structural Dynamics and Propulsion (Note 005)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Accelerometer saturation detection (8G range) | Sensor | **Extremely High** | $0 |
| 2 | 16G range switching for ignition | Sensor | **Extremely High** | $0 |
| 3 | Fin flutter speed analysis (aeroelastic eqns) | Structural | **Revolutionary** | $0 |
| 4 | Carbon fibre fins for flutter suppression | Structural | **Very High** | ~$10 |
| 5 | Ground vibration testing protocol | Testing | High | $0 |
| 6 | Custom KNSB propellant grain geometry | Propulsion | **Revolutionary** | $5–8/motor |
| 7 | PID-friendly thrust curve profiling | Propulsion | **Very High** | $0 |
| 8 | Cd vs Mach extraction from flight data | Aerodynamics | **Very High** | $0 |
| 9 | Wind sensing (vane/anemometer) | Environmental | High | $3–8 |
| 10 | Adaptive launch angle correction | Guidance | High | $0 |
| 11 | Onboard ESP32-CAM on rocket | Verification | High | ~$8 |
| 12 | OTA firmware updates for all nodes | Development | **Very High** | $0 |

### Cycle 6 — Physical Data Quality Foundations (Note 006)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | IMU vibration isolation (Sorbothane) | Physical | **Revolutionary** | $2–5 |
| 2 | 4th-order Butterworth software bandpass | Physical | High | $0 |
| 3 | Thermal management (cork insulation) | Thermal | **Revolutionary** | ~$1 |
| 4 | Gyro temperature compensation table | Thermal | **Very High** | $0 |
| 5 | Cold gas RCS (CO₂) for zero-airspeed | Control | **Revolutionary** | $15–20 |
| 6 | Multi-stage flight architecture | Architecture | **Revolutionary** | ~$8 |
| 7 | Accelerometer-based separation detection | Architecture | **Very High** | $0 |
| 8 | Dual-IMU voting algorithm | Redundancy | **Very High** | $2–15 |
| 9 | ESP-MESH networking for cameras | Network | **High** | $0 |
| 10 | Environmental monitoring station | Environmental | High | $15–25 |
| 11 | Dual-station wind gradient estimation | Environmental | High | $0 |

---

## C. Complete Coverage Matrix

**Legend:** X = addressed in cycle; — = not addressed

| Subsystem | C1 | C2 | C3 | C4 | C5 | C6 |
|-----------|:--:|:--:|:--:|:--:|:--:|:--:|
| Sensor fusion algorithms | X | X | X | — | — | — |
| IMU hardware selection | X | X | — | — | — | — |
| Attitude estimation (Madgwick) | X | — | — | — | — | — |
| Cascaded PID control | X | X | — | — | — | — |
| Gain scheduling | — | — | X | — | — | — |
| Feed-forward control | — | — | X | — | — | — |
| Actuator rate limiting | — | — | X | — | — | — |
| Canard deflection control | X | — | — | — | — | — |
| Dual-axis (pitch+roll) | — | X | — | — | — | — |
| TVC (thrust vector control) | X | X | — | — | — | — |
| Cold gas RCS | — | — | — | — | — | X |
| LoRa telemetry | X | X | — | — | — | — |
| Dual-band comm (WiFi+LoRa) | — | X | — | — | — | — |
| Telemetry checksum/framing | — | — | — | X | — | — |
| ESP-MESH networking | — | — | — | — | — | X |
| OTA firmware updates | — | — | — | — | X | — |
| SD card data logging | — | X | — | — | — | — |
| Onboard flash logging | X | — | — | — | — | — |
| 18650 battery system | X | X | — | — | — | — |
| YOLO custom retraining | — | X | — | — | — | — |
| Measurement gating | — | X | — | — | — | — |
| Kalman thread safety fix | — | X | — | — | — | — |
| Pitot tube airspeed | — | — | X | — | — | — |
| Accelerometer saturation | — | — | — | — | X | — |
| IMU vibration isolation | — | — | — | — | — | X |
| IMU dual-voting redundancy | — | — | — | — | — | X |
| Thermal management | — | — | — | — | — | X |
| Guidance (gravity turn) | — | — | X | — | — | — |
| Guidance (proportional nav) | — | — | X | — | — | — |
| Launch rail departure logic | — | — | X | — | — | — |
| Wind sensing | — | — | — | — | X | X |
| Adaptive launch angle | — | — | — | — | X | — |
| Environmental monitoring | — | — | — | — | — | X |
| Dual-deployment recovery | — | — | X | — | — | — |
| Flight termination system | — | — | — | X | — | — |
| Ignition continuity | — | — | — | X | — | — |
| Ignition redundancy | — | — | — | X | — | — |
| Smart ignition timing | — | — | — | X | — | — |
| HIL bench testing | — | — | — | X | — | — |
| Post-flight analysis | — | — | X | — | — | — |
| Canard sizing (CP-CG) | — | — | — | X | — | — |
| Cl_delta estimation | — | — | — | X | — | — |
| Fin flutter analysis | — | — | — | — | X | — |
| Carbon fibre fins | — | — | — | — | X | — |
| Propellant grain geometry | — | — | — | — | X | — |
| Thrust curve profiling | — | — | — | — | X | — |
| Cd extraction from data | — | — | — | — | X | — |
| Multi-stage architecture | — | — | — | — | — | X |
| Separation detection | — | — | — | — | — | X |
| Roll-yaw coupling (4×3) | — | — | — | X | — | — |
| Compass timing interference | — | — | — | X | — | — |
| Security (credential removal) | — | X | — | — | — | — |
| Onboard rocket camera | — | — | — | — | X | — |
| Network topology (mesh) | — | — | — | — | — | X |

**Total individual subsystem items: 54** (across 6 cycles)
**Unique subsystem categories (grouped): 29**

---

## D. Novel Ideas Ranked by Impact

### Tier 1 — Paradigm-Shifting

1. **IMU vibration isolation** (Cycle 6) — $2–5 Sorbothane isolators as mechanical low-pass filter. Identified motor vibration (200–800 Hz) as root cause degrading ALL sensor fusion algorithms simultaneously. Paradigm shift: fix physical data quality before improving algorithms.

2. **Cold gas RCS** (Cycle 6) — $15–20 CO₂ cartridge with solenoid nozzles. Identified fundamental limitation of aerodynamic control surfaces (require dynamic pressure). Previously undiscussed in any thread or issue.

3. **Custom KNSB propellant grain geometry** (Cycle 5) — $5–8/motor. Moving from off-the-shelf motor selection to custom grain design for PID-friendly thrust curves. Entirely new domain for the project.

4. **Fin flutter analysis** (Cycle 5) — $0 (analysis) / $10 (CF fins). First structural dynamics analysis. PLA fin flutter speed (150–250 m/s) dangerously close to E-class flight speeds. Equations provided.

5. **Multi-stage architecture** (Cycle 6) — $8 additional electronics. Two-stage with accelerometer-based separation detection for 2–3× altitude gain.

### Tier 2 — Very High Impact

6. **HIL bench testing** (Cycle 4) — $0. Simulated flight profiles driving real PID loop for desk-based tuning.
7. **Proportional navigation guidance** (Cycle 3) — $0 (~10 lines). Classic guided missile law applied to amateur rocketry.
8. **Dynamic-pressure gain scheduling** (Cycle 3) — $0. Physics-based PID gain adaptation.
9. **Flight termination system** (Cycle 4) — $0. LoRa-based in-flight abort. Safety-critical capability absent from original design.
10. **Aerodynamic canard sizing** (Cycle 4) — $0. First principled canard design (CP-CG, Cl_delta).

### Tier 3 — High Impact

11. **Dual-deployment recovery** (Cycle 3) — ~$1. Drogue + main for reusability.
12. **Telemetry XOR checksum** (Cycle 4) — $0. Silent data corruption from EMI addressed.
13. **Cd extraction from flight data** (Cycle 5) — $0. Validate OpenRocket simulations.
14. **Thermal management** (Cycle 6) — $1–7. Cork insulation + temperature compensation.
15. **OTA firmware updates** (Cycle 5) — $0. WiFi-based updates for all ESP32 nodes.

---

## E. Composite Depth Score Details

### Scoring Breakdown by Cycle

| Dimension | Cycle 2 | Cycle 3 | Cycle 4 | Cycle 5 | Cycle 6 |
|-----------|---------|---------|---------|---------|---------|
| **Algorithmic sophistication** | 6 | 8 | 7 | 8 | 7 |
| Rationale | Complementary filter, cascaded PID, Kalman fix | Gain scheduling, PN guidance, feed-forward | HIL testing, roll-yaw coupling matrix | Aeroelastic equations, Cd extraction methods | Butterworth filter design, voting algorithms |
| **Physics domains** | 3 | 5 | 6 | 8 | 9 |
| Rationale | Control theory, communication, power | + guidance, recovery, aerodynamics | + safety, thermal (ignition), magnetics | + structural dynamics, propulsion chemistry, atmospheric | + vibration physics, thermodynamics, fluid dynamics (RCS), network theory |
| **Hardware/mechanical** | 3 | 4 | 6 | 8 | 9 |
| Rationale | Sensor/servo selection, basic BOM | + pitot tube, springs, CF fins | + ignition circuits, canard sizing (CP-CG) | + flutter analysis, custom grain design, camera integration | + vibration isolation design, thermal insulation, RCS nozzle layout, staging mechanics |
| **System integration** | 4 | 6 | 7 | 8 | 10 |
| Rationale | Single-node firmware improvements | + ground segment (LoRa), recovery system | + full vehicle safety (abort, ignition, telemetry integrity) | + flight data pipeline, field operations, simulation validation | + multi-stage distributed system, mesh network, environmental profiling station |
| **Composite mean** | **4.0** | **5.75** | **6.5** | **8.0** | **8.75** |

### Trend Analysis

- **Monotonic increase**: Composite score rose every cycle without exception
- **Steepest jump**: Cycle 4 → 5 (+1.5 points) — entry into structural dynamics and propulsion
- **Largest dimension jump**: System integration, Cycle 5 → 6 (+2 points) — multi-stage architecture
- **Most consistent dimension**: Algorithmic sophistication (range: 6–8) — maintained high level throughout
- **Most growth dimension**: Physics domains (3 → 9, +200%) and Hardware depth (3 → 9, +200%)

---

## F. Root-Cause Evolution Timeline

| Cycle | Approach to Sensor Accuracy | Classification |
|-------|----------------------------|----------------|
| 2 | Complementary filter, Kalman fix | **Algorithmic coping** |
| 3 | Pitot tube for missing airspeed state | **Missing data identification** |
| 5 | Accelerometer 8G saturation during ignition | **Failure mode detection** |
| 6 | Vibration isolation + thermal compensation | **Physical root-cause elimination** |

This four-stage evolution mirrors established engineering maturity models where teams progress from treating symptoms to eliminating causes.

---

## G. Cross-Domain Connection Inventory

| Cycle | Connections | Details |
|-------|------------|---------|
| 2 | 2 | Sensor fusion → PID performance; Communication range → Operational capability |
| 3 | 3 | Propulsion profile → Gain scheduling need; Guidance law → Recovery timing; Servo dynamics → Control authority limit |
| 4 | 2 | Safety infrastructure → Control architecture; Aerodynamic sizing → Mechanical design constraints |
| 5 | 5 | Structural dynamics → Control algorithms; Propulsion design → Gain scheduling elimination; Simulation → Flight data validation; Wind → Trajectory dispersion; Camera → Servo verification |
| 6 | 7 | Physical mounting → All sensor fusion; Thermal → All control algorithms; Zero-airspeed → Recovery orientation; Multi-stage → Propulsion; Sensor redundancy → Reliability; Network topology → Communication; Atmospheric → Guidance |

**Trend:** 2 → 3 → 2 → 5 → 7 connections. Accelerating cross-domain synthesis as the agent builds a more complete system model.

---

## H. Data Availability

All source data is publicly available in the parent repository:

| File | Location |
|------|----------|
| Progression notes 002–006 | `artifacts/rocket-launcher/progression-note-00X.md` |
| INDEX.md | `INDEX.md` |
| Scheduled task prompt | `research/# Scheduled Task.txt` |
| Telegram reports | `research/# Chat Thread.txt` |
| Autogram platform docs | `autogram.md` |

Target GitHub repositories remain publicly accessible:
- https://github.com/novatic14/MANPADS-System-Launcher-and-Rocket
- https://github.com/novatic14/Distributed-Camera-Node-Tracking-System
