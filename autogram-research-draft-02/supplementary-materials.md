# Supplementary Materials

**For:** "Progressive Technical Deepening Through Autonomous Scheduled Agent Interaction on a Hybrid Human-AI Social Platform: A Case Study"

---

## A. Complete Technical Suggestions Catalog

### Cycle 1 — Initial Code Review (Note 001)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Madgwick sensor fusion algorithm | Sensor fusion | Moderate (established) | $0 |
| 2 | Cascaded PID (outer rate + inner position) | Control | Moderate (established) | $0 |
| 3 | Differential canard control | Actuator | Moderate | $0 |
| 4 | LoRa telemetry recommendation | Communication | Moderate (for project) | ~$8 |
| 5 | Onboard flash logging | Data recording | Moderate | $0 |
| 6 | Servo upgrade path (MG90S) | Actuator | Moderate | ~$3 |
| 7 | BNO085 IMU upgrade | Sensor | Moderate | ~$12 |
| 8 | TVC consideration for future | Actuator architecture | Moderate | ~$10-20 |
| 9 | Fire control bridge | System integration | Moderate | $0 |

### Cycle 2 — Detailed Analysis and Prioritized Roadmap (Note 002)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Complementary filter for IMU fusion | Sensor fusion | Moderate | $0 |
| 2 | Cascaded PID with anti-windup | Control | Moderate | $0 |
| 3 | Dual-axis stabilization (pitch canards) | Actuator | Moderate-High | ~$5 |
| 4 | Thrust Vector Control (revisited) | Actuator | Moderate | ~$10 |
| 5 | SD card logging at 100Hz+ | Data recording | Moderate | ~$2 |
| 6 | SX1262 LoRa module (5-10km) | Communication | Moderate-High | ~$8 |
| 7 | Dual-band communication (WiFi+LoRa) | Communication | Moderate | ~$0 |
| 8 | Kalman filter race condition fix | Software | **Novel (bug found)** | $0 |
| 9 | Measurement gating (Mahalanobis distance) | Software | High | $0 |
| 10 | Custom YOLOv8-nano retraining | Computer vision | High | $0 |
| 11 | EMA smoothing for triangulation | Computer vision | Moderate | $0 |
| 12 | 18650 battery pack replacement | Power | Moderate | ~$12 |
| 13 | NTP time synchronization | Software | High | $0 |
| 14 | Web configuration page (remove hardcoded creds) | Security | **Novel for project** | $0 |

**Bugs Identified:**
- Kalman filter threading race condition in Python tracking code
- Missing measurement gating for false positive rejection
- Hardcoded credentials committed to repository
- Brownout detection disabled as workaround (symptom, not fix)

### Cycle 3 — Advanced Control and Guidance (Note 003)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Dynamic-pressure gain scheduling | Control | **High** | $0 |
| 2 | Feed-forward rate command | Control | **High** | $0 |
| 3 | Actuator rate limiting model | Control | Moderate | ~5 lines code |
| 4 | Canard servo blowback detection | Actuator | **Very High** | $0.50-10 |
| 5 | Pitot tube airspeed (MPXV7002DP) | Sensor | **High** | $5 |
| 6 | Gravity turn follower guidance | Guidance | **Very High** | $0 |
| 7 | Proportional navigation (PN) guidance | Guidance | **Very High** | ~10 lines code |
| 8 | Dual-deployment recovery system | Recovery | **High** | ~$1 |
| 9 | Launch rail departure logic | Control | High | $0 |
| 10 | Post-flight analysis pipeline | Development | High | $0 |

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
| 11 | Roll-yaw coupling with 4x3 mixing matrix | Control | **Very High** | $0 |

### Cycle 5 — Structural Dynamics and Propulsion (Note 005)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | Accelerometer saturation detection (8G range) | Sensor | **Extremely High** | $0 |
| 2 | 16G range switching for ignition | Sensor | **Extremely High** | $0 |
| 3 | Fin flutter speed analysis | Structural | **Revolutionary** | $0 (analysis) |
| 4 | Carbon fiber fins for flutter suppression | Structural | **Very High** | ~$10 |
| 5 | Ground vibration testing protocol | Testing | High | $0 |
| 6 | Custom KNSB propellant grain geometry | Propulsion | **Revolutionary** | $5-8/motor |
| 7 | PID-friendly thrust curve profiling | Propulsion | **Very High** | $0 |
| 8 | Cd vs Mach extraction from flight data | Aerodynamics | **Very High** | $0 |
| 9 | Wind sensing (vane/anemometer) | Environmental | High | $3-8 |
| 10 | Adaptive launch angle correction | Guidance | High | $0 |
| 11 | Onboard ESP32-CAM on rocket | Verification | High | ~$8 |
| 12 | OTA firmware updates for all nodes | Development | **Very High** | $0 |

### Cycle 6 — Physical Data Quality Foundations (Note 006)

| # | Suggestion | Subsystem | Novelty | Est. Cost |
|---|-----------|-----------|---------|-----------|
| 1 | IMU vibration isolation (Sorbothane) | Physical | **Revolutionary** | $2-5 |
| 2 | 4th-order Butterworth software bandpass | Physical | High | $0 |
| 3 | Thermal management (cork insulation) | Thermal | **Revolutionary** | ~$1 |
| 4 | Gyro temperature compensation table | Thermal | **Very High** | ~20 lines code |
| 5 | Cold gas RCS (CO2) for zero-airspeed | Control | **Revolutionary** | $15-20 |
| 6 | Multi-stage flight architecture | Architecture | **Revolutionary** | ~$8 |
| 7 | Accelerometer-based separation detection | Architecture | **Very High** | $0 |
| 8 | Dual-IMU voting algorithm | Redundancy | **Very High** | $2-15 |
| 9 | ESP-MESH networking for cameras | Network | **High** | $0 (~50 lines code) |
| 10 | Environmental monitoring station | Environmental | High | $15-25 |
| 11 | Dual-station wind gradient estimation | Environmental | High | $0 |

---

## B. Complete Coverage Matrix

Subsystems covered (X = addressed in cycle):

| Subsystem | C1 | C2 | C3 | C4 | C5 | C6 |
|-----------|----|----|----|----|----|----|
| Sensor fusion algorithms | X | X | X | | | |
| IMU hardware selection | X | X | | | | |
| Attitude estimation (Madgwick) | X | | | | | |
| Cascaded PID control | X | X | | | | |
| Gain scheduling | | | X | | | |
| Feed-forward control | | | X | | | |
| Actuator rate limiting | | | X | | | |
| Canard deflection control | X | | | | | |
| Dual-axis (pitch+roll) | | X | | | | |
| TVC (thrust vector control) | X | X | | | | |
| Cold gas RCS | | | | | | X |
| LoRa telemetry | X | X | | | | |
| Dual-band comm (WiFi+LoRa) | | X | | | | |
| Telemetry checksum/framing | | | | X | | |
| ESP-MESH networking | | | | | | X |
| OTA firmware updates | | | | | X | |
| SD card data logging | | X | | | | |
| Onboard flash logging | X | | | | | |
| 18650 battery system | X | X | | | | |
| Voltage monitoring | X | X | | | | |
| Supercapacitor buffer | | | | | | |
| YOLO custom retraining | | X | | | | |
| Measurement gating | | X | | | | |
| NTP time sync | | X | X | | | |
| Kalman thread safety fix | | X | | | | |
| Pitot tube airspeed | | | X | | | |
| Accelerometer saturation | | | | | X | |
| IMU vibration isolation | | | | | | X |
| IMU dual-voting redundancy | | | | | | X |
| Thermal management (heat) | | | | | | X |
| Computer vision triangulation | | X | | | | |
| Computer vision EMA smoothing | | X | | | | |
| Unity visualization | | X | | | | |
| Guidance (gravity turn) | | | X | | | |
| Guidance (proportional nav) | | | X | | | |
| Launch rail departure logic | | | X | | | |
| Wind sensing | | | | | X | X |
| Adaptive launch angle | | | | | X | |
| Environmental monitoring station | | | | | | X |
| Dual-deployment recovery | | | X | | | |
| Flight termination system | | | | X | | |
| Ignition system (continuity) | | | | X | | |
| Ignition redundancy | | | | X | | |
| Smart ignition timing | | | | X | | |
| HIL bench testing | | | | X | | | |
| Post-flight analysis pipeline | | | X | | | |
| Aerodynamic canard sizing | | | | X | | |
| CP-CG analysis | | | | X | | |
| Cl_delta estimation | | | | X | | |
| Fin flutter analysis | | | | | X | |
| Aeroelastic stability | | | | | X | |
| Carbon fiber fins | | | | | X | |
| Propellant grain geometry | | | | | X | |
| Thrust curve profiling | | | | | X | |
| Drag Cd extraction from data | | | | | X | |
| Multi-stage architecture | | | | | | X |
| Accelerometer separation detect | | | | | | X |
| Dual-IMU voting | | | | | | X |
| Roll-yaw coupling (4x3 matrix) | | | | X | | |
| Compass timing interference | | | | X | | |
| Web config (security fix) | | X | | | | |
| Hardcoded credential removal | | X | | | | |
| Onboard rocket camera | | | | | X | |
| Network topology (mesh) | | | | | | X |

**Total subsystem categories addressed: 54** (across 6 cycles, with some overlap)
**Unique subsystem categories addressed: 29** (distinct engineering domains)

---

## C. Novel Ideas Ranked by Impact

The following ideas were classified as novel (not present in any existing thread comment, GitHub issue, or pull request) and ranked by estimated impact on the project:

### Tier 1 — Paradigm-Shifting

1. **IMU vibration isolation (Cycle 6):** Identified that physical vibration from motor (200-800 Hz) corrupts all sensor fusion algorithms simultaneously. $2-5 Sorbothane solution improves every algorithm. Paradigm shift: fix physical data quality before improving algorithms.

2. **Cold gas RCS for zero-airspeed control (Cycle 6):** Identified fundamental limitation of aerodynamic control surfaces (need dynamic pressure). CO2 cartridge + solenoid nozzles enable attitude control at apogee. Previously undiscussed in any thread or issue.

3. **Custom KNSB propellant grain geometry (Cycle 5):** Moving from off-the-shelf motor selection to custom grain design for PID-friendly thrust curves. Eliminates need for gain scheduling. Entirely new domain for the project.

4. **Fin flutter analysis with aeroelastic equations (Cycle 5):** First structural dynamics analysis. Identified that PLA fin flutter speed (150-250 m/s) is dangerously close to E-class flight speeds. Equations provided for estimation.

5. **Multi-stage flight architecture (Cycle 6):** Proposed two-stage rocket with accelerometer-based separation detection. Single biggest performance improvement available (2-3x altitude for D+D).

### Tier 2 — Very High Impact

6. **Hardware-in-the-loop bench testing (Cycle 4):** Simulated flight data driving real PID loop for desk-based tuning. Replaces expensive live launches with iterative bench testing.

7. **Proportional navigation guidance (Cycle 3):** Classic guided missile law applied to amateur rocketry. ~10 lines of code for active trajectory guidance.

8. **Dynamic-pressure gain scheduling (Cycle 3):** Lookup table indexed by altitude/velocity for PID gain adaptation. Physics-based approach to control authority variation.

9. **Flight termination system (Cycle 4):** LoRa-based in-flight abort command. Safety-critical capability not present in original design.

10. **Aerodynamic canard sizing analysis (Cycle 4):** First principled canard design (CP-CG, Cl_delta) replacing empirical motor-per-motor tuning.

### Tier 3 — High Impact

11. **Dual-deployment recovery (Cycle 3):** Barometric apogee detection + drogue + main deployment for rocket reusability.

12. **Telemetry XOR checksum (Cycle 4):** Silent data corruption from motor EMI identified and addressed.

13. **Drag coefficient extraction (Cycle 5):** Extract Cd vs Mach from coast phase flight data to validate simulations.

14. **Onboard rocket camera (Cycle 5):** Visual verification of canard deflection, rail departure, and exhaust plume.

15. **OTA firmware updates (Cycle 5):** WiFi-based updates for all 4-6 ESP32 nodes, eliminating USB flashing bottleneck.

---

## D. Progression Note Summaries

### Note 001 (2026-04-03)
Initial code review of both GitHub repositories. Identified basic improvement areas: sensor fusion (Madgwick), cascaded PID, LoRa telemetry, servo upgrades, BNO085 IMU, TVC consideration. Broad but surface-level assessment.

### Note 002 (2026-04-03)
Detailed code-level analysis. Found actual bugs: Kalman filter race condition, missing measurement gating, hardcoded credentials. Organized 14 improvements into prioritized roadmap with BOM estimates ($96 -> $130-150). First note with systematic organization.

### Note 003 (2026-04-03)
Entered advanced control territory. Dynamic-pressure gain scheduling, proportional navigation, canard servo blowback, pitot tube airspeed, dual-deployment recovery. Proposed phased development roadmap v1.5 through v3.0.

### Note 004 (2026-04-03)
Shifted to reliability engineering. Ignition system flaws, telemetry protocol integrity, HIL bench testing, aerodynamic canard sizing, flight termination, compass interference, roll-yaw coupling. First note to address safety-critical infrastructure.

### Note 005 (2026-04-03)
Entered structural dynamics and propulsion. Accelerometer saturation during ignition, fin flutter analysis, custom propellant grain geometry, drag coefficient extraction, wind sensing, onboard camera, OTA updates. Broadest domain expansion.

### Note 006 (2026-04-03)
Paradigm shift to physical foundations. IMU vibration isolation, thermal management, cold gas RCS, multi-stage architecture, dual-IMU voting, ESP-MESH, environmental monitoring. Identified that physical data quality is prerequisite for all algorithmic improvements.

---

## E. Data Availability

All data from this study is publicly available:
- Progression notes: `artifacts/rocket-launcher/progression-note-00X.md` (X = 1-6)
- Index file: `INDEX.md`
- Scheduled task prompt: `research/# Scheduled Task.txt`
- Telegram reports: `research/# Chat Thread.txt`
- Autogram documentation: `autogram.md`

The target GitHub repositories for the rocket launcher project remain publicly accessible.
