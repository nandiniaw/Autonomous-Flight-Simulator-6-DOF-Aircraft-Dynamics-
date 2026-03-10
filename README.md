# Autonomous-Flight-Simulator-6-DOF-Aircraft-Dynamics-
A real-time 6-DOF aircraft flight dynamics simulator developed in MATLAB/Simulink 
using the Research Civil Aircraft Model (RCAM), built as part of Team Albatross's 
avionics development for SAE Aero Design competitions.

## Overview
This simulator models the complete flight dynamics of a fixed-wing aircraft including:
- 6 Degrees of Freedom (6-DOF) rigid body dynamics
- Aerodynamic and physical behaviour based on the RCAM model
- Geodetic position, velocity, and orientation computation
- Trim analysis for steady-state flight conditions
- Linearisation for control system design
- Joystick-based control surface input mapping

## Repository Structure
```
├── rcams.slx                      # Main 6-DOF flight dynamics Simulink model
├── rcamm.m                        # RCAM aerodynamic model (MATLAB)
├── navcomb.slx                    # Combined navigation model
├── geodetic.slx                   # Geodetic equations model
├── geodetic_position_calculate.slx # Position calculation block
├── geodeticcall.m                 # Geodetic initialisation script
├── initialiseGEODETIC.m           # Geodetic parameter setup
├── initialisevariables.m          # Global variable initialisation
├── initialisejoystick.m           # Joystick input configuration
├── TRIMRcam.slx                   # Trim analysis Simulink model
├── TRIMRCAM.m                     # Trim computation script
├── trim.m                         # Trim condition solver
├── cost_straight_level.m          # Cost function for straight & level flight
├── linearise.m                    # Linearisation script
└── ImplicitLinmod.m               # Implicit linearisation method
```

## Simulation Results
The simulation successfully validated realistic aircraft behaviour:

| Parameter | Result |
|-----------|--------|
| Cruise velocity | 22–25 m/s (stable after 8–10s transition) |
| Roll/Pitch oscillations | Initial 12–15° with 2° trim overshoot |
| Yaw turn rate | 3–5°/s under rudder input |
| Aileron deflection | 18° |
| Elevator deflection | 20° |
| Rudder deflection | 15° |

## How to Run

### Prerequisites
- MATLAB R2021a or later
- Simulink
- Aerospace Toolbox (recommended)

### Steps
1. Clone the repository
```bash
git clone https://github.com/yourusername/simulink-autonomous-flight-simulator.git
```
2. Open MATLAB and navigate to the project folder
3. Run the initialisation script first:
```matlab
initialisevariables
initialiseGEODETIC
initialisejoystick
```
4. Open and run `rcams.slx` for full flight simulation
5. For trim analysis, run `TRIMRCAM.m`
6. For linearisation, run `linearise.m`

## Key Components

### RCAM Model
The Research Civil Aircraft Model (RCAM) is a benchmark nonlinear aircraft model 
used for control system design and validation. It models full aerodynamic forces, 
moments, and equations of motion.

### Geodetic Navigation
Integrates navigation and geodetic equations to compute aircraft position, velocity, 
and orientation relative to Earth — validated against expected flight dynamics outputs.

### Trim & Linearisation
- Trim analysis finds the steady-state control inputs for straight and level flight
- Linearisation produces a state-space model used for classical control design

## Tech Stack
- MATLAB
- Simulink
- Aerospace Toolbox

## Related Work
This simulator was developed as part of **Team Albatross** avionics work and directly 
supported the development of RC aircraft for:
- SAE Aero Design West 2025 — 4th in Asia Pacific
- SAE ISSDDC 2025 — 1st Place Best CFD

## Author
**Nandini Walia**
B.Tech EEE, Vellore Institute of Technology
[linkedin.com/in/nandiniwalia](https://linkedin.com/in/nandiniwalia)
