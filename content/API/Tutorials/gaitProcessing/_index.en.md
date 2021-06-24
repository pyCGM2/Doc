---
title: "Process your gait data"
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 2
---


In this tutorial, we show how you can work with gait data. We introduce the file `analysis.py`  and `plot.py` from the `lib` module.

By gait data, we mean you applied a model on your marker. c3d files contain :
  * gait events
  * model outputs


The following code show how you can report conventional kinematic plots, kinetic plot panels and spatio-temporal parameter representation    

```python
import pyCGM2
from pyCGM2.Report import normativeDatasets
from pyCGM2.Lib import analysis
from pyCGM2.Lib import plot

DATA_PATH = "c:\\pathTomydata\\"
modelledFilenames = ["gait Trial 01.c3d", "gait Trial 02.c3d"]

analysisInstance = analysis.makeAnalysis(DATA_PATH, modelledFilenames)

normativeDataset = normativeDatasets.NormativeData("Schwartz2008","Free") # refer to the normative dataset from swartz 2008

plot.plot_DescriptiveKinematic(DATA_PATH,analysisInstance,"LowerLimb",normativeDataset)
plot.plot_DescriptiveKinetic(DATA_PATH,analysisInstance,"LowerLimb",normativeDataset)
plot.plot_spatioTemporal(DATA_PATH,analysisInstance)

analysis.exportAnalysis(analysisInstance,DATA_PATH,"spreadsheet")

```

The central object is the `analysisInstance` built from the function  `makeAnalysis`.
This function time-normalize all model data (ie kinematic and kinetic model outputs) and all emg analog channels, then gather everything in a **single instance**.
By default in pyCGM2, the emg channels are labelled :

```
["Voltage.EMG1","Voltage.EMG2",....,Voltage.EMG16]
```

From the `analysisInstance`, you can simply call convenient plot functions and export as xlsx spreadsheet.  


### Advanced use of `makeAnalysis`

#### Add metadata information

We input information relative to the subject, the experiment itself or the model from basic dictionnaries

This metadata information will appear in each sheet of the exported xlsx spreasheet

```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```

#### Do not deal with emg channels

Set `emgChannels = None` just disable the

```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    emgChannels = None
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```



#### Process specific model outputs  

In the code below, we focus on specific kinematic and kinetic model outputs. We normalize the outputs   
`LHipAngles` and `LKneeAngles` with `Left` gait events and `RHipAngles` and `RKneeAngles` with `Right` gait events.
The process is similar for kinetic outputs. `LHipMoment` and `LKneePower` with `Left` gait events and `RHipMoment` and `RKneePower` with `Right` gait events.    

```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    kinematicLabelsDict = {"Left":["LHipAngles","LKneeAngles"],"Right":["RHipAngles","RKneeAngles"]},
                    kineticLabelsDict   = {"Left":["LHipMoment","LKneePower"],"Right":["RHipMoment","RKneePower"]},
                    emgChannels = None
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```

#### process specific emg channels

Instead of calling defaut emg channels named   `["Voltage.EMG1","Voltage.EMG2",....,Voltage.EMG16]`, the code below called the analog channels named  `['myEMG1','myEMG2']` only


```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    emgChannels = ['myEMG1','myEMG2']
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```



#### compute Spatio-temporal parameters, Kinematics, kinetics and emg from different ciles  


This is an extreme context. in this example, we call different c3d files for computing spatiotempral data, kinematics, kinetics and emg.
It's done trhough the keyword arguments:

 * pstfilenames
 * kinematicfilenames
 * kineticfilenames
 * emgfilenames

For instance, in the code below, `["Gait1.c3d","Gait2.c3d"]` are used for computing the spatio-temporal parameters.

```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    None,
                    kinematicLabelsDict = {"Left":["LHipAngles","LKneeAngles"],"Right":["RHipAngles","RKneeAngles"]},
                    kineticLabelsDict   = {"Left":["LHipMoment","LKneePower"],"Right":["RHipMoment","RKneePower"]},
                    emgChannels = None
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    pstfilenames = ["Gait1.c3d","Gait2.c3d"],
                    kinematicfilenames = ["Gait3.c3d","Gait4.c3d"],
                    kineticfilenames = ["Gait5.c3d","Gait6.c3d"] ,
                    emgfilenames = ["Gait7.c3d","Gait8.c3d"]
                    )

```
