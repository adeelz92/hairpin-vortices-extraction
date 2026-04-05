# Extract and Characterize Hairpin Vortices in Turbulent Flows

> This repository is a work in progress...

This repository is the implementation of paper "A. Zafar, D. Yang and G. Chen, "Extract and Characterize Hairpin Vortices in Turbulent Flows," in IEEE Transactions on Visualization and Computer Graphics, doi: 10.1109/TVCG.2023.3326603". The code and the supplemental material is distributed under CC-BY-NC-4.0. Kindly cite our papar.

```
A. Zafar, D. Yang and G. Chen, "Extract and Characterize Hairpin Vortices in Turbulent Flows," in IEEE Transactions on Visualization and Computer Graphics, vol. 30, no. 1, pp. 716-726, Jan. 2024, doi: 10.1109/TVCG.2023.3326603.
```

### How to run the code
- In the first step, go the the folder "splitting" and follow the readme instructions.
- Then go to the clustering folder and perform clustering. Read the comments in the code for additional information.
- Move the clustering results, the tree json file and the vtk file from step 1 to the same folder and follow the instructions below to visualize the results in the system.

**_Required_ Python >= 3.9**

### How to run the interactive visualization code
Download and extract this code.

Install miniconda, then go to start and open anaconda prompt. 'cd' to the code's folder.

Then execute the following commands to create a new environment.
```
conda create -n myenv python=3.9
conda activate myenv
pip install -r requirements.txt
```
then 'cd' to vis_sys folder and run *python pyecharts_QtWebEngine.py*.
- Use the browse button to open the vtk file from one of the folder from the *full_data* folder and click open.
- Doing so will automatically read the tree and profiles information from the *.json* file and the clustering infromation from the *_clusters.txt* associated with each dataset. 
- Currently *.vtk*, *.json* and *_clusters.txt* are only provided for **Benard** and **Cylinder** flow datasets. These files are the output of our vortex extraction and separation strategies explained in the paper.
