---
title: "CGM1"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 1
---

{{< notice "note" >}}
  check out the [CGM1.0 section]({{< ref "CGM/CGM1.0" >}}) to know the details of this model
{{< /notice >}}


* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)

### Calibration

{{< youtube XbdTaaLq3MQ >}}
*as you can see, the calibration was done with a Knee aligment Device, it was automatically detected by the calibration script*


The procedure is :

* [Nexus] load your static file
* [miniconda Console] type `Nexus_CGM1_Calibration.exe`

Model calibration will be carried out according the CGM1 and its settings (`CGM1-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM1_Calibration.exe -l 0` (equiv `Nexus_CGM1_Calibration.exe --leftFlatFoot 0`):
  * disables the flat foot option on the left side while keeping the flat foot option enable on the right side

* `Nexus_CGM1_Calibration.exe -l 0 -md 16 -ps cgm1` ( equiv to `Nexus_CGM1_Calibration.exe --leftFlatFoot 0 --markerDiameter 16 --pointSuffix cgm1`) :
  * disable the flat foot option on the left side while keeping the flat foot option enable on the right side
  * use marker of 16mm diameter instead of 14mm
  * suffix model outputs with *_cgm1*

{{< /collapse >}}

<hr>

### Fitting

{{< youtube 0fAeBiVQqMQ >}}

The procedure:

  * [Nexus] load your gait file
  * [miniconda Console] type `Nexus_CGM1_Fitting.exe`

Model will be fitted according the CGM1 and its settings (`CGM1-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM1_Fitting.exe --proj Proximal -md 16` :
  * use marker of 16mm diameter instead of 14mm
  * project joint moment into the proximal segment
{{< /collapse >}}
