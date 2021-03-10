---
title: "The Nexus operations"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 3
---


With Vicon Nexus, modelling operations consist in two stages :

 *  **Calibration** : construction of anatomical coordinate systems from a **static pose**
 *  **Fitting** :  segmental pose tracking of a motion, followed by the calculation of the kinematics and kinetics

Each modelling operation is associated with a python script (see folder:*PATHTO\\Miniconda3\\envs\\pycgm3\\Scripts*))  

For instance, scripts `Nexus_CGM1_Calibration.exe` and `Nexus_CGM1_Fitting.exe` call `CGM1-pyCGM2.settings` and  calibrate ( resp. fit) the static ( resp. gait) trial with the CGM1















* generates **scripts** into the virtual environment ( here pycgm3) folder *PATHTO\\Miniconda3\\envs\\pycgm3\\Scripts*)
* creates a folder *C:\\programData\\pycgm2* and gathers in **settings**
* detects your Vicon Nexus version and populates *C:\\Users\\Public\\Documents\\Vicon\\Nexus2.x*
