# Drone Design Analysis Team 3

MATLAB-based UAV arm design and optimization project using CAD modeling, thrust-to-weight analysis, finite element analysis (FEA), and material cost optimization to evaluate structural performance and payload capacity.

This project was completed as part of the MathWorks Classroom Challenge and demonstrates the application of CAD modeling, MATLAB programming, thrust-to-weight analysis, and finite element analysis (FEA) to optimize UAV drone arm performance.

---

# Project Objective

The objective of this project is to design and evaluate a quadcopter drone arm that maximizes payload capacity while maintaining safe flight performance and structural integrity. Two distinct drone arm geometries were evaluated using six different engineering materials through thrust-to-weight analysis and Finite Element Analysis (FEA).

Through the development and analysis of these designs, the project investigates how geometry and material selection affect payload capacity, factor of safety, material cost, structural displacement, and stress distribution (e.g., Von Mises stress). Through analytical calculations and computational modeling, this project identifies the drone arm design that best provides effective payload capacity and structural integrity while optimizing material cost.

---

# MATLAB is used throughout this project to:

* Perform thrust-to-weight analysis
* Perform Finite Element Analysis (FEA)
* Perform material cost optimization

---

# Repository Structure

## cad-designs

Contains all CAD models and design sketches.

### design-1-hollow-tapered-rectangular-tube
* Design_1_Concept_Sketch.pdf 
* Design_1_CAD_Model.STEP 
* Visualization_Only_Model.STL --- STL export for visual purposes only on GitHub

### design-2-hollow-truss-structure

* Design_2_Concept_Sketch.pdf 
* Design_2_CAD_Model.STL 

## Documentation

Contains supporting project documentation.

* Drone_Constraints_Assumptions_and_Design_Ideas.pdf
* drone_payload_team_3_toa.pdf

## MATLAB

Contains all MATLAB files used throughout the project.

* live-script-pdf-exports
  * Design_1_Live_Script_Analysis_Export.pdf --- PDF export of the MATLAB analysis using Design 1.
  * Design_2_Live_Script_Analysis_Export.pdf --- PDF export of the MATLAB analysis using Design 2.
* drone_design_team3_analysis.mlx --- Main MATLAB Live Script containing the complete drone design, analysis, and optimization workflow.

* droneArmMaterials.mat --- Material properties database used throughout the analysis.

## Results

Contains all exported project results organized by drone design.

Each design folder contains:

* Maximum payload tables and charts
* Material cost optimization tables and charts
* FEA plots
* FEA result tables
* Face label reference files

---

# How to Download the CAD Files

1. Open the **cad-designs** folder.
2. Open the **design-1-hollow-tapered-rectangular-tube** or **design-2-hollow-truss-structure** folder
3. Select the desired STEP (For Design 1) or STL (For Design 2) file.
4. Click **Download Raw File** (download icon) in the upper-right corner.
   -  Alternatively, right-click **Raw** and choose **Save Link As...**

---

# How to Run the Project

1. Open MATLAB.

2. Place all project files in the same working folder.

3. Open drone_design_team3_analysis.mlx.

4. Ensure the following files are located in the working directory:

* droneArmMaterials.mat
* Design_1_CAD_Model.STEP
* Design_2_CAD_Model.STL

5. Select which drone arm design you would like to analyze during **Task 4: Finite Element Analysis (FEA)**.

To switch between the two drone arm designs, locate the STEP file assignment in the Live Script.

For Design 1:

```matlab
selectedDesign = "Design 1";
% selectedDesign = "Design 2";
```

For Design 2:

```matlab
% selectedDesign = "Design 1";
selectedDesign = "Design 2";
```

Only one design should remain uncommented before running the script.

6. Click **Run**.

---

# Project Workflow

## 1. Load Material Properties

Loads the density, Young's modulus, Poisson's ratio, yield strength, and material cost for:

* Carbon Fiber Composite (CFRP)
* Aluminum Alloy
* Fiberglass Composite (GFRP)
* PLA Plastic
* ABS Plastic
* Wood (Birch)



## 2. Thrust-to-Weight Analysis

Calculates the mass of each drone arm and determines the maximum payload capacity while verifying that each design satisfies:

* Minimum payload requirement of **0.5 kg**
* Minimum thrust-to-weight ratio of **2:1**



## 3. Finite Element Analysis (FEA)

Imports the selected STL or STEP model into MATLAB.

The script then:

* Generates the finite element mesh
* Applies boundary conditions
* Applies motor thrust and motor weight
* Computes:

  * Maximum displacement
  * Von Mises stress
  * Factor of Safety

The results are displayed as summary tables and interactive displacement and stress plots.



## 4. Material Cost Optimization

After completing the thrust-to-weight analysis and FEA, MATLAB calculates the material cost for each design based on the arm geometry and material properties.

The program filters materials that satisfy all project constraints and identifies the lowest-cost engineering solution.

---

# Required Software

* MATLAB R2026a

---

# Required Toolboxes

* Partial Differential Equation Toolbox
* MATLAB Live Editor

---

# How to Reproduce the Results

To reproduce the project results:

1. Use the provided **droneArmMaterials.mat** database.
2. Use the provided CAD models.
3. Open **drone_design_team3_analysis.mlx**.
4. Select either Design 1 or Design 2 by commenting/uncommenting the corresponding CAD file.
5. Run the Live Script without modifying any input parameters.

The Live Script automatically generates:

* Payload summary tables
* Maximum payload comparison charts
* Material cost comparison charts
* FEA displacement plots
* Von Mises stress plots
* FEA results tables
* Material cost optimization tables
* Final design recommendation

All exported figures, tables, and analysis outputs can be found in the **Results** folder, organized separately for Design 1 and Design 2.

---

# Final Recommendation

Based on the thrust-to-weight analysis, Finite Element Analysis (FEA), and material cost optimization, the recommended design is **Design 1, a tapered hollow rectangular arm** constructed from **Fiberglass Composite (GFRP)**. It provides the best balance of payload capacity, structural safety, and engineering performance while satisfying all project constraints.

Although Carbon Fiber Composite (CFRP) provided the highest overall structural performance, GFRP offered a better balance between performance and cost while still meeting all project requirements. The improvements provided by CFRP were relatively small compared to its increase in material cost, making GFRP the more practical engineering choice.

Additionally, while Wood (Birch) was identified as the lowest-cost material, it was not selected as the final recommendation. Although it satisfied the project requirements under the simplified loading conditions, it was not considered the best choice for real-world drone applications where additional engineering conditions such as wind, vibration, fatigue, and landing impacts must be considered. Furthermore, wood can absorb moisture from the environment, which may reduce structural performance over time while increasing the overall weight of the drone. For these reasons, GFRP was considered the strongest overall engineering solution.

Compared with Design 2, Design 1 demonstrated better structural behavior. Although Design 2 met the project requirements, it experienced greater maximum displacement. Through investigation, it was determined that the truss members primarily reinforced the x- and y-directions but provided limited resistance in the z-direction. This reduced the arm's resistance to vertical bending and likely contributed to the higher displacement. Rather than redesigning the arm, the team chose to retain the original design because it demonstrates the engineering design process. The results highlighted how analysis, testing, and iteration lead to improved engineering decisions and provide valuable lessons for future designs.

Overall, Design 1 with GFRP provided the best combination of payload capacity, structural integrity, manufacturability, and material cost. Future work could expand this analysis by incorporating wind loading, vibration, fatigue, landing impacts, motor torque, and experimental prototype testing to better represent real operating conditions.

A more detailed report of the final design recommendation, including the MATLAB-based analysis, FEA results, and optimization process, can be found in the accompanying MATLAB Live Script (drone_design_team3_analysis.mlx).
