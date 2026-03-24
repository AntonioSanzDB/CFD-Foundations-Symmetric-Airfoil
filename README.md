# 2D CFD Foundations: Symmetric Airfoil Analysis & Flow Separation

Author: [Antonio Sanz]  
Date: March 2026  
Software: ANSYS Fluent, ANSYS DesignModeler, ANSYS Meshing  

## 📌 Project Objective
The primary objective of this project was to establish a foundational understanding of the ANSYS Workbench CFD pipeline (Geometry $\rightarrow$ Mesh $\rightarrow$ Setup $\rightarrow$ Solution). A custom symmetric teardrop airfoil was modeled to study basic aerodynamic principles, specifically lift generation via Angle of Attack (AoA) and the onset of flow separation (aerodynamic stall). 

This project served as the baseline software validation prior to simulating complex, high-camber asymmetric profiles for motorsport applications.

## ⚙️ Methodology & Setup
A 2D computational domain was constructed, and the geometry was processed using the Boolean subtract method to create the fluid region.

* **Airfoil Profile:** Custom Symmetric Teardrop (Derived from mirrored Selig profile coordinates)
* **Angle of Attack (AoA):** +15° (Nose-up orientation)
* **Solver:** Steady-State, Pressure-Based
* **Turbulence Model:** $k-\omega \text{ SST}$
* **Inlet Velocity:** 15 m/s
* **Fluid:** Air

### Meshing Strategy
A foundational quad-dominant mesh was generated. Edge sizing was applied to the airfoil boundaries to ensure the solver accurately captured the surface curvature. 

*(Note: While effective for basic flow visualization, future iterations require localized inflation layers to accurately resolve boundary layer friction and precise drag coefficients).*

---

## 📊 Results & Aerodynamic Data

The solver achieved convergence rapidly, stabilizing the force calculations at approximately 32 iterations.

### 1. Force Coefficients & Aerodynamic Stall
Because the airfoil is perfectly symmetric, it relies entirely on its 15° Angle of Attack to deflect air and generate lift. The console output yielded:

* **Coefficient of Lift ($C_l$):** +0.653
* **Coefficient of Drag ($C_d$):** 0.147

While positive lift was achieved, the $C_l$ is relatively low for such a steep angle. This suggests the airfoil has surpassed its critical Angle of Attack and entered an aerodynamic stall.

### 2. Static Pressure Contour
The pressure contour clearly visualizes the mechanics of lift. A high-pressure zone (red/orange) is visible on the lower surface as it forces air downward, while a low-pressure zone (blue/green) forms on the upper surface. 

![Static Pressure]([Drag-and-drop your pressure contour image here])

### 3. Velocity Magnitude & Flow Separation
The velocity contour confirms the hypothesis of an aerodynamic stall. The air accelerating over the top surface (red) abruptly detaches before reaching the trailing edge. This massive flow separation results in a large, low-velocity turbulent wake (dark blue streak) extending behind the wing, which severely limits lift generation and induces drag.

![Velocity Magnitude]([Drag-and-drop your velocity contour image here])

---

## 🏁 Conclusion & Next Steps
This simulation successfully validated the end-to-end ANSYS CFD workflow. Furthermore, it provided clear visual data on flow separation and the limitations of symmetric airfoils at high Angles of Attack. 

With the software pipeline validated, the next phase of research involves applying these methods to highly cambered, asymmetric airfoils (such as the Selig S1223) utilized in Formula SAE to generate maximum downforce at 0° to 15° orientations. 

**Link to Phase 2 (FSAE High-Downforce Analysis):** [Insert the link to your other GitHub repo here]
