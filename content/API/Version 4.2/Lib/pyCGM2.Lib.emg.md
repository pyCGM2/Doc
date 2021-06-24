---
title: pyCGM2.Lib.emg
---

# <kbd>module</kbd> `pyCGM2.Lib.emg`


****





---

## <kbd>function</kbd> `loadEmg`

```python
loadEmg(DATA_PATH)
```

Load and manage emg settings 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path. 

****




**Returns:**
 
 - <b>`pyCGM2.EMG.EmgManger`</b>:  an emg manager class instance 


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

basic filtering of EMG from c3d files . 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path. 
 - <b>`gaitTrials`</b> (str):  list of c3d files. 
 - <b>`emgChannels`</b> (list):  list or emg channel 

****




**Keyword Args:**
 
 - <b>`highPassFrequencies (list)[20,200]`</b>:  boundaries of the bandpass filter 
 - <b>`envelopFrequency (float)[6.0]`</b>:  cut-off frequency of low pass emg 
 - <b>`fileSuffix (str)[None]`</b>:  add a suffix to the exported c3d files 
 - <b>`outDataPath (str)[None]`</b>:  path to place the exported c3d files. 

****


Examples 

****


```python
emg.processEMG(DATA_PATH, ["file1.c3d","file2.c3d"], ["Voltage.EMG1","Voltage.EMG2"])
``` 


---

## <kbd>function</kbd> `normalizedEMG`

```python
normalizedEMG(
    DATA_PATH,
    analysis,
    method='MeanMax',
    fromOtherAnalysis=None,
    mvcSettings=None
)
```

Emg normalisation in amplitude. 

****


This function update the analysis instance with normalized emg signal in amplitude 

****




**Args:**
 
 - <b>`analysis`</b> (pyCGM2.Processing.analysis.Analysis):  an analysis Instance 
 - <b>`DATA_PATH`</b> (str):  folder path 

****




**Keyword Args:**
 
 - <b>`method (str)["MeanMax"]`</b>:  normalisation method (choice : MeanMax, MaxMax, MedianMax ). 
 - <b>`fromOtherAnalysis (pyCGM2.Processing.analysis.Analysis)[None]`</b>:  normalise in amplitude from another analysis instance. 
 - <b>`mvcSettings (dict)[None]`</b>:  mvc settings. 

****




****




****




**Examples:**
 

****


```python
emg.normalizedEMG(emgAnalysisInstance,
.................["Voltage.EMG1","Voltage.EMG2"],
.................["Left","Right"],
.................method="MeanMax",
.................fromOtherAnalysis=emgAnalysisInstancePreBloc)
``` 


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



****






