---
title: "QTM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---

All available Nexus apps can be displayed with the command

`pycgm2.exe QTM -h`

you will see, we propose QTM workflows for each CGM
![QtmCommands](QtmCommands.jpg)


The procedure to run a CGM workflow is 

* open QTM
* select the CGM2 projet
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm39`)
* [QTM] generate your session.xml
  * select *Generate Session* in the *start processing* menu
* go to your data folder.   
* run  `pycgm2.exe QTM CGM1.0` to run the CGM1.0 workflow


This process sucessively:

 * generate session.xml
 * Export c3d files
 * Detect static and dynamic trials according the attribute type of the `session.xml` node : measurement
 * Detect events according Zeni's algorithm
 * Automatically open Mokka to for checking events 
 * run kinematic and kinetic calculation
 * Export plots as pdf pages (stored in the subsession folder *processed*)
