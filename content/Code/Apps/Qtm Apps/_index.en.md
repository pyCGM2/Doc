---
title: "QTM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---


* run QTM
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)



The procedure is:

* [QTM] generate your session.xml
* [miniconda console] go to your data folder
* [miniconda console] type the name of the workflow script (e.g `QTM_CGM#i#_workflow.exe`, replace *#i#* by the CGM version number).

{{< collapse "example of input arguments" >}}

* `QTM_CGM1_workflow.exe --sessionFile mysession.xml` :
  * call `mysession.xml` instead of `session.xml`

{{< /collapse >}}
