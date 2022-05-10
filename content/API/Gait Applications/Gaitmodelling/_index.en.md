---
title: "Application of a conventional Gait model"
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 1
---

### Application of the CGM2.1


This code shows how you can apply the CGM2.1 on your c3d trials.

{{< notice "tip" >}}
  You can replicate the process on all CGM. Just check out the input arguments of the calibration and fitting operations
{{< /notice >}}


```python
# -*- coding: utf-8 -*-
import os
import pyCGM2
from pyCGM2.Utils import files
from pyCGM2.Tools import btkTools
from pyCGM2.ForcePlates import forceplates
from pyCGM2 import enums
from pyCGM2.Lib.CGM import cgm2_1

LOGGER = pyCGM2.LOGGER


# data
DATA_PATH = "C:\\myPATH\\"
staticFile ="03367_05136_20200604-SBNNN-VDEF-02.c3d" # static trial
trialName = "03367_05136_20200604-GBNNN-VDEF-01.c3d" # gait trial


# setting
settings = files.loadModelSettings(DATA_PATH,"CGM2_1-pyCGM2.settings")

# CGM2.1 CALIBRATION
#-------------------

acqStatic = btkTools.smartReader(DATA_PATH+staticFile) # construct the btk.Acquisition instance

# calibration options from settings
leftFlatFoot = settings["Calibration"]["Left flat foot"]
rightFlatFoot= settings["Calibration"]["Right flat foot"]
headFlat= settings["Calibration"]["Head flat"]
translators = settings["Translators"]
markerDiameter = settings["Global"]["Marker diameter"]
HJC = settings["Calibration"]["HJC"]
pointSuffix = settings["Global"]["Point suffix"]

# anthropometric parameters
required_mp = dict()
required_mp["Bodymass"] = 75.0
required_mp["Height"]= 1750
required_mp["LeftLegLength"] = 800
required_mp["LeftKneeWidth"] = 90
required_mp["RightLegLength"] = 800
required_mp["RightKneeWidth"] = 90
required_mp["LeftAnkleWidth"] = 60
required_mp["RightAnkleWidth"] = 60
required_mp["LeftSoleDelta"] = 0
required_mp["RightSoleDelta"] = 0
required_mp["LeftShoulderOffset"] = 0
required_mp["LeftElbowWidth"] = 0
required_mp["LeftWristWidth"] = 0
required_mp["LeftHandThickness"] = 0
required_mp["RightShoulderOffset"] = 0
required_mp["RightElbowWidth"] = 0
required_mp["RightWristWidth"] = 0
required_mp["RightHandThickness"]= 0

optional_mp = dict()
optional_mp["InterAsisDistance"]= 0
optional_mp["LeftAsisTrocanterDistance"]= 0
optional_mp["LeftTibialTorsion"]= 0
optional_mp["LeftThighRotation"]= 0
optional_mp["LeftShankRotation"]= 0
optional_mp["RightAsisTrocanterDistance"]= 0
optional_mp["RightTibialTorsion"]= 0
optional_mp["RightThighRotation"]= 0
optional_mp["RightShankRotation"]= 0

# calibrate function
model,finalAcqStatic,error = cgm2_1.calibrate(DATA_PATH,
    staticFile,
    translators,
    required_mp,
    optional_mp,
    leftFlatFoot,
    rightFlatFoot,
    headFlat,
    markerDiameter,
    HJC,
    pointSuffix)

# CGM2.1 FITTING
#----------------

# fitting options from settings
momentProjection = enums.enumFromtext(settings["Fitting"]["Moment Projection"],enums.MomentProjection)
pointSuffix = settings["Global"]["Point suffix"]

# force plate assignement
acq = btkTools.smartReader(DATA_PATH+trialName) # btk.Acquisition instance
mfpa = forceplates.matchingFootSideOnForceplate(acq) #detect correct foot contact with a force plate

# fitting function

acqGait,detectAnomaly = cgm2_1.fitting(model,DATA_PATH, trialName,
    translators,
    markerDiameter,
    pointSuffix,
    mfpa,
    momentProjection,
    frameInit= None, frameEnd= None )# acqGait updated with CGM2.1 ouputs ( kinematics and kinetics)

# EXPORT
# -------
btkTools.smartWriter(acqGait, DATA_PATH+trialName[:-4]+"-modelled.c3d") # save the btk.Acquisition instance as a new c3d with the suffix "-modelled"

```

Briefly, the code above,

 1. constructs `btk.Acquisition` instances from your static and gait trial c3d files.
 2. calls settings of the CGM2.1 and extract from them the  model options ( eg `left flat Foot` options).
 3. loads the required anthropometric data
 4. calibrates the CGM2.1
 5. applies the fitting operation on the gait trial to get kinematics and kinetics.

Eventually, the code exports CGM2.1 outputs in a new c3d file suffixed with `-modelled.c3d`

{{< notice "note" >}}
  As you can see, the code calls the settings from the file `CGM2_1-pyCGM2.settings`. Unless your data folder does not contain this file,
  the code will load by default the file located in the folder `pyCGM2/Settings/CGM2_1-pyCGM2.settings`
{{< /notice >}}
