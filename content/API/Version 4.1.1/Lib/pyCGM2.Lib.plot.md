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
    modelledFilenames,
    bodyPart,
    pointLabelSuffix=None,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    btkAcq=None,
    exportPng=False
)
```

plotTemporalKinematic : display temporal trace of the CGM kinematic outputs 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`modelledFilenames`</b> (str):  name of your c3d including kinematic output 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`pointLabelSuffix`</b> (str):  suffix previously added to your model outputs. 
 - <b>`exportPdf`</b> (bool):  export as pdf (default: False). 
 - <b>`outputName`</b> (type):  name of the output file . 
 - <b>`show`</b> (bool):  show the matplotlib figure (default: True) . 
 - <b>`title`</b> (str):  modify plot panel title 
 - <b>`btkAcq`</b> (btk.Acquisition):  Description of parameter `btkAcq`. 
 - <b>`exportPng`</b> (bool): export as png (default: False). 



**Returns:**
 





**Examples:**
 

``` plotTemporalKinematic("C:\myDATA\", "file1.c3d","LowerLimb")```



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
    btkAcq=None,
    exportPng=False
)
```

plotTemporalKinetic : display temporal trace of the CGM kinetic outputs 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`modelledFilenames`</b> (str):  name of your c3d including kinematic output 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`pointLabelSuffix`</b> (str):  suffix previously added to your model outputs. 
 - <b>`exportPdf`</b> (bool):  export as pdf (default: False). 
 - <b>`outputName`</b> (type):  name of the output file . 
 - <b>`show`</b> (bool):  show the matplotlib figure (default: True) . 
 - <b>`title`</b> (str):  modify plot panel title 
 - <b>`btkAcq`</b> (btk.Acquisition):  btk acquisition use instead of `modelledFilenames` 
 - <b>`exportPng`</b> (bool): export as png (default: False). 



**Returns:**
 





**Examples:**
 

``` plotTemporalKinetic("C:\myDATA\", "file1.c3d","LowerLimb")```



---

## <kbd>function</kbd> `plotTemporalEMG`

```python
plotTemporalEMG(
    DATA_PATH,
    processedEmgfile,
    emgChannels,
    muscles,
    sides,
    normalActivityEmgs,
    rectify=True,
    exportPdf=False,
    outputName=None,
    show=True,
    title=None,
    btkAcq=None,
    ignoreNormalActivity=False,
    exportPng=False,
    OUT_PATH=None
)
```

Display temporal traces of EMG signals 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`processedEmgfile`</b> (str):  name of your c3d file with emg. 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`muscles`</b> (list):  names of the muscles associated to each channel. 
 - <b>`sides`</b> (list):  side ( Left or Right) where the emg device was positioned 
 - <b>`normalActivityEmgs`</b> (list):  muscle used as reference for displaying normal activity in the background. 
 - <b>`rectify`</b> (bool):  display rectify or raw signal (default: True). 
 - <b>`exportPdf`</b> (bool):  export as pdf (default: False). 
 - <b>`outputName`</b> (str):  name of the output file. 
 - <b>`show`</b> (bool):  show the matplotlib figure (default: True) . 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`btkAcq`</b> (btk.Acquisition):  btk acquisition use instead of `modelledFilenames`. 
 - <b>`ignoreNormalActivity`</b> (bool):  disable display of normal activity in the background. 
 - <b>`exportPng`</b> (bool):  export as png. 
 - <b>`OUT_PATH`</b> (str):  specify an path different than the `DATA_PATH` to export plot 



**Returns:**
 





**Examples:**
 

``` plotTemporalEMG("C:\myDATA\", "file1.c3d", ["Voltage.EMG1","Voltage.EMG1"], ["RECFEM","VASLAT"], ["Left","Right"], ["RECFEM","VASLAT"])```



---

## <kbd>function</kbd> `plotDescriptiveEnvelopEMGpanel`

```python
plotDescriptiveEnvelopEMGpanel(
    DATA_PATH,
    analysis,
    emgChannels,
    muscles,
    contexts,
    normalActivityEmgs,
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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`muscles`</b> (list):  names of the muscles associated to each channel. 
 - <b>`contexts`</b> (list):  event context (Left or Right) used to display the emg envelop. It makes sense to use "Left" for event context if the emg was placed on the left RECFEM 
 - <b>`normalActivityEmgs`</b> (list):  muscle used as reference for displaying normal activity in the background. 
 - <b>`normalized`</b> (bool):  enable plot of emg normalized in amplitude (default:False). 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 



**Examples:**
 

``` plotDescriptiveEnvelopEMGpanel("C:\myDATA\", analysisInstance, ["Voltage.EMG1","Voltage.EMG1"], ["RECFEM","VASLAT"], ["Left","Right"], ["RECFEM","VASLAT"])```



---

## <kbd>function</kbd> `plotConsistencyEnvelopEMGpanel`

```python
plotConsistencyEnvelopEMGpanel(
    DATA_PATH,
    analysis,
    emgChannels,
    muscles,
    contexts,
    normalActivityEmgs,
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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`muscles`</b> (list):  names of the muscles associated to each channel. 
 - <b>`contexts`</b> (list):  event context (Left or Right) used to display the emg envelop. It makes sense to use "Left" for event context if the emg was placed on the left RECFEM 
 - <b>`normalActivityEmgs`</b> (list):  muscle used as reference for displaying normal activity in the background. 
 - <b>`normalized`</b> (bool):  enable plot of emg normalized in amplitude (default:False). 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plotConsistencyEnvelopEMGpanel("C:\myDATA\", analysisInstance, ["Voltage.EMG1","Voltage.EMG1"], ["RECFEM","VASLAT"], ["Left","Right"], ["RECFEM","VASLAT"])```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_spatioTemporal("C:\myDATA\", analysisInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`pointLabelSuffix`</b> (type): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_DescriptiveKinematic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`pointLabelSuffix`</b> (type): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_ConsistencyKinematic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`pointLabelSuffix`</b> (type): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_DescriptiveKinetic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`pointLabelSuffix`</b> (type): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_ConsistencyKinetic("c:\mydata\",analysisInstance,"LowerLimb",normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  analysis instance. 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`pointLabelSuffix`</b> (type): suffix previously added to your model outputs. 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` plot_MAP("c:\mydata\",analysisInstance,normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`context`</b> (str):  event context 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`plotType`</b> (str):  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes`</b> (list): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` compareKinematic("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"],"Left","LowerLimb",normativeInstance)```



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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`context`</b> (str):  event context 
 - <b>`bodyPart`</b> (str):  body part (choice : LowerLimb, Trunk, UpperLimb) 
 - <b>`normativeDataset`</b> (pyCGM2.Report.normativeDatasets.NormativeData):  normative data instance. 
 - <b>`plotType`</b> (str):  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`pointSuffixes`</b> (list): suffix previously added to your model outputs. 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` compareKinetic("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"],"Left","LowerLimb",normativeInstance)```



---

## <kbd>function</kbd> `compareEmgEnvelops`

```python
compareEmgEnvelops(
    DATA_PATH,
    analyses,
    legends,
    emgChannels,
    muscles,
    contexts,
    normalActivityEmgs,
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



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`muscles`</b> (list):  names of the muscles associated to each channel. 
 - <b>`contexts`</b> (list):  event context (Left or Right) used to display the emg envelop. It makes sense to use "Left" for event context if the emg was placed on the left RECFEM 
 - <b>`normalActivityEmgs`</b> (list):  muscle used as reference for displaying normal activity in the background. 
 - <b>`normalized`</b> (bool):  enable plot of emg normalized in amplitude (default:False). 
 - <b>`plotType`</b> (str):  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

``` compareEmgEnvelops("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"], ["Voltage.EMG1","Voltage.EMG1"], ["RECFEM","VASLAT"], ["Left","Right"], ["RECFEM","VASLAT"])```



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

compare selected EMG envelops from different analysis instances. 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path to your data 
 - <b>`analysis`</b> (list):  list of analysis instances. 
 - <b>`legends`</b> (list):  short label representing each analysis instances 
 - <b>`emgChannels`</b> (list):  names of your emg channels ( ie analog labels ). 
 - <b>`muscles`</b> (list):  names of the muscles associated to each channel. 
 - <b>`contexts`</b> (list):  event context (Left or Right) used to display the emg envelop. It makes sense to use "Left" for event context if the emg was placed on the left RECFEM 
 - <b>`normalized`</b> (bool):  enable plot of emg normalized in amplitude (default:False). 
 - <b>`plotType`</b> (str):  descriptive (ie average + sd) or consistency plots ( choice: Descriptive, Consistency) 
 - <b>`type`</b> (str):  type of events (default: Gait). if different to Gait, use foot strike only to define cycles 
 - <b>`exportPdf`</b> (bool):  export as pdf 
 - <b>`outputName`</b> (str):  name of the output filename. 
 - <b>`show`</b> (bool):  show matplotlib figure. 
 - <b>`title`</b> (str):  modify the plot panel title. 
 - <b>`exportPng`</b> (bool):  export as png. 



**Returns:**
 





**Examples:**
 

The following code plots the channel *Voltage.EMG1* time-normalized according *Left* events included in *analysisInstance1* with *Voltage.EMG2* time-normalized according *Left* events included in  *analysisInstance2*. 

``` compareSelectedEmgEvelops("c:\mydata\",[analysisInstance1,analysisInstance2],["pre","post"], ["Voltage.EMG1","Voltage.EMG2"], ["Left","Left"])```




