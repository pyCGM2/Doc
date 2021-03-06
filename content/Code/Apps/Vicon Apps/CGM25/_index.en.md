---
title: "CGM2.5"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 6
---

{{< notice "note" >}}
  check out the [CGM2.5 section]({{< ref "CGM/CGM2.5" >}}) to know the details of this model.
{{< /notice >}}


{{< notice "info" >}}
  This model use *Inverse kinematic* as default segmental pose algorithm.    
{{< /notice >}}



* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)

### Calibration

{{< youtube F14S0yHFnGw   >}}

As you can see, the procedure is :

* [Nexus] load your static file
* [miniconda Console] type `Nexus_CGM25_Calibration.exe`

Model calibration will be carried out according the CGM25 and its settings (`CGM25-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM25_Calibration.exe -l 0` (equiv `Nexus_CGM25_Calibration.exe --leftFlatFoot 0`):
  * disables the flat foot option on the left side while keeping the flat foot option enable on the right side

* `Nexus_CGM25_Calibration.exe -l 0 -md 16 -ps cgm25` ( equiv to `Nexus_CGM25_Calibration.exe --leftFlatFoot 0 --markerDiameter 16 --pointSuffix cgm25`) :
  * disable the flat foot option on the left side while keeping the flat foot option enable on the right side
  * use marker of 16mm diameter instead of 14mm
  * suffix model outputs with *_cgm25*

{{< /collapse >}}

<hr>

### Fitting

{{< youtube eiz85DV4Mt0  >}}

The procedure:

  * [Nexus] load your gait file
  * [miniconda Console] type `Nexus_CGM25_Fitting.exe`

Model will be fitted according the CGM1 and its settings (`CGM25-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM25_Fitting.exe --proj Proximal -md 16 --noIK ` :
  * use marker of 16mm diameter instead of 14mm
  * project joint moment into the proximal segment
  * disable inverse kinematics and compute pose with segmental least-square optimisation (i.e 6DOF model)

* `Nexus_CGM25_Fitting.exe --proj Proximal -md 16 -a 1e-5 ` :
  * use marker of 16mm diameter instead of 14mm
  * project joint moment into the proximal segment
  * set the inverse kinematic accuracy to 1e-5  
{{< /collapse >}}
