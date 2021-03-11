---
title: "QTM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 4
---

QTM-based pycgm2 workflows gather in a single **workflow** both  calibration and fitting operations.


QTM-based pycgm2 workflow are located in *PATHTO\\Miniconda3\\envs\\pycgm3\\Scripts* and named `QTM_CGM#i#_workflow.exe` ( replace *#i"* by the CGM version number) ( e.g `QTM_CGM1_workflow.exe` is the workflow for the CGM1)   

`QTM_CGM#i#_workflow.exe` scripts require the `session.xml` file. You need thus to generate this file before running any script.
The role of `session.xml` is to overloaded the  internal `#-pycgm2.settings` file     
