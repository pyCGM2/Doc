---
title: "CGM1.1"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---

{{< notice "note" >}}
  check out the [CGM1.1 section]({{< ref "CGM/CGM1.1" >}}) to know the details of this model
{{< /notice >}}


* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)

### Calibration

{{< youtube _pKB-CXCXLM  >}}

As you can see, the procedure is :

* [Nexus] load your static file
* [miniconda Console] type `Nexus_CGM11_Calibration.exe`

Model calibration will be carried out according the CGM11 and its settings (`CGM11-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM11_Calibration.exe -l 0` (equiv `Nexus_CGM11_Calibration.exe --leftFlatFoot 0`):
  * disables the flat foot option on the left side while keeping the flat foot option enable on the right side

* `Nexus_CGM11_Calibration.exe -l 0 -md 16 -ps cgm11` ( equiv to `Nexus_CGM11_Calibration.exe --leftFlatFoot 0 --markerDiameter 16 --pointSuffix cgm1`) :
  * disable the flat foot option on the left side while keeping the flat foot option enable on the right side
  * use marker of 16mm diameter instead of 14mm
  * suffix model outputs with *_cgm11*

{{< /collapse >}}

<hr>

### Fitting

{{< youtube TCZWi5gSLUA  >}}

The procedure:

  * [Nexus] load your gait file
  * [miniconda Console] type `Nexus_CGM11_Fitting.exe`

Model will be fitted according the CGM1 and its settings (`CGM11-pyCGM2.settings`)

{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM11_Fitting.exe --proj Proximal -md 16` :
  * use marker of 16mm diameter instead of 14mm
  * project joint moment into the proximal segment
{{< /collapse >}}
