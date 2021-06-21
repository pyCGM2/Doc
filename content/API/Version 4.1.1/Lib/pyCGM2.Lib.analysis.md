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
    subjectInfo=None,
    experimentalInfo=None,
    modelInfo=None,
    **kwargs
)
```

This function normalises data in time and returns an **Analysis Instance** ie a nested dictionnary  containing  spatiotemporal parameters, normalized kinematics, normalized kinetics and normalized EMG envelops from a list of c3d files. 

 By default: the function calls : 

 * kinematic and kinetic ouputs of the CGM  * emg channels names Voltage.EMG1 to Voltage.EMG16 

 You can also compute spatiotemporal parameters, normalized kinematics, normalized kinetics and normalized EMG envelops  from different set of c3d files. For that, use the named arguments : 

 * pstfilenames  * kinematicfilenames  * kineticfilenames  * emgfilenames 







**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path 
 - <b>`filenames`</b> (list):  list of c3d files to normalize 

Keyword Args: 
 - <b>`type (str)[Gait]`</b>:  event type (choice : "Gait" or "unknown"). 
 - <b>`kinematicLabelsDict (dict)[cgm.CGM.ANALYSIS_KINEMATIC_LABELS_DICT]`</b>:  dictionnary containing kinematic data to normalize. 
 - <b>`kineticLabelsDict (dict)[cgm.CGM.ANALYSIS_KINETIC_LABELS_DICT]`</b>:  dictionnary containing kinetic data to normalize. 
 - <b>`emgChannels (list)[channels of emg.settings]`</b>:  list of emg channels 
 - <b>`pointLabelSuffix (str)[None]`</b>:  suffix associated to point output 
 - <b>`subjectInfo (dict)[None]`</b>:  dictionnary with metadata information about the subject. 
 - <b>`experimentalInfo (dict)[None]`</b>:  dictionnary with metadata information about the expreiment. 
 - <b>`modelInfo (dict)[None]`</b>:  dictionnary with metadata information about the model. 

Keyword Args (low-level): 
 - <b>`btkAcqs`</b> (list of btk.Acquisition):  btkAcq instances to process instead of calling c3d file. 
 - <b>`pstfilenames (list)[None]`</b>:  list of c3d files used for computing spatiotemporal parameters 
 - <b>`kinematicfilenames (list)[None]`</b>:  list of c3d files used to normalize kinematic data 
 - <b>`kineticfilenames (list)[None]`</b>:  list of c3d files used to normalize kinetic data 
 - <b>`emgfilenames (list)[None]`</b>:  list of c3d files used to normalize emg data 







**Returns:**
 
 - <b>`pyCGM2.Processing.analysis.Analysis`</b>:  analysis instance 





**Examples:**
 

The code below takes 2 c3d files, the time normalized kinematics, kinetics and emg. Kinematic , kinetic and emg labels are the default CGM output and emg channels from the emg.setting file 

``` analysisInstance = analysis.makeAnalysis(DATA_PATH,     [file1.c3d,"file2.c3d"])```

A more advanced use ( see below) called specific model outputs and emg channels. This code also adds a subject, experimental and model metadata:

``` analysisInstance2 = analysis.makeAnalysis(DATA_PATH,         [file1.c3d,"file2.c3d"],         kinematicLabelsDict = {"Left": ["LHipAngles,LKneeAngles"], "Right": ["RHipAngles,RKneeAngles"]},         kineticLabelsDict = {"Left": ["LHipMoment,LKneePower"], "Right": ["RHipMoment,RKneeMoment"],         emgChannels = ["Voltage.EMG1","Voltage.EMG2","Voltage.EMG3"],         subjectInfo = {"Name":"Doe","Firstname":"John"},         experimentalInfo = {"Barefoot":"No"},         modelInfo = {"Model":"CGM1"})``` 


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

Keyword Args: 
 - <b>`mode (str)[Advanced]`</b>:  spreadsheet mode . ("Advanced or Basic") 

Examples 

``` exportAnalysis(AnalysisInstance, "c:\DATA\","johnDoe")```



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







