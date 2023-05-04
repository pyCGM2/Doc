---
title: "Changelog"
description: ""
draft: false
---

{{< notice "info" >}}
  Use the contact form to suggest improvements
{{< /notice >}}


## pyCGM2 4.3.0-rc2 - Documentation - [april 2023] -one command to rule them all 

{{< changelog "Added" >}}

* creation of a [conda package](https://anaconda.org/pyCGM2/pycgm2)
* creation of [shared conda environments](https://anaconda.org/pyCGM2/environments) 
* package compatible for python 3.7 to 3.9 
* compatibility with opensim 4.4
* A single command line  `pyCGM2.exe` to control all Nexus, Qtm apps
* Computation of the L(R)GroundReactionForce +  creation of a new model ouputs L(R)StanGroundReactionForce standardising the ground reaction force for clinical description
(X: forward/backward Y: Lateral/medial Z: Upward/downward)
* new variables ("LTHIplanarAngle", "RTHIplanarAngle","LTIBplanarAngle", "RTIBplanarAngle") fro CGM1 to 2.1 returning the planar angles between the proximal joint (e.g. LHJC)
the lateral joint marker(e.g. LKNE) and the lateral marker (e.g LTHI). (Reference Leboeuf, F.; Sangeux, M. (2022) Wand-mounted lateral markers are less prone to soft-tissue artefacts than skin-mounted markers when using the conventional gait model. In : Gait & posture. DOI: 10.1016/j.gaitpost.2022.12.013.)
* interaction with the **param** c3d section.
* implementation of the Plantar-flexor - knee extension index (Sangeux, Morgan; Rodda, Jill; Graham, H. Kerr (2015) Sagittal gait patterns in cerebral palsy: the plantarflexor-knee extension couple index. In : Gait & posture, vol. 41, n° 2, p. 586–591. DOI: 10.1016/j.gaitpost.2014.12.019. ). 
* implementation of Sangeux et al, 2015. (Sangeux, Morgan; Polak, Julia (2015) A simple method to choose the most representative stride and detect outliers. In : Gait & posture, vol. 41, n° 2, p. 726–730. DOI: 10.1016/j.gaitpost.2014.12.004)
* new interface with opensim 4.4
* **experimental** implementation of the kalman opensim inverse kinematic solder
* **experimental** computation of the muscle lenght for CGM2.2 and 2.3
* **experimental** enable use of custom anthropometric parameters.
* **experimental** integration of Blue trident btk reader and basic IMU calculation
* **experimental** possibility to use Nexus Commamds in offline mode

{{</ changelog >}}

{{< changelog "Changed" >}}
* processing module reorganised. Procedures and filters in distinct submodules
 {{</ changelog >}}

{{< changelog "Fixed" >}}
* SARA and Calibration2Dof fixed for working with the lower limb model
* tibial torsion now updated with the CGM1 presenting  medial ankle markers.
* [nexus] new script argument `forceMP` to force the use of anthropometric parameter offset 
* export of the gvs scores enable
* fix issue with  settings if you have several virtual environments
* wrong axis used in Naaim's knee varus valugus correction  

 {{</ changelog >}}


 

## pyCGM2 4.2.0 - Documentation - [may 2022]

{{< changelog "Added" >}}

* Documentation API generated with sphinx (available at [readthedoc website](https://pycgm2.readthedocs.io/en/version4.2.0/))
* restructuration module. Procedures and filters  in distinct modules
* management of the **param** c3d section.
* classification filter for classify gait according the Plantar-flexor - knee extension value.     
{{</ changelog >}}

{{< changelog "Changed" >}}

  * installation  do not copy  settings into the folder *c:/programData/pycgm2/*. Default settings are called from the *settings* folder of your installed pyCGM2 package     
  * better management of the settings file (emg.settings and CGMi-pycgm2.settings).  `Utils.files.loadModelSettings` looks for a cgm settings file in your data folder if not found. it loads the default cgm settings.  
  *  emg processing functions improved. better management of the emg.settings through a  new class `EMG.EmgManager`  
 {{</ changelog >}}

{{< changelog "Fixed" >}}

* **vicon CGM1.1 calibration  app** fixed ( wrong argument name)
* **Vicon apps** for plotting comparison does not fail anymore from 2 eclipse marked nodes
* wrong settings  are called if you have several virtual environments
* wrong axis calculation - Naaim's knee varus valugus correction method fixed
 {{</ changelog >}}



###  pyCGM2 4.1.0 - Phantoms- [april, 2021]



{{< changelog "Added" >}}
 * **Management of  missing markers**. The code no longer detects body part (i.e lower body, Upper body or Lower body + thorax). This new feature allows to process data with markers placed over the left or right leg only

* **Anomaly detectors**.  CGM operations integrate anomaly detectors.  Implemented anomaly detectors check :
     * marker trajectory
     * anthropometric data
     * saturation of force plate
     * gait events

* **new QTM workflows** : CGM2.5 and CGM2.6 implemented
{{</ changelog >}}


{{< changelog "Changed" >}}
  * The *fitting* operation.  The user can specify frames of interest (first and last frame) from script argument. If not specified, the fitting operation automatically detect frames of interest based on tracking makers presence.     
  * Clarification of the log message.
  * the *chord* function was reimplemented from scratch ( former implementation was time consuming)
{{</ changelog >}}

{{< changelog "Fixed" >}}
None
{{</ changelog >}}




**march, 2021**

{{< changelog "changed" >}}
* hugo as static web site generator  
{{</ changelog >}}

<hr>






<!-- ### Changelog label

{{< changelog "Added" >}}
{{</ changelog >}}

{{< changelog "Changed" >}}
{{</ changelog >}}

{{< changelog "Depricated" >}}
{{</ changelog >}}

{{< changelog "Removed" >}}
{{</ changelog >}}

{{< changelog "Fixed" >}}
{{</ changelog >}}

{{< changelog "Security" >}}
{{</ changelog >}}

{{< changelog "Unreleased" >}}
{{</ changelog >}} -->
