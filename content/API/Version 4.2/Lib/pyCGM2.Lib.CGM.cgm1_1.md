---
title: pyCGM2.Lib.CGM.cgm1_1
---

# <kbd>module</kbd> `pyCGM2.Lib.CGM.cgm1_1`


****





---

## <kbd>function</kbd> `calibrate`

```python
calibrate(
    DATA_PATH,
    calibrateFilenameLabelled,
    translators,
    required_mp,
    optional_mp,
    leftFlatFoot,
    rightFlatFoot,
    headFlat,
    markerDiameter,
    pointSuffix,
    **kwargs
)
```

CGM1.1 calibration. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path. 
 - <b>`calibrateFilenameLabelled`</b> (str):  filename of your static file. 
 - <b>`translators`</b> (dict):  marker translators. 
 - <b>`required_mp`</b> (dict):   required anthropometric parameter. 
 - <b>`optional_mp`</b> (dict):  optional anthropometric parameter.. 
 - <b>`leftFlatFoot`</b> (bool):  flat foot option. 
 - <b>`rightFlatFoot`</b> (bool):  flat foot option. 
 - <b>`headFlat`</b> (bool):  flat head option. 
 - <b>`markerDiameter`</b> (float):  marker diameter 
 - <b>`pointSuffix`</b> (str):  suffix to add to ouputs 

****


Low-level Keyword Args : 
 - <b>`anomalyException`</b> (bool):  raise exception if anomaly detected 
 - <b>`forceBtkAcq`</b> (btk.Acquisition):  use a btkAcquisition instance instead of building the btkAcquisition from the static filename 
 - <b>`displayCoordinateSystem`</b> (bool):  return virtual markers for visualisation of the anatomical refentials 
 - <b>`noKinematicsCalculation (bool) `</b>:  disable computation of joint kinematics 

****




**Returns:**
 
 - <b>`pyCGM2.Model`</b>:  the calibrated Model 
 - <b>`Btk.Acquisition `</b>:  static btkAcquisition instance with model ouputs 
 - <b>`bool`</b>:  presence of deteced anomalies 


---

## <kbd>function</kbd> `fitting`

```python
fitting(
    model,
    DATA_PATH,
    reconstructFilenameLabelled,
    translators,
    markerDiameter,
    pointSuffix,
    mfpa,
    momentProjection,
    **kwargs
)
```

CGM1.1 Fitting. 

****




**Args:**
 
 - <b>`DATA_PATH`</b> (str):  folder path. 
 - <b>`reconstructFilenameLabelled`</b> (str):  filename of your gait trial. 
 - <b>`translators`</b> (dict):  marker translators. 
 - <b>`markerDiameter`</b> (float):  marker diameter 
 - <b>`pointSuffix`</b> (str):  suffix to add to ouputs 
 - <b>`mfpa`</b> (str):  force plate assignment 
 - <b>`momentProjection (str) `</b>:  referential for projection of joint moment 

****


Low-level Keyword Args : 
 - <b>`anomalyException`</b> (bool):  raise exception if anomaly detected 
 - <b>`forceBtkAcq`</b> (btk.Acquisition):  use a btkAcquisition instance instead of building the btkAcquisition from the static filename 
 - <b>`frameInit`</b> (int):   frame index. 
 - <b>`frameEnd`</b> (int):   frame index 
 - <b>`fc_lowPass_marker`</b> (float):  low-pass fiter cutoff frequency applied on marker trajectories 
 - <b>`order_lowPass_marker`</b> (int):  order of the low-pass filter applied on marker trajectories 
 - <b>`fc_lowPass_forcePlate`</b> (float):  low-pass fiter cutoff frequency applied on force plate measurements 
 - <b>`order_lowPass_forcePlate`</b>:  order fiter cutoff frequency applied on force plate measurements 
 - <b>`displayCoordinateSystem`</b> (bool):  return virtual markers for visualisation of the anatomical refentials 
 - <b>`noKinematicsCalculation (bool) `</b>:  disable computation of joint kinematics 

****




**Returns:**
 
 - <b>`Btk.Acquisition `</b>:   btkAcquisition instance with model ouputs 
 - <b>`bool`</b>:  presence of deteced anomalies 



