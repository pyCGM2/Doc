---
title: "Process your gait data"
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 2
---


Here, we show how you can work with c3d files incorporating **CGM#i model outputs** and **gait events**.

The code introduces the `analysis` object which contain time-normalized results under  
 specific conditions ( ie, barefoot spontaneous gait, fast gait with shoes.... )


## Basic process

```python
import pyCGM2
from pyCGM2.Report import normativeDatasets
from pyCGM2.Lib import analysis
from pyCGM2.Lib import plot

# data
DATA_PATH = "c:\\pathTomydata\\"
modelledFilenames = ["gait Trial 01.c3d", "gait Trial 02.c3d"] # two gait trials with both gait event and CGMi model ouptuts


analysisInstance = analysis.makeAnalysis(DATA_PATH, modelledFilenames,
                                          emgChannels=None) # construction of the analysis instance.
normativeDataset = normativeDatasets.NormativeData("Schwartz2008","Free") # selected normative dataset

# plots
plot.plot_DescriptiveKinematic(DATA_PATH,analysisInstance,"LowerLimb",normativeDataset)
plot.plot_DescriptiveKinetic(DATA_PATH,analysisInstance,"LowerLimb",normativeDataset)
plot.plot_spatioTemporal(DATA_PATH,analysisInstance)

# export as spreadsheet
analysis.exportAnalysis(analysisInstance,DATA_PATH,"spreadsheet")

```

The code

 1. returns plot panels of the kinematics, kinetics and spatio-temporal parameters.
 2. export your result in a excel spreadsheet    


The central object is the `analysisInstance` built from the function  `makeAnalysis`.
This function time-normalizes all model ouptuts (ie kinematic and kinetic model outputs, plus all emg analog channels), then return an `analysis` instance


## Advanced use 

### Add metadata information

We input information relative to the subject, the experiment itself or the model as basic dictionaries

This metadata information will appear in each sheet of the exported xlsx spreasheet as column

```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    emgChannels= None,
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```


### Process specific model outputs  

Instead of to time-normalized all CGM model outputs, the code below deals with specific kinematic or kinetic parameters


```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    modelledFilenames,
                    kinematicLabelsDict = {"Left":["LHipAngles","LKneeAngles"],"Right":["RHipAngles","RKneeAngles"]},
                    kineticLabelsDict   = {"Left":["LHipMoment","LKneePower"],"Right":["RHipMoment","RKneePower"]},
                    emgChannels = None,
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    )

```
`kinematicLabelsDict` is a dictionary with two entries (ie  `Left` and  `right`) which defined the event context used for time-normalized a CGM ouptut.
In the above case, the `LHipAngles` and `LKneeAngles` are time-normalized with `Left` gait events and `RHipAngles` and `RKneeAngles` with `Right` gait events.

The process is similar for kinetic outputs `kineticLabelsDict`. `LHipMoment` and `LKneePower` are time-normalized with `Left` gait events and `RHipMoment` and `RKneePower` with `Right` gait events.    


### work with different set of c3d  


This is an particular case a gait analyst might encounter.

In this example, the spatio-temporal parameters , kinematic results and kinetics results are computed for different c3d files.


```python
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    None,
                    kinematicLabelsDict = {"Left":["LHipAngles","LKneeAngles"],"Right":["RHipAngles","RKneeAngles"]},
                    kineticLabelsDict   = {"Left":["LHipMoment","LKneePower"],"Right":["RHipMoment","RKneePower"]},
                    emgChannels = None,
                    subjectInfo={"Name":"Hannibal"},
                    experimentalInfo={"Context":"Post-Toxin"},
                    modelInfo={"model":"CGM"},
                    pstfilenames = ["Gait1.c3d","Gait2.c3d"],
                    kinematicfilenames = ["Gait3.c3d","Gait4.c3d"],
                    kineticfilenames = ["Gait5.c3d","Gait6.c3d"]
                    )

```

This process is enable from the presence of the keyword arguments:

 * `pstfilenames`
 * `kinematicfilenames`
 * `kineticfilenames`
 * `emgfilenames`

In the above code :

 - the spatio-temporal parameters are calculated from  `["Gait1.c3d","Gait2.c3d"]`
 - the kinematic results are calculated from  `["Gait3.c3d","Gait4.c3d"]`
 - the kinetic results are calculated from  `["Gait5.c3d","Gait6.c3d"]`
