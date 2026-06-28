Task for tomorrow: Next, start transmissibility.m in 02_matlab/

# Vibration Isolation Module (VIM)

The Vibration Isolation Module is my first mechanical engineering personal project. I'm using it to develop and learn the skills essential to real product development and real-world problem solving — taking one system from first-principles model all the way to validated hardware.

**The build:** A passive parallel-link vibration isolation module for a last-mile delivery robot's camera/LiDAR payload (2.5 kg).

**The pipeline:** MATLAB SDOF model → SolidWorks CAD → ANSYS FEA → fabrication → Arduino/MPU6050 validation.

**The targets:** ≥40% RMS acceleration reduction over the 5–30 Hz band, and model-vs-test agreement within 10% on natural frequency.

## Why this design
A delivery robot's wheels and terrain feed vibration (~5–30 Hz) straight into its sensors, blurring camera and LiDAR data. A passive isolation stage tuned to a low natural frequency (3.5 Hz) lets the payload "float" above that band. The parallel 4-bar linkage keeps the payload level (pure vertical travel) instead of tilting, which a simple spring mount can't do.

## Key specs
| Parameter | Value |
|---|---|
| Payload mass | 2.5 kg |
| Total stiffness | 1200 N/m |
| Natural frequency | 3.5 Hz |
| Damping ratio (target) | 0.10–0.15 |
| Max stroke | ±15 mm |
| Isolation band | ~5–30 Hz |

## Repository structure
- `01_requirements/` — requirements, targets, verification matrix
- `02_matlab/` — SDOF model: transmissibility, PSD response, bump response
- `03_cad/` — SolidWorks parts, assembly, drawings
- `04_fea/` — ANSYS static + modal analysis
- `05_fabrication/` — fab files, BOM, build photos
- `06_testing/` — DAQ code, test data, analysis
- `07_report/` — final writeup and results

## Status
🔧 In progress — started June 2026.

---
*Built by Abhinav Singh — mechanical engineering student, Purdue University.*
