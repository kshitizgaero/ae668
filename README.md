# Conceptual Design, Multi-Fidelity Aerodynamics, and Flight-Control Simulation of a Lifting-Wing Quadcopter

**Course:** AE668 – Computational Aeromechanics and Control of UAVs
**Instructor:** Prof. Navrose, Helicopter and VTOL Lab, Department of Aerospace Engineering, IIT Kanpur
**Type:** Individual Project
**Duration:** Jan 2026 – Apr 2026

## Overview

This project explores the conceptual design, aerodynamic analysis, and flight-control simulation of a lifting-wing quadcopter — a hybrid configuration that combines multirotor hover capability with fixed-wing lift generation for efficient forward flight. The goal was to quantify the cruise-efficiency benefits of the wing over a purely hover-based multirotor and to validate the design through progressively higher-fidelity analysis, from conceptual sizing to CFD to closed-loop control simulation.

## Objectives

- Size a lifting-wing quadcopter for a 4 kg MTOW with a 1 kg payload capacity
- Compare aerodynamic performance across solver fidelities (panel method vs. RANS CFD)
- Assess structural adequacy of the airframe under representative aerodynamic loading
- Simulate closed-loop flight-control behavior across the full hover-cruise-hover mission profile

## Methodology

### 1. Conceptual Sizing
- Mission-based sizing performed in MATLAB to establish the design point
- BEMT-based propulsion sizing combined with a multidisciplinary design optimization (MDO) study sweeping cruise velocity, angle of attack, disk loading, thrust coefficient, and figure of merit
- Benchmarked the resulting configuration against comparable eVTOL platforms (VertiKUL2, Amazon Prime Air MK30, FIXAR 025) to quantify cruise-efficiency gains over hover-only flight

### 2. Multi-Fidelity Aerodynamic Analysis
- Low-fidelity: FlightStream panel-method solver, run in both propeller-on and propeller-off configurations
- High-fidelity: ANSYS Fluent RANS simulations using the k-ω SST turbulence model on a ~1M-cell poly-hexcore mesh with y+ ≈ 1 boundary-layer resolution
- Grid-convergence and validation studies were performed to verify the CFD predictions
- Quantified discrepancies in lift-curve slope (CL-α) and pitching-moment slope (Cmy-α) between the two solvers

### 3. Structural and Modal Analysis
- Static-structural analysis in ANSYS Workbench under an 80 N representative aerodynamic load, evaluating maximum deformation, principal stress, and strain energy
- Modal analysis to extract the first five natural frequencies of the airframe (1st mode ≈ 508 Hz)

### 4. Flight-Control Simulation
- Closed-loop flight dynamics simulated in MATLAB/Simulink across the full mission: hover climb → transition → cruise → transition → hover descent
- Identified that performance degrades beyond approximately 20 m/s cruise speed
- Found that a lower (~45°) wing-install angle reduces transition control complexity relative to a tail-sitter configuration

## Key Results

| Metric | Result |
|---|---|
| Design MTOW | 4 kg (1 kg payload) |
| Mesh (CFD) | ~1M cells, poly-hexcore, y+ ≈ 1 |
| 1st structural mode | ≈ 508 Hz |
| Cruise speed limit | ~20 m/s before performance degradation |
| Wing install angle | ~45° (reduces transition complexity vs. tail-sitter) |

## Tools Used
- **Sizing & Control:** MATLAB, Simulink
- **Aerodynamics:** FlightStream, ANSYS Fluent
- **Structures:** ANSYS Workbench
- **Meshing:** Poly-hexcore mesh generation with boundary-layer resolution

## Repository Structure
