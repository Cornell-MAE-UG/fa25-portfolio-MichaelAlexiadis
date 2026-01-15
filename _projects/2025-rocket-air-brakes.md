---
layout: project
title: "Rocket Air Brake System Dynamics"
image: /assets/images/airbrake.png
---

## Overview
This project was the final group project for **MAE 3260 – System Dynamics** with Prof. MacMartin. Our team designed and analyzed an **active rocket air brake system** intended to precisely control a rocket’s apogee using feedback control.

The objective was to model how deployable air brake flaps influence aerodynamic drag and velocity, and to design a controller capable of driving the rocket toward a target altitude while remaining stable in the presence of nonlinear dynamics and disturbances.

---

## Problem Statement
Unguided rockets are highly sensitive to variations in initial launch conditions, drag, and environmental disturbances such as wind gusts. These effects can lead to large deviations in apogee.

The goal of this project was to:
- Actively regulate rocket apogee using air brake deployment
- Reduce sensitivity to initial velocity variations
- Maintain stability despite nonlinear drag behavior
- Respect physical actuator limits

---

## Physical Modeling & Linearization
The dominant nonlinearity in the system arises from aerodynamic drag, which depends on the square of velocity and the effective frontal area of the air brakes.

To enable control-oriented analysis, we:
- Linearized the nonlinear drag force using a **first-order Taylor series expansion** about a nominal operating velocity
- Defined the system state as the deviation from this nominal velocity
- Introduced an aggregated parameter that combined air brake area and drag coefficient into a single effective control input

This approach preserved the physical intuition of the problem while enabling linear systems analysis near the operating point.

---

## State-Space Representation
After linearization, the system was expressed in state-space form, with:
- **State:** deviation from nominal velocity  
- **Input:** effective air brake deployment  
- **Output:** velocity deviation  

This representation allowed us to analyze system stability through eigenvalues and provided a foundation for controller design.

---

## Control Strategy
We implemented a **proportional feedback controller** that continuously adjusted air brake deployment based on predicted apogee error.

At each timestep:
1. The current velocity and altitude were used to numerically predict apogee
2. The predicted apogee was compared to a target altitude
3. The resulting error was fed into a proportional controller
4. The commanded air brake area was saturated to respect physical limits

This approach allowed the controller to remain active throughout the flight rather than only near a narrow operating point.

![Design and Optimization Workflow]({{ "/assets/images/control_loop.png" | relative_url }})

---

## Numerical Simulation
The full nonlinear system was simulated in **MATLAB** using `ode45`. Two cases were modeled:
- Flight with active air brake control
- Flight without air brakes (baseline comparison)

The simulation included actuator saturation and a modeled wind gust disturbance to evaluate robustness.

![Design and Optimization Workflow]({{ "/assets/images/plots1.png" | relative_url }})

---

## Results
Simulation results demonstrated that:
- The active air brake system reduced apogee error by approximately **100 m**
- The controller converged to within **~1 cm of the target apogee** under idealized conditions
- Control effort was frequently saturated, indicating aggressive correction and fast response

A simulated wind gust produced a visible disturbance in predicted apogee, which the controller successfully rejected with minimal impact on final altitude.

![Design and Optimization Workflow]({{ "/assets/images/plots2.png" | relative_url }})

---

## Assumptions & Limitations
To keep the problem tractable, several simplifying assumptions were made:
- Constant air density with altitude
- Constant drag coefficient during air brake deployment
- Negligible actuator dynamics (instantaneous flap motion)

While these assumptions simplified analysis and simulation, they would need refinement for real flight hardware.

---

## Key Takeaways
This project highlighted the tradeoff between analytical simplicity and physical realism. Linearization enabled insight and stability analysis, while numerical simulation was essential for validating controller performance in a nonlinear system.

Key skills demonstrated:
- Linearization of nonlinear physical systems
- State-space modeling and stability analysis
- Feedback control design with saturation
- Numerical simulation using ODE solvers
- Disturbance modeling and rejection

---

## Tools & Methods
- MATLAB (`ode45`)
- State-space modeling
- Proportional feedback control
- Taylor series linearization

---