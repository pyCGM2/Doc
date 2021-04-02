---
title: "CGM2.6"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 7
---

{{< notice "note" >}}
  check out the [CGM2.6 section]({{< ref "CGM/CGM2.6" >}}) to know the details of this model.
{{< /notice >}}

* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)

{{< notice "info" >}}
  The CGM2.6 refined the knee axis of the CGM2.5. Calibration and Fitting are similar to CGM2.5.<br>
  The knee functional calibration operation occurs before the Fitting one.



{{< /notice >}}


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


### Knee functional calibration

2 knee functional calibration methods are available :

 * Calibration2Dof
 * SARA


{{< youtube xuv4PkCcItw  >}}

For both the procedure is :

 *  [Nexus] load your knee flexion extension file
 * [miniconda Console] type `Nexus_CGM26_2DOF.exe` or `Nexus_CGM26_SARA.exe`

The script detects the lower body side and optimise the knee flexion axis from all frames of your c3d.

If you want to manually define the side and the initial and last frame, use the input arguments:


{{< collapse "examples of input argument alteration" >}}
* `Nexus_CGM26_2DOF.exe --side Left -b 320 -e 430` :
  * apply calibration2DOF on the left side from frames 320 to 430
{{< /collapse >}}   







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
