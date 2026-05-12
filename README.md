# Portfolio-de-proyectos
#!/bin/bash
# ─────────────────────────────────────────────
# Pelayo de la Mata — Portfolio Repository Setup
# Run once from the folder where you want the repo
# ─────────────────────────────────────────────

set -e

REPO="pelayo-portfolio"
mkdir -p "$REPO"
cd "$REPO"
git init

# ── Folder structure ──────────────────────────
folders=(
  "01_hydraulic-network"
  "02_climate-statistics"
  "03_f1-banked-corner"
  "04_suv-suspension"
  "05_motorcycle-plant"
  "06_spaghetti-truss"
  "07_commodity-trading"
  "08_abb-robotics"
  "09_plc-automation-sorting"
  "10_kia-drivesafe-hackathon"
)

for f in "${folders[@]}"; do
  mkdir -p "$f"
  touch "$f/.gitkeep"
done

# ── Root README ───────────────────────────────
cat > README.md << 'EOF'
# Pelayo de la Mata — Engineering Portfolio

**B.Eng. Industrial Systems Engineering · UFV Madrid · Graduating 2027**

📧 pelayodelamataderamos@gmail.com · [LinkedIn](https://www.linkedin.com/in/pelayo-de-la-mata-de-ramos-609980378)

---

## Projects

| # | Project | Area | Tools |
|---|---------|------|-------|
| 01 | [Hydraulic Network Design](#01-hydraulic-network-design) | Fluid Mechanics | MATLAB · EPANET |
| 02 | [Climate Statistics — Madrid](#02-climate-statistics--madrid) | Statistics | Python · Excel |
| 03 | [F1 Banked Corner Optimization](#03-f1-banked-corner-optimization) | Calculus · Mechanics | MATLAB · SolidWorks |
| 04 | [SUV Suspension ODE Model](#04-suv-suspension-ode-model) | ODEs · Dynamics | MATLAB · SolidWorks |
| 05 | [Motorcycle Manufacturing Plant](#05-motorcycle-manufacturing-plant) | Industrial Design | Excel |
| 06 | [Spaghetti Truss Competition](#06-spaghetti-truss-competition) | Structural Mechanics | FTool · SolidWorks |
| 07 | [Commodity Trading Simulation — #1 in class](#07-commodity-trading-simulation--1-in-class) | Finance · Markets | Excel · TradingView |
| 08 | [ABB IRB1200 Robot Programming](#08-abb-irb1200-robot-programming) | Robotics | Rhino 8 · Grasshopper |
| 09 | [PLC Automation — Sorting by Weight](#09-plc-automation--sorting-by-weight) | Automation | TIA Portal V18 · Factory IO |
| 10 | [KIA × UFV Hackathon — DriveSafe](#10-kia--ufw-hackathon--drivesafe) | Product · Connected Vehicle | CARLA · MATLAB Simulink |

---

## 01 Hydraulic Network Design
**Subject:** Fluid Mechanics · 2024/25 · Team of 4

Pressurised water supply network for the UFV campus — 5.5 km of pipe, 45 m of elevation change, sized in MATLAB and cross-checked in EPANET.

**Key results:** 120,000 L/h · Pump 248.4 kW · CAPEX €89,317 · Annual energy cost €67,073/yr

📁 `01_hydraulic-network/` — project report, MATLAB scripts, EPANET model

---

## 02 Climate Statistics — Madrid
**Subject:** Statistics · 2024/25 · Team of 3

72 monthly regression models (12 months × 6 NOAA stations, 1945–present) projecting Madrid temperatures to 2050 and testing for statistically significant warming.

**Key results:** TMAX +0.18°C · TMIN +0.50°C · Precipitation −219 mm vs 2020 · 95% CI excludes zero

📁 `02_climate-statistics/` — project report, Excel regression models

---

## 03 F1 Banked Corner Optimization
**Subject:** Calculus II · 2024/25

Grip-limited speed analysis on the 2026 Madrid GP banked hairpin (30° banking, 217° arc) for the Red Bull RB20. Racing line comparison (inside/apex/outside/ellipse) and 3D geometry in SolidWorks.

**Key results:** Outside line fastest (4.20 s transit) despite longest arc. Ellipse (cone-plane intersection) is geometrically smoothest but slower (5.41 s).

📁 `03_f1-banked-corner/` — project report, MATLAB scripts, SolidWorks model

---

## 04 SUV Suspension ODE Model
**Subject:** ODEs · 2024/25

Second-order ODE model of a 1,500 kg SUV suspension comparing a functional damper (ζ = 0.276) against one degraded to 10% of its original hydraulic constant. Scenarios: speed bump at 50 km/h and tight corner at R = 6 m.

**Key results:** Roll angle 21.77° (functional) vs 75.95° (degraded) → rollover certain above 90°. Oscillations unsettled >60 s in degraded case.

📁 `04_suv-suspension/` — project report, MATLAB scripts, SolidWorks speed bump model

---

## 05 Motorcycle Manufacturing Plant
**Subject:** Business Organisation · Jan 2026 · Team of 8

Industrial design of a 125cc café racer plant in Madrid. Scope: product definition, location selection, 7-stage U-line assembly, supply chain, workforce and 10-year financial plan.

**Key results:** Location: Pinto (4.50/5) · Plant 20,000 m² · Takt Time 160 min/unit · IRR 114% · Payback 2.12 years

📁 `05_motorcycle-plant/` — full report, financial model, presentation

---

## 06 Spaghetti Truss Competition
**Subject:** Structural Mechanics · Jan 2026

Howe-type truss (80 cm × 8 cm) built from spaghetti for the 2nd UFV competition. Full method-of-joints analysis, Euler buckling calculation and experimental test to failure.

**Key results:** 37 members · 5 zero-force members · Max compression −4P in members 16/20 · Experimental collapse 38.8 N via local buckling — location confirmed by analysis.

📁 `06_spaghetti-truss/` — project report, SolidWorks model, FTool file

---

## 07 Commodity Trading Simulation — #1 in class
**Subject:** Trading de Materias Primas · 2025/26 · Team of 5 · **1st place**

10-week macro-driven trading simulation ($150,000 USD virtual portfolio) during the US–Israel–Iran conflict and Strait of Hormuz closure. Ranked 1st out of all class groups at UFV.

**Key results:** $150,000 → $194,500 (+29.67%) · 10 operations · 8 profitable · Win rate 80% · Best trade: Platinum +17.33% in <2 weeks · Energy futures: +19.56%

📁 `07_commodity-trading/` — final report (memoria), Excel operation register

---

## 08 ABB IRB1200 Robot Programming
**Subject:** Robotics & Digital Fabrication · 2025/26 · Team of 2

ABB IRB1200 (6-axis) programmed entirely in Grasshopper (Rhino 8) using the unimelb-irb1200 open-source library. Draws initials ERC + PdlM across two independent spatial planes with a mid-sequence tool change. No teach-pendant.

**Key results:** 5 modular Grasshopper clusters · Dual-plane toolpath · Tool change sub-routine · Full simulation validated before physical execution.

📁 `08_abb-robotics/` — Grasshopper file (.gh), Rhino file, simulation video, script screenshot

---

## 09 PLC Automation — Sorting by Weight
**Subject:** Industrial Automation · 2025/26 · Team of 2

TIA Portal V18 Ladder program for a Factory IO weight-sorting scene. 10-state state machine, auto/manual modes, three-layer alarm architecture (sensor + motor + SCL handler) and full I/O documentation.

**Key results:** 3-channel sorting (<8 kg right · 8–10 kg left · >15 kg alarm/front) · 10 sensor alarms (DB7–DB15) · 10 motor alarms (DB16–DB23) · CTU zone counters

📁 `09_plc-automation-sorting/` — TIA Portal project (.zip), Factory IO scene, Excel I/O table, state diagrams

---

## 10 KIA × UFV Hackathon — DriveSafe
**Event:** KIA × UFV Innovation Challenge · 2025/26 · Team of 5

Two-day hackathon with KIA engineers. Challenge: design a connected vehicle feature. Our proposal: real-time biometric monitoring (ECG + SpO2) to detect medical emergencies and automatically stop the vehicle safely. Didn't win — but the problem was real.

**Concept:** 12–15% of fatal accidents involve a medical condition · Detection pipeline: ECG + SpO2 → preprocessing → health assessment algorithm → vehicle control → safe stop + emergency alert · Simulation: CARLA + MATLAB Simulink

📁 `10_kia-drivesafe-hackathon/` — pitch deck (.pptx)

---

*B.Eng. Industrial Systems Engineering · UFV Madrid · 2023–2027*
EOF

# ── Folder READMEs ────────────────────────────

cat > 01_hydraulic-network/README.md << 'EOF'
# 01 — Hydraulic Network Design & Sizing

**Subject:** Fluid Mechanics · UFV · 2024/25 · Team of 4

## Files
- `report.pdf` — full project report
- `matlab/` — MATLAB scripts (Swamee-Jain, pump sizing, cost analysis)
- `epanet/` — EPANET network model (.net)

## Summary
Steady-state hydraulic network from the UFV reservoir (700 m elevation) to two higher-elevation buildings via a 5,500 m DN110 main pipe and two DN63 branches.
- Flow: 120,000 L/h total · Pump: 248.4 kW (η = 70%)
- Manometric head: 531.8 m (governing case: new building branch)
- CAPEX: €89,317 · Annual energy cost: €67,073/yr
EOF

cat > 02_climate-statistics/README.md << 'EOF'
# 02 — Climate Statistics — Madrid 2050 Projection

**Subject:** Statistics (Mathematics II) · UFV · 2024/25 · Team of 3

## Files
- `report.pdf` — full project report with regression tables and confidence intervals
- `data/` — cleaned NOAA monthly datasets (6 stations, 1945–present)
- `models/` — Excel regression workbooks (72 models: 12 months × 6 stations)

## Summary
72 linear regression models projecting Madrid temperatures and precipitation to 2050.
- 2050 vs 2020: TMAX +0.18°C · TMIN +0.50°C · Precipitation −219 mm
- 95% confidence intervals exclude zero → statistically significant warming confirmed
- Point forecast for 23 May 2025: ±1°C accuracy across all 6 stations
EOF

cat > 03_f1-banked-corner/README.md << 'EOF'
# 03 — F1 Banked Corner Optimization — 2026 Madrid GP

**Subject:** Calculus II · UFV · 2024/25

## Files
- `report.pdf` — full project report
- `matlab/` — racing line speed calculations, ellipse arc length, transit times
- `solidworks/` — 3D corner geometry model

## Summary
Grip-limited speed and racing line analysis on the 2026 Madrid GP banked hairpin (turns 9–12, 30° banking, 151 m inner radius, 217° arc). Reference car: Red Bull RB20, 798 kg.
- Outside line: fastest (4.20 s, vmax 523 km/h dry) despite longest arc
- Ideal ellipse: geometrically smoothest (cone-plane intersection) but slower (5.41 s)
- Three track conditions: μ = 0.9 / 0.7 / 0.5
EOF

cat > 04_suv-suspension/README.md << 'EOF'
# 04 — SUV Suspension ODE Model & Simulation

**Subject:** Ordinary Differential Equations · UFV · 2024/25

## Files
- `report.pdf` — full project report
- `matlab/` — ODE solver scripts for both damper states and two scenarios
- `solidworks/` — 3D speed bump geometry

## Summary
Mass-spring-damper model (k = 60,375 N/m, b = 2,625 Ns/m) for a 1,500 kg SUV under two scenarios: speed bump at 50 km/h and tight corner at R = 6 m.
- Functional damper ζ = 0.276 → oscillations settle ~3 s, roll angle 21.77°
- Degraded damper ζ' = 0.0276 → oscillations persist >60 s, roll angle 75.95° → rollover
EOF

cat > 05_motorcycle-plant/README.md << 'EOF'
# 05 — Motorcycle Manufacturing Plant — MM-125 Urban

**Subject:** Business Organisation · UFV · January 2026 · Team of 8

## Files
- `report.pdf` — full industrial design report
- `financial-model.xlsx` — 10-year P&L, IRR, NPV, break-even
- `presentation.pdf` — project pitch deck

## Summary
Design and launch plan for a 125cc café racer plant in Madrid (MM-125 Urban: 4-stroke, 15 hp, 130 kg). Production target: 60 units/month from Oct 2026.
- Location: Pinto (score 4.50/5 via multi-criteria model)
- Plant: 20,000 m² · 7-stage U-line · Takt Time 160 min/unit
- IRR: 114% · NPV: €18,321 · Payback: 2.12 years · Break-even: 508 units
EOF

cat > 06_spaghetti-truss/README.md << 'EOF'
# 06 — Spaghetti Truss — Structural Design & Competition

**Subject:** Structural Mechanics · UFV · January 2026

## Files
- `report.pdf` — full structural analysis report
- `solidworks/` — 3D truss model and axial force simulation
- `ftool/` — FTool verification file

## Summary
Howe-type truss (80 cm × 8 cm) designed, analysed and built from spaghetti for the 2nd UFV Spaghetti Truss Competition.
- 37 members · 5 zero-force members · Max compression −4P in members 16 and 20
- Central bracing clips halve effective buckling length (80 → 40 mm), quadrupling Euler critical load
- Experimental collapse: 38.8 N via local buckling — location confirmed by method of joints
EOF

cat > 07_commodity-trading/README.md << 'EOF'
# 07 — Commodity Trading Simulation — #1 in Class

**Subject:** Trading de Materias Primas para Ingenieros · UFV · 2025/26 · Team of 5
**Result: 1st place out of all class groups**

## Files
- `memoria.pdf` — full final report (strategy, operations, analysis, conclusions)
- `registro-operaciones.xlsx` — complete trade register with entry/exit prices, P&L, returns

## Summary
10-week macro-driven trading simulation ($150,000 USD virtual portfolio) during the US–Israel–Iran conflict and Strait of Hormuz closure (Feb–Apr 2026). Operated exclusively on Tuesdays and Thursdays.
- $150,000 → $194,500 · **+29.67% total return**
- 10 operations · 8 profitable · 2 at loss · Win rate 80%
- Best trade: Platinum futures +17.33% in <2 weeks
- Energy futures (Brent + Gas): +19.56% across 4 operations, all profitable
- Assets: Brent Crude (long + short), Gas Natural, Platinum, FCX, NEM, RIO, Repsol
EOF

cat > 08_abb-robotics/README.md << 'EOF'
# 08 — ABB IRB1200 Robot Programming

**Subject:** Robotics & Digital Fabrication · UFV · 2025/26 · Team of 2

## Files
- `grasshopper/` — .gh Grasshopper definition (5 modular clusters)
- `rhino/` — Rhino 8 scene file
- `video/` — simulation video
- `screenshots/` — Grasshopper script overview

## Summary
ABB IRB1200 (6-axis industrial robot) programmed entirely in Grasshopper (Rhino 8) using the unimelb-irb1200 open-source component library. No teach-pendant — every robot instruction generated parametrically from input geometry.
- Draws initials ERC + PdlM across two independent spatial planes
- Mid-sequence tool change programmed as a sub-routine
- 5 colour-coded Grasshopper clusters: geometry input, plane definition, path planning, tool change, robot output
- Full simulation validated in Rhino 8 before physical execution
EOF

cat > 09_plc-automation-sorting/README.md << 'EOF'
# 09 — PLC Automation — Sorting by Weight

**Subject:** Industrial Automation · UFV · 2025/26 · Team of 2

## Files
- `tia-portal/` — TIA Portal V18 project (.zip)
- `factory-io/` — Factory IO scene (.factoryio)
- `documentation/` — Excel I/O table, alarm list, tag list
- `diagrams/` — state machine diagrams (full + structured)

## Summary
Ladder (LAD) program in TIA Portal V18 for a weight-based sorting system simulated in Factory IO.
- 10-state state machine (E0–E10): idle → entry → scale → classify → route → deliver → reset
- 3-channel sorting: <8 kg → right · 8–10 kg → left · >15 kg → alarm + front stop
- Auto/manual modes with ENCLAVAMIENTO interlocking
- Alarm architecture: E-STOP (NC) + 10 sensor alarms (DB7–DB15) + 10 motor alarms (DB16–DB23) + SCL handler (DB10)
- CTU zone counters per output channel
EOF

cat > 10_kia-drivesafe-hackathon/README.md << 'EOF'
# 10 — KIA × UFV Hackathon — DriveSafe

**Event:** KIA × UFV Innovation Challenge · 2025/26 · Team of 5

## Files
- `KIADriveSafe_hackaton.pptx` — full pitch deck (6 slides)

## The idea
12–15% of fatal traffic accidents involve a medical condition in the driver. DriveSafe monitors the driver's biometrics in real time (ECG + SpO2 + stress), detects an emergency before loss of control, and acts automatically: safe stop, hazard lights, emergency call.

**Detection pipeline:**
ECG + SpO2 signal → preprocessing → health assessment algorithm → emergency flag → vehicle control system → safe stop + alert

**Simulation stack:**
- CARLA: autonomous driving simulator for realistic urban scenarios
- MATLAB Simulink: signal processing pipeline prototype (ECG/SpO2 → vehicle control)

**System response sequence:** reduce speed → activate hazard lights → find safe stopping point → contact emergency services → unlock doors for first responders → driver can cancel if false positive
EOF

# ── .gitignore ────────────────────────────────
cat > .gitignore << 'EOF'
.DS_Store
Thumbs.db
*.tmp
~$*
EOF

# ── Initial commit ────────────────────────────
git add .
git commit -m "Initial portfolio structure — 10 projects"

echo ""
echo "✅ Repository created: $REPO/"
echo ""
echo "Next steps:"
echo "  1. Go to github.com → New repository → name it 'pelayo-portfolio' (public)"
echo "  2. Copy the remote URL (e.g. https://github.com/YOUR_USERNAME/pelayo-portfolio.git)"
echo "  3. Run:"
echo "       cd $REPO"
echo "       git remote add origin YOUR_REMOTE_URL"
echo "       git push -u origin main"
echo "  4. Drop your project files into each numbered folder and run:"
echo "       git add . && git commit -m 'Add [project name] files' && git push"
