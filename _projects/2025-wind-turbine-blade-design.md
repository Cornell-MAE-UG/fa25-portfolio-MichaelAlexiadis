---
layout: project
title: Wind Turbine Blade Design Project
image: /assets/images/blade_image.png
---

# Wind Turbine Blade Design Project

**Course:** MAE 4272 – Fluids & Heat Transfer Laboratory  
**Team:** Gregory Sharma, Jacob Gonzalez, Ata Zavaro, Michael Alexiadis  

## Project Overview
As part of MAE 4272, our team designed, optimized, manufactured, and tested a small-scale wind turbine blade intended to maximize power output in low-wind conditions. The objective was to design a blade that performed optimally under a realistic Weibull wind-speed distribution (mean wind speed of 4.59 m/s) while satisfying strict geometric, structural, and operational constraints. This project emphasized the full engineering cycle—from modeling and optimization to physical testing and performance assessment.

## Design Process
We developed a coupled numerical and CAD-based workflow to translate aerodynamic optimization directly into a manufacturable blade geometry. Aerodynamic performance was modeled using a simplified blade element theory framework combined with low–Reynolds-number airfoil data. A Python-based differential evolution optimizer was used to tune blade pitch distribution, root chord, and target operating RPM to maximize expected power output while enforcing constraints on stress, geometry, and rotational speed. The blade was discretized into spanwise segments to mirror the CAD construction process, allowing optimized parameters to be directly implemented in Fusion 360. The NACA 4412 airfoil was selected for its superior lift-to-drag performance at low Reynolds numbers.

## Testing and Results
The finalized blades were manufactured and tested in a wind tunnel across multiple wind speeds and loading conditions. Experimental measurements included rotational speed, torque, and power output, which were used to generate power–RPM curves for comparison with model predictions. While the blade met all structural and geometric constraints and survived testing without failure, experimental results showed significantly lower power output than predicted, particularly at low wind speeds where the turbine failed to self-start. Testing revealed that a blade pitch orientation error and unmodeled physical effects such as friction and startup losses contributed to the discrepancy between simulation and experiment. These results highlighted the sensitivity of turbine performance to both physical modeling assumptions and implementation details.

## My Contribution
I contributed to the aerodynamic modeling and optimization workflow, including supporting the development and interpretation of the differential evolution optimizer and connecting its outputs to the CAD-based blade geometry. I also assisted with CAD development, testing setup, and analysis of experimental data, focusing on comparing predicted performance to measured results and identifying sources of discrepancy between the model and physical system.

## Figures
Representative figures from the project are shown below.

<img src="assets/optimizer_workflow.png" alt="Design and Optimization Workflow" width="550"/>

<img src="assets/blade_cad.png" alt="Final Blade CAD Geometry" width="550"/>

<img src="assets/power_curves.png" alt="Measured Power vs RPM at Multiple Wind Speeds" width="550"/>



