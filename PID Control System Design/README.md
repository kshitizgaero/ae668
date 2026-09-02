# PID Control System Design & Simulink Simulation

**Course:** AE668 – Computational Aeromechanics and Control of UAVs
**Instructor:** Prof. Navrose, Helicopter and VTOL Lab, Department of Aerospace Engineering, IIT Kanpur
**Type:** Group Project
**Duration:** Jan 2026 – Apr 2026

## Overview

This project designs and analyzes a PID controller for a second-order plant, using classical control-theory tools (root locus and Routh-Hurwitz criteria) to characterize stability across a range of gains, and validates the results through Simulink simulation.

## Objectives

- Tune a PID controller to achieve critical damping for a second-order system
- Map out stability behavior across a range of controller gains
- Simplify the control design via pole-zero cancellation

## Methodology

### 1. Controller Design & Tuning
- Designed and tuned a PID controller for a second-order plant
- Used root-locus analysis and the Routh-Hurwitz stability criterion to determine gain boundaries
- Identified critical damping at **K = 5.83**, achieving zero overshoot with the fastest settling time

### 2. Stability Regime Mapping
- Analyzed system response across multiple gain values:
  - **K = 1** → underdamped, oscillatory response
  - **K = 6, K = 10** → stable, overdamped response
- Validated all cases through Simulink step-response simulation

### 3. Pole-Zero Cancellation
- Performed pole-zero cancellation to eliminate a dominant pole at **p = -1**
- Simplified the system order, reducing control-design complexity without sacrificing performance

## Key Results

| Gain (K) | Response | Notes |
|---|---|---|
| 1 | Underdamped | Oscillatory |
| 5.83 | Critically damped | Zero overshoot, fastest settling time |
| 6 | Overdamped | Stable |
| 10 | Overdamped | Stable |

- Dominant pole at p = -1 eliminated via pole-zero cancellation, simplifying system order

## Tools Used
- MATLAB (root locus, Routh-Hurwitz analysis)
- Simulink (step-response simulation and validation)

## Repository Structure


## Author
Kshitiz Gupta — MS (Research), Department of Aerospace Engineering, IIT Kanpur
