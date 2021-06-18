---
title: pyCGM2.Lib.configuration
---

# <kbd>module</kbd> `pyCGM2.Lib.configuration`





---

## <kbd>function</kbd> `loadEmgConfiguration`

```python
loadEmgConfiguration(DATA_PATH, emgSettingsFile='emg.settings')
```

This function returns emg details from the `emg.settings` file. Unless `emg.settings` file is found in the data folder, the code loads the `emg.settings` located in `pyCGM2/Settings` 



**Args:**
 
 - <b>`DATA_PATH`</b> (str):  path with double \ at the end. 
 - <b>`emgSettingsFile`</b> (str):  name of the emg settings file ( default is `emg.settings`). 



**Returns:**
 
 - <b>`list`</b>:  channel labels 
 - <b>`list`</b>:  names of the muscle 
 - <b>`list`</b>:  context name of the muscle 
 - <b>`list `</b>:  names of the muscle set in reference for displaying its normal activity during gait 

Examples 

``` EMG_LABELS,EMG_MUSCLES,EMG_CONTEXT,NORMAL_ACTIVITIES = configuration.loadEmgConfiguration(DATA_PATH)```




