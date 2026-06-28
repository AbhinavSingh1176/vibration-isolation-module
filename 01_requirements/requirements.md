# VIM — Requirements & Design Targets

## Mission
Isolate a 2.5 kg camera/LiDAR payload on a last-mile delivery robot from chassis and terrain vibration, so sensor data stays clean.

## Functional Requirements
| ID | Requirement |
|---|---|
| FR1 | Reduce RMS vertical acceleration at the payload by ≥40% over a 5–30 Hz input band |
| FR2 | Support the 2.5 kg payload statically with deflection < 25 mm |
| FR3 | Allow ±15 mm dynamic stroke without hard-stop contact |
| FR4 | Keep the payload platform level (pure vertical translation, no tilt) via a parallel 4-bar linkage |

## Constraints
| ID | Constraint |
|---|---|
| C1 | Passive only — no powered actuators |
| C2 | Footprint ≤ 200 × 200 mm, height ≤ 150 mm |
| C3 | Module mass ≤ 1.5 kg (excluding payload) |
| C4 | Fabricable with waterjet + mill + 3D printer |
| C5 | Purchased-parts budget ≤ $120 |

## Key Design Parameters
| Parameter | Value |
|---|---|
| Payload mass, m | 2.5 kg |
| Total stiffness, k | 1200 N/m |
| Natural frequency, fn | 3.5 Hz |
| Damping ratio, ζ (target) | 0.10–0.15 |
| Max stroke | ±15 mm |

## Sanity Checks (hand calcs)
- **Natural frequency:** fn = (1/2π)·√(k/m) = (1/2π)·√(1200/2.5) = **3.49 Hz** ✓
- **Static deflection:** x = mg/k = (2.5 × 9.81)/1200 = **0.0204 m ≈ 20.4 mm** — under the 25 mm limit (FR2) ✓
- **Isolation onset:** isolation begins above √2·fn ≈ **4.9 Hz**, so the 5–30 Hz input band sits in the isolation region ✓

## Verification Matrix
| Req | Verified by | Result |
|---|---|---|
| FR1 | Accelerometer test, base-vs-payload PSD comparison | _TBD_ |
| FR2 | Static deflection measurement under 2.5 kg | _TBD_ |
| FR3 | Bump test, measure peak stroke vs ±15 mm | _TBD_ |
| FR4 | Visual / motion check during stroke | _TBD_ |
