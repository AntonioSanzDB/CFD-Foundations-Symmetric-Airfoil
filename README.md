# 2D CFD Foundations: Symmetric Airfoil Analysis & Flow Separation

Author: [Antonio Sanz]  
Date: March 2026  
Software: ANSYS Fluent, ANSYS DesignModeler, ANSYS Meshing  

##  Project Objective
The primary objective of this project was to establish a foundational understanding of the ANSYS Workbench CFD (Geometry $\rightarrow$ Mesh $\rightarrow$ Setup $\rightarrow$ Solution). A custom symmetric teardrop airfoil was modeled to study basic aerodynamic principles, specifically lift generation via Angle of Attack (AoA) and the onset of flow separation (aerodynamic stall) simulating a wing of an airplane. 

This project served as the baseline software validation prior to simulating complex, high-camber asymmetric profiles for motorsport applications.

## Methodology & Setup
A 2D computational domain was constructed, and the geometry was processed using the Boolean subtract method to create the fluid region.

* Airfoil Profile: Custom Symmetric Teardrop (Derived from mirrored profile coordinates of a NACA wing (airplane wing))
* Angle of Attack (AoA): 15° (Nose-up orientation)
* Solver: Steady-State, Pressure-Based
* Turbulence Model: Inviscid (zero viscosity)
* Inlet Velocity: 15 m/s
* Fluid: Air

### Meshing Strategy
A mesh was generated using 0.1m for decent precision. Adaptive edge sizing was applied to the airfoil boundaries to ensure the solver accurately captured the surface curvature. 

![meshwing](https://github.com/user-attachments/assets/9473e699-781c-4b63-96b6-f13b85a6f627)

---

## Results & Aerodynamic Data

The solver was configurated for 600 iteration or until it achives convergence. In this case it achieved convergence rapidly, stabilizing the force calculations at approximately 32 iterations.
![residualswing](https://github.com/user-attachments/assets/d58a673a-9e65-481f-b7a6-d0747f87fe9c)

### 1. Force Coefficients & Aerodynamic Stall
Because the airfoil is perfectly symmetric, it relies entirely on its 15° Angle of Attack to deflect air and generate lift. The console output yielded:

* Coefficient of Lift ($C_l$): 0.653
* Coefficient of Drag ($C_d$): 0.147
![liftwing](https://github.com/user-attachments/assets/cf21522b-2444-453d-bbd5-bc7697a27538)
![dragwing](https://github.com/user-attachments/assets/089bd778-108d-443f-ae33-1522e4c5e5ae)

While positive lift was achieved, the $C_l$ is relatively low for such a steep angle. This might be due to an aerodynamic stall.

### 2. Static Pressure Contour
The pressure contour clearly visualizes the mechanics of lift. A high-pressure zone (red/orange) is visible on the lower surface as it forces air downward, while a low-pressure zone (blue/green) forms on the upper surface. Since air tends to go from low-pressure to high-pressure this generates lift.

![pressurewing](https://github.com/user-attachments/assets/540055db-150a-4faa-beb2-7d2ac871f89c)

### 3. Velocity Magnitude & Flow Separation
The velocity contour confirms the hypothesis of an aerodynamic stall. The air accelerating over the top surface (red) detaches before reaching the trailing edge. This flow separation results in a low-velocity turbulent wake (blue streak) extending behind the wing, which limits lift generation and inducing drag. 

![velocitywing](https://github.com/user-attachments/assets/e7d63818-2d5c-4b43-a2f5-5f89ae47166d)

---

## Conclusion & Next Steps
This simulation it provided clear visual data on flow separation and the limitations of symmetric airfoils at high Angles of Attack. It also showed an irregularity since a inviscid flow model shouldn't stall and it should generate more lift and less drag. Then the coarse grid need to have introduced a numerical viscosity and artificially separated the flow.

With this introduction to simulation the next step is to simulate more complex and asymmetric airfoils (such as the Selig S1223) utilized in Formula SAE 

Link to Phase 2 (FSAE High-Downforce Analysis): [https://github.com/AntonioSanzDB/FSAE-2D-CFD-Aerodynamics.git]
