---
title: pyCGM2.Lib.plot
---

# <kbd>module</kbd> `pyCGM2.Lib.plot`
This module gathers convenient functions fro plotting Kinematic - Kinetic and EMG 


---

## <kbd>function</kbd> `plotTemporalKinematic`

```python
plotTemporalKinematic(
    DATA_PATH,
    modelledFilename,
    bodyPart,
    pointLabelSuffix=None,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False,
    **kwargs
)
```

plotTemporalKinematic : display temporal trace of the CGM kinematic outputs 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`modelledFilenames`</b> (str):  name of your c3d including kinematic output 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`pointLabelSuffix`</b> (str):  suffix previously added to your model outputs. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None] `</b>:  suffix previously added to your model outputs. 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf. 
 - <b>`outputName (str)[None]`</b>:  name of the output file . 
 - <b>`show (bool)[True]`</b>:  show the matplotlib figure  . 
 - <b>`title (str)[None]`</b>:  modify plot panel title 
 - <b>`exportPng (bool)[False]`</b>: export as png . 

****


Keyword Args (low-level): 
 - <b>`btkAcq (btk.Acquisition)[None]`</b>:  force use of a btkAcquisition instead of loading from `modelledFilename`. 

****




**Returns:**
 

****




****




**Examples:**
 

****


```python
plotTemporalKinematic("C:\myDATA\", "file1.c3d","LowerLimb")
``` 


---

## <kbd>function</kbd> `plotTemporalKinetic`

```python
plotTemporalKinetic(
    DATA_PATH,
    modelledFilenames,
    bodyPart,
    pointLabelSuffix=None,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False,
    **kwargs
)
```

plotTemporalKinetic : display temporal trace of the CGM kinetic outputs 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`modelledFilenames`</b> (str):  name of your c3d including kinematic output 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`pointLabelSuffix`</b> (str):  suffix previously added to your model outputs. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None] `</b>:  suffix previously added to your model outputs. 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf. 
 - <b>`outputName (str)[None]`</b>:  name of the output file . 
 - <b>`show (bool)[True]`</b>:  show the matplotlib figure  . 
 - <b>`title (str)[None]`</b>:  modify plot panel title 
 - <b>`exportPng (bool)[False]`</b>: export as png . 

****


Keyword Args (low-level): 
 - <b>`btkAcq (btk.Acquisition)[None]`</b>:  force use of a btkAcquisition instead of loading from `modelledFilename`. 

****




****




****




**Examples:**
 

****


```python
plotTemporalKinetic("C:\myDATA\", "file1.c3d","LowerLimb")
``` 


---

## <kbd>function</kbd> `plotTemporalEMG`

```python
plotTemporalEMG(
    DATA_PATH,
    processedEmgfile,
    emgSettings,
    rectify=True,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    ignoreNormalActivity=False,
    exportPng=False,
    OUT_PATH=None,
    **kwargs
)
```

Display temporal traces of EMG signals 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`processedEmgfile`</b> (str):  name of your c3d file with emg. 
 - <b>`emgSettings`</b> (str):  content of the emg.setting file. 

****




**Keyword Args:**
 
 - <b>`rectify (bool)[True]`</b>:  display rectify or raw signal . 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf (default: False). 
 - <b>`outputName (str)[None]`</b>:  name of the output file. 
 - <b>`show (bool)[True]`</b>:  show the matplotlib figure (default: True) . 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`ignoreNormalActivity (bool)[False]`</b>:  disable display of normal activity in the background. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 
 - <b>`OUT_PATH (str)[None]`</b>:  specify an path different than the `DATA_PATH` to export plot 

****


Keyword Args (low-level): 
 - <b>`btkAcq (btk.Acquisition)[None]`</b>:  force use of a btkAcquisition instead of loading from `processedEmgfile`. 

****




**Examples:**
 

****


```python
plotTemporalEMG("C:\myDATA\", "file1.c3d", emgSettingsContent)
``` 


---

## <kbd>function</kbd> `plotDescriptiveEnvelopEMGpanel`

```python
plotDescriptiveEnvelopEMGpanel(
    DATA_PATH,
    analysis,
    emgSettings,
    normalized=False,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display average and standard deviation of time-normalized EMG envelops. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`emgSettings`</b> (str):  content of the emg.Settings file 

****




**Keyword Args:**
 
 - <b>`normalized (bool)[False]`</b>:  enable plot of emg normalized in amplitude . 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 

****




****




**Examples:**
 

****


```python
plotDescriptiveEnvelopEMGpanel("C:\myDATA\", analysisInstance, emgSettingsContent)
``` 


---

## <kbd>function</kbd> `plotConsistencyEnvelopEMGpanel`

```python
plotConsistencyEnvelopEMGpanel(
    DATA_PATH,
    analysis,
    emgSettings,
    normalized=False,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display all-cycles of time-normalized EMG envelops. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`emgSettings`</b> (str):  content of the emg.Settings file 

****




**Keyword Args:**
 
 - <b>`normalized (bool)[False]`</b>:  enable plot of emg normalized in amplitude. 
 - <b>`type (str)[Gait]`</b>:  type of events . if different to *Gait*, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[True]`</b>:  export as png. 

****




**Returns:**
 

****




****




**Examples:**
 

****


```python
plotConsistencyEnvelopEMGpanel("C:\myDATA\", analysisInstance, emgSettingsContent)
``` 


---

## <kbd>function</kbd> `plot_spatioTemporal`

```python
plot_spatioTemporal(
    DATA_PATH,
    analysis,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display spatio-temporal parameters as horizontal histogram. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 

****




**Keyword Args:**
 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
plot_spatioTemporal("C:\myDATA\", analysisInstance)
``` 


---

## <kbd>function</kbd> `plot_DescriptiveKinematic`

```python
plot_DescriptiveKinematic(
    DATA_PATH,
    analysis,
    bodyPart,
    normativeDataset,
    pointLabelSuffix=None,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display average and standard deviation of time-normalized kinematic output. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
plot_DescriptiveKinematic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `plot_ConsistencyKinematic`

```python
plot_ConsistencyKinematic(
    DATA_PATH,
    analysis,
    bodyPart,
    normativeDataset,
    pointLabelSuffix=None,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display all cycles of time-normalized kinematic output. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




**Examples:**
 

****


```python
plot_ConsistencyKinematic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `plot_DescriptiveKinetic`

```python
plot_DescriptiveKinetic(
    DATA_PATH,
    analysis,
    bodyPart,
    normativeDataset,
    pointLabelSuffix=None,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display average and standard deviation of time-normalized kinetic outputs. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
plot_DescriptiveKinetic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `plot_ConsistencyKinetic`

```python
plot_ConsistencyKinetic(
    DATA_PATH,
    analysis,
    bodyPart,
    normativeDataset,
    pointLabelSuffix=None,
    type='Gait',
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    exportPng=False
)
```

display all cycles of time-normalized kinetic outputs. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
plot_ConsistencyKinetic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `plot_MAP`

```python
plot_MAP(
    DATA_PATH,
    analysis,
    normativeDataset,
    exportPdf=False,
    outputName=None,
    pointLabelSuffix=None,
    show=True,
    title=None,
    exportPng=False
)
```

display histogram of the Movement Analysis Profile. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

**Keyword Args:**
 
 - <b>`pointLabelSuffix (str)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
plot_MAP("c:\mydata\",analysisInstance,normativeInstance)
``` 


---

## <kbd>function</kbd> `compareKinematic`

```python
compareKinematic(
    DATA_PATH,
    analyses,
    legends,
    context,
    bodyPart,
    normativeDataset,
    plotType='Descriptive',
    type='Gait',
    pointSuffixes=None,
    show=True,
    title=None,
    outputName=None,
    exportPng=False,
    exportPdf=False
)
```

plot kinematics from different analysis instances. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`context`</b> (str):  event context 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`plotType (str)["Descrptive"]`</b>:  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type (str)[Gait]`</b>:  type of events . if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes (list)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




****




****




**Examples:**
 

****


```python
compareKinematic("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"],"Left","LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `compareKinetic`

```python
compareKinetic(
    DATA_PATH,
    analyses,
    legends,
    context,
    bodyPart,
    normativeDataset,
    plotType='Descriptive',
    type='Gait',
    pointSuffixes=None,
    show=True,
    title=None,
    outputName=None,
    exportPng=False,
    exportPdf=False
)
```

plot kinetics from different analysis instances. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`context`</b> (str):  event context 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 

****




**Keyword Args:**
 
 - <b>`plotType (str)["Descrptive"]`</b>:  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type (str)[Gait]`</b>:  type of events . if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes (list)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
compareKinetic("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"],"Left","LowerLimb",normativeInstance)
``` 


---

## <kbd>function</kbd> `compareEmgEnvelops`

```python
compareEmgEnvelops(
    DATA_PATH,
    analyses,
    legends,
    emgSettings,
    normalized=False,
    plotType='Descriptive',
    show=True,
    title=None,
    type='Gait',
    outputName=None,
    exportPng=False,
    exportPdf=False
)
```

plot EMG envelops from different analysis instances. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`emgSettings`</b> (str):  content of the emg.Settings file 

****




**Keyword Args:**
 
 - <b>`normalized (bool)[False]`</b>:  enable plot of emg normalized in amplitude . 
 - <b>`plotType (str)["Descrptive"]`</b>:  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type (str)[Gait]`</b>:  type of events . if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes (list)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




****




**Examples:**
 

****


```python
compareEmgEnvelops("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"], emgSettings)
``` 


---

## <kbd>function</kbd> `compareSelectedEmgEvelops`

```python
compareSelectedEmgEvelops(
    DATA_PATH,
    analyses,
    legends,
    emgChannels,
    contexts,
    normalized=False,
    plotType='Descriptive',
    type='Gait',
    show=True,
    title=None,
    outputName=None,
    exportPng=False,
    exportPdf=False
)
```

compare selected EMG envelops from different analysis instances constructed from the same session. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`contexts`</b> (list):  event contexts (matched with side of the emg channels). 

****




**Keyword Args:**
 
 - <b>`normalized (bool)[False]`</b>:  enable plot of emg normalized in amplitude . 
 - <b>`plotType (str)["Descrptive"]`</b>:  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type (str)[Gait]`</b>:  type of events . if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes (list)[None]`</b>: suffix previously added to your model outputs. 
 - <b>`show (bool)[True]`</b>:  show matplotlib figure. 
 - <b>`type (str)[Gait]`</b>:  type of events. if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf (bool)[False]`</b>:  export as pdf 
 - <b>`outputName (str)[None]`</b>:  name of the output filename. 
 - <b>`title (str)[None]`</b>:  modify the plot panel title. 
 - <b>`exportPng (bool)[False]`</b>:  export as png. 

****




**Examples:**
 

****


The following code plots the channel *Voltage.EMG1* time-normalized according *Left* events included in *analysisInstance1* with *Voltage.EMG2* time-normalized according *Left* events included in  *analysisInstance2*. 

****


```python
compareSelectedEmgEvelops("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"], ["Voltage.EMG1","Voltage.EMG2"], ["Left","Left"])
``` 



