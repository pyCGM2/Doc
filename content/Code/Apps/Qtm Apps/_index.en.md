---
title: "QTM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---


* run QTM
* select the CGM2 projet
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)

{{< youtube nnIQvpoIS7E >}}
{{< notice "note" >}}
  this video calls the script `QTM_CGM1_workflow.exe` and end up with the pdf report
{{< /notice >}}

The procedure is:

* [QTM] generate your session.xml
  * select *Generate Session* in the *start processing* menu
* [miniconda console] (**optional**) go to your data folder. (you can keep working with *C:* if you have permission)   
* [miniconda console] type the name of the workflow script (e.g `QTM_CGM#i#_workflow.exe`, replace *#i#* by the CGM version number).


<hr>

This process will sucessively:

 * Generate session.xml
 * Export c3d files
 * Detect static and dynamic trials according the attribute type of the `session.xml` node : measurement
 * Detect events according Zeni's algorithm
 * Automatically open Mokka for event verification
 * run kinematic and kinetic calculation
 * Export plots as pdf pages (stored at subsession folder > processed)
