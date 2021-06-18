---
title: pyCGM2.Lib.analysis
---

# <kbd>module</kbd> `pyCGM2.Lib.analysis`





---

## <kbd>function</kbd> `makeAnalysis`

```python
makeAnalysis(
    DATA_PATH,
    filenames,
    type='Gait',
    kinematicLabelsDict={'Left': ['LHipAngles', 'LKneeAngles', 'LAnkleAngles', 'LFootProgressAngles', 'LPelvisAngles', 'LForeFootAngles', 'LThoraxAngles', 'LSpineAngles', 'LNeckAngles', 'LHeadAngles', 'LShoulderAngles', 'LElbowAngles', 'LWristAngles'], 'Right': ['RHipAngles', 'RKneeAngles', 'RAnkleAngles', 'RFootProgressAngles', 'RPelvisAngles', 'RForeFootAngles', 'RThoraxAngles', 'RSpineAngles', 'RNeckAngles', 'RHeadAngles', 'RShoulderAngles', 'RElbowAngles', 'RWristAngles']},
    kineticLabelsDict={'Left': ['LHipMoment', 'LKneeMoment', 'LAnkleMoment', 'LHipPower', 'LKneePower', 'LAnklePower'], 'Right': ['RHipMoment', 'RKneeMoment', 'RAnkleMoment', 'RHipPower', 'RKneePower', 'RAnklePower']},
    emgChannels=['Voltage.EMG1', 'Voltage.EMG2', 'Voltage.EMG3', 'Voltage.EMG4', 'Voltage.EMG5', 'Voltage.EMG6', 'Voltage.EMG7', 'Voltage.EMG8', 'Voltage.EMG9', 'Voltage.EMG10', 'Voltage.EMG11', 'Voltage.EMG12', 'Voltage.EMG13', 'Voltage.EMG14', 'Voltage.EMG15', 'Voltage.EMG16'],
    pointLabelSuffix=None,
    btkAcqs=None,
    subjectInfo=None,
    experimentalInfo=None,
    modelInfo=None,
    pstfilenames=None,
    kinematicfilenames=None,
    kineticfilenames=None,
    emgfilenames=None
)
```

This function normalises data in time and returns an **Analysis Instance** ie a nested dictionnary  containing  spatiotemporal parameters, normalized kinematics, normalized kinetics and normalized EMG envelops from a list of c3d files. 

 By default: the function calls : 

 * kinematic and kinetic ouputs of the CGM  * emg channels names Voltage.EMG1 to Voltage.EMG16 

 You can also compute spatiotemporal parameters, normalized kinematics, normalized kinetics and normalized EMG envelops  from different set of c3d files. For that, use the named arguments : 

 * pstfilenames  * kinematicfilenames  * kineticfilenames  * emgfilenames 







**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path [REQUIRED] 
 - <b>`filenames`</b> (list):  list of c3d files to normalize [REQUIRED] 
 - <b>`type`</b> (str):  event type (choice : "Gait" or "unknown"). 
 - <b>`kinematicLabelsDict`</b> (dict):  dictionnary containing kinematic data to normalize. 
 - <b>`kineticLabelsDict`</b> (dict):  dictionnary containing kinetic data to normalize. 
 - <b>`emgChannels`</b> (list):  list of emg channel 
 - <b>`pointLabelSuffix`</b> (str):  suffix associated to pont output 
 - <b>`btkAcqs`</b> (list of btk.Acquisition):  btkAcq instances to process instead of calling c3d file. 
 - <b>`subjectInfo`</b> (dict):  dictionnary with metadata information about the subject. 
 - <b>`experimentalInfo`</b> (dict):  dictionnary with metadata information about the expreiment. 
 - <b>`modelInfo`</b> (dict):  dictionnary with metadata information about the model. 
 - <b>`pstfilenames`</b> (list):  list of c3d files used for computing spatiotemporal parameters 
 - <b>`kinematicfilenames`</b> (list):  list of c3d files used to normalize kinematic data 
 - <b>`kineticfilenames`</b> (list):  list of c3d files used to normalize kinetic data 
 - <b>`emgfilenames`</b> (list):  list of c3d files used to normalize emg data 



**Returns:**
 
 - <b>`pyCGM2.Processing.analysis.Analysis`</b>:  analysis instance 





**Examples:**
 

``` analysisInstance2 = analysis.makeAnalysis(DATA_PATH,         [file1.c3d,"file2.c3d"],         type="Gait",         kinematicLabelsDict = {"Left": ["LHipAngles,LKneeAngles"], "Right": ["RHipAngles,RKneeAngles"]},         kineticLabelsDict = {"Left": ["LHipMoment,LKneePower"], "Right": ["RHipMoment,RKneeMoment"],         emgChannels = ["Voltage.EMG1","Voltage.EMG2","Voltage.EMG3"],         pointLabelSuffix="cgm1",         subjectInfo = {"Name":"Doe","Firstname":"John"},         experimentalInfo = {"Barefoot":"No"},         modelInfo = {"Model":"CGM1"})```



---

## <kbd>function</kbd> `exportAnalysis`

```python
exportAnalysis(analysisInstance, DATA_PATH, name, mode='Advanced')
```

export an Analysis instance as excel spreadsheet. 



**Args:**
 
 - <b>`analysisInstance`</b> (pyCGM2.Processing.analysis.Analysis):  Analysis instance. 
 - <b>`DATA_PATH`</b> (str): folder path 
 - <b>`name`</b> (str):  name of your excel file. 
 - <b>`mode`</b> (str):  spreadsheet mode . ("Advanced or basic") 


---

## <kbd>function</kbd> `automaticCPdeviations`

```python
automaticCPdeviations(
    DATA_PATH,
    analysis,
    reference='Nieuwenhuys2017',
    pointLabelSuffix=None,
    filterTrue=False,
    export=True,
    outputname='Nieuwenhuys2017'
)
```







