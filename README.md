# FEM Optimization for 2D Truss Structures

This project is a MATLAB-based Finite Element Method (FEM) solver designed to analyze and optimize 2D truss structures. 

##  Application Modules

### Page 1: Setup & Configuration
* **Importing Geometry:** Truss structures can be imported manually or by using the **"Read Node and Elements"** button to load `.txt` files from the `truss_structures/` directory.
* **Boundary Conditions (BC):** * The two furthest points on the bottom plane must be fixed using the BC section.
    * Supports both displacement and force inputs.
    * **Display BC Switch:** Toggles the visibility of all active boundary conditions on the model.
* **Material Selection:** Users can choose from a pre-defined material library or enter manual properties using the **Custom** material selection.

### Page 2: Static & Modal Analysis
* **Static Results:** Clicking **Run** generates Stress and Displacement gradients for the current configuration.
* **Modal Analysis:** * Solves for eigenvalues and eigenvectors to determine the vibration profile and natural frequencies of each node.
    * **Play Mode Sound:** A unique audio feature that generates a sound frequency corresponding to the selected vibration mode.

### Page 3: Global Matrix & Extended Data
* **Extended Node List:** Displays comprehensive nodal data after the solver completes.
* **Global Matrix:** Provides a full view of the assembled Global Stiffness Matrix $[K]$ used in the solution process.

### Page 4: Evolutionary Optimization
* **Objective Function:** The optimizer minimizes the product of total weight and maximum displacement:
$$f_{obj} = \min(W \times \text{disp})$$
* **Algorithm:** Utilizes an **Evolutionary Algorithm** to design a bridge with minimum weight and a homogeneous stress distribution.
* **Live Monitoring:** Real-time feedback on Weight, Max Displacement, Max Stress, and the current Objective Function value.
* **Manual Override:** The process can be terminated at any point using the **Stop** button.





## 📁 Directory Structure
* `project_final.mlapp`: Main MATLAB App Designer file.
* `materials.txt`: Database for material property definitions.
* `truss_structures/`: Folder containing example configurations (`bridge.txt`, `warren_truss.txt`, `arch.txt`, `high_density.txt`).

## 🛠 Operational Constraints
1. **Node Geometry:** The distance between any two connected nodes must be **$\le 3\text{m}$**.
2. **Support Fixation:** The bottom-left and bottom-right corners must be fixed in both the **X and Y axes**.
3. **BC Consistency:** A single node cannot have two identical Boundary Conditions assigned to it.
4. **Modal Limits:** The requested mode number for analysis must be less than or equal to the total degrees of freedom available.

## ⚙️ How to Run
1. Clone or download this repository.
2. Open MATLAB and navigate to the project folder (app).
3. Run `project_final.mlapp` to launch the GUI.
4. On **Page 1**, load a configuration and set BCs to begin analysis.

