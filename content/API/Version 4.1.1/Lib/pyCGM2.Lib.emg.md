---
title: pyCGM2.Lib.emg
---

# <kbd>module</kbd> `pyCGM2.Lib.emg`





---

## <kbd>function</kbd> `processEMG`

```python
processEMG(
    DATA_PATH,
    gaitTrials,
    emgChannels,
    highPassFrequencies=[20, 200],
    envelopFrequency=6.0,
    fileSuffix=None,
    outDataPath=None
)
```

basic filtering of EMG . 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path. 
 - <b>`gaitTrials`</b> (str):  list of c3d files. 
 - <b>`emgChannels`</b> (list):  list or emg channel 
 - <b>`highPassFrequencies`</b> (list ):  boundaries of the bandpass filter 
 - <b>`envelopFrequency`</b> (float):  cut-off frequency of low pass emg 
 - <b>`fileSuffix`</b> (str):  add a suffix to the exported c3d files 
 - <b>`outDataPath`</b> (str):  path to place the exported c3d files. 

Examples 

``` emg.processEMG(DATA_PATH, ["file1.c3d","file2.c3d"], ["Voltage.EMG1","Voltage.EMG2"])```



---

## <kbd>function</kbd> `processEMG_fromBtkAcq`

```python
processEMG_fromBtkAcq(
    acq,
    emgChannels,
    highPassFrequencies=[20, 200],
    envelopFrequency=6.0
)
```






---

## <kbd>function</kbd> `normalizedEMG`

```python
normalizedEMG(
    analysis,
    emgChannels,
    contexts,
    method='MeanMax',
    fromOtherAnalysis=None,
    mvcSettings=None
)
```

Emg normalisation in amplitude. 

This function update the analysis instance with normalized emg signal in amplitude 



**Args:**
 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  an analysis Instance 
 - <b>`emgChannels`</b> (str):  list or emg channel 
 - <b>`contexts`</b> (list):  indicate event context 
 - <b>`method`</b> (str):  normalisation method (choice : MeanMax[default], MaxMax, MedianMax ). 
 - <b>`fromOtherAnalysis`</b> (pyCGM2.Processing.analysis.Analysis):  normalise in amplitude from another analysis instance. 
 - <b>`mvcSettings`</b> (dict):  mvc settings. 





Examples 

``` emg.normalizedEMG(emgAnalysisInstance,                     ["Voltage.EMG1","Voltage.EMG2"],                     ["Left","Right"],                     method="MeanMax",                     fromOtherAnalysis=emgAnalysisInstancePreBloc)```




