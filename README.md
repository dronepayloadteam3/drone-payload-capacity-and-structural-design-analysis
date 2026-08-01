# Drone-Design-Analysis-Team-3
MATLAB-based UAV arm design and optimization project using CAD modeling, thrust analysis, and finite element analysis (FEA) to evaluate structural performance and payload capacity.
Project Objective

The objective of this project is to design and evaluate a quadcopter drone arm that maximizes payload capacity while maintaining safe flight performance and structural integrity. Using thrust-to-weight analysis and Finite Element Analysis (FEA), we evaluate two distinct drone arm geometries using six different engineering materials.

Through the development and analysis of these designs, we investigate how the geometry and material selection affect payload capacity, factor of safety, material cost, structural displacement, and stress distribution (such as Von Mises stress). Through analytical calculations and computational modeling, we identify the drone arm design that best provides effective payload capacity and structural integrity, as well as optimizing material cost.


MATLAB is used throughout this project to:
  - Perform thrust-to-weight analysis
  - Finite Element Analysis (FEA)
  - Material cost optimization

Files Included
- drone_design_team3_analysis.mlx – Main MATLAB Live Script containing the complete drone design, analysis, and optimization workflow.
- droneArmMaterials.mat – Material properties database used throughout the analysis.
- Design_1_CAD_Model.STEP – CAD model of Design 1 used for finite element analysis (FEA).
- Design_2_CAD_Model.STL – CAD model of Design 2 used for visualization and design comparison.
- DroneDesign1_Team3_Analysis.pdf – PDF export of the Design 1 MATLAB analysis for viewing without MATLAB.
- DroneDesign2_Team3_Analysis.pdf – PDF export of the Design 2 MATLAB analysis for viewing without MATLAB.
- Design_1_Concept_Sketch.pdf – Concept sketch for the first drone arm design.
- Design_2_Concept_Sketch.pdf – Concept sketch for the second drone arm design.
- README.md – Project documentation and usage instructions.


How to Run the Project
1. Open MATLAB.
2. Place all project files in the same folder.
3. Open drone_design_team3_analysis.mlx..
4. Ensure the following files are in the working directory:
- droneArmMaterials.mat
- Design_1_CAD_Model.STEP
- Design_2_CAD_Model.STL
5. Click Run to execute the Live Script.


Project Workflow:

1. Load Material Properties
        -  The project loads the density, Young’s modulus, Poisson's ratio, yield strength, and cost for six drone arm materials: Carbon Fiber Composite (CFRP), Aluminum Alloy, Fiberglass Composite             (GFRP), PLA Plastic, ABS Plastic, Wood (Birch)
2. Thrust-to-Weight Analysis
        - Calculates the mass of each drone arm and determines the maximum payload capacity while checking that each design satisfies the minimum payload of 0.5 kg and minimum thrust-to-weight                 ratio of 2:1. 
3. Finite Element Analysis (FEA)
        -  Imports the STEP model and generates the finite element mesh. Will analyze the maximum displacement, von mises stress, and factor of safety for each material and display results in a                 summary table and displacement and stress graphs that can be moved when clicked on. 
4. Cost Optimization
        -  After running the thrust-to-weight analysis and Finite Element Analysis (FEA), we calculate the cost of each material based on the design’s volume and length. Based on the results, we                filter the options that do not satisfy the project requirements and identify the lowest-cost material.


Required Software and Toolboxes
Software:
- MATLAB_R2026a
  
Required Toolboxes:
- Partial Differential Equation Toolbox
- MATLAB Live Editor

How to Reproduce the Results
To reproduce the results:
1. Use the provided droneArmMaterials.mat material properties database.
2. Use the provided Design_1_CAD_Model.STEP CAD model.
3. Use the provided Design_2_CAD_Model.STL CAD model.
4. Open drone_design_team3_analysis.mlx in MATLAB.
5. Run the Live Script without modifying the input parameters.


The script will automatically generate:
  - Payload summary tables
  - Maximum payload bar graphs
  - FEA displacement plots and Von Mises stress plots
  - FEA results table
  - Material cost comparison graph
  - Final design recommendation
