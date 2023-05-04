---
title: "Input argument reference "
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 5
---    
    

## CGM inputs arguments

### Calibration 

Add the `-h` to the command (e.g.  `pycgm2.exe NEXUS CGM1.0 Calibration -h`)   to know the input arguments of the CGM1.0 calibration process
( replace `CGM1.0` for other CGM ) 

**example 1**

```bash
pycgm2.exe NEXUS CGM1.0 Calibration -l 0 -r 1 -md 16 --check
```
or  
```bash
pycgm2.exe NEXUS CGM1.0 Calibration --leftFlatFoot 0 --rightFlatFoot 1 --markerDiameter 16 --check
```
=> disable the left  flat foot option, keep enable the right flat foot option, use 16mm marker diameter and add the suffix *_cgm1* to model ouputs

**example 2**
```bash
pycgm2.exe NEXUS CGM2.1 Calibration -forceLHJC 30 50 60
```
=> position the left hip joint centre relative to the pelvic coordinate system with the coodinates 30 50 and 60 


This table resumes all available arguments across CGM

| CGM     | long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| CGM1.0+ | `--leftFlatFoot` | `-l`        | `int`    | Left flat foot option                                          |
| CGM1.0+ | `--rightFlatFoot` | `-r`        | `int`    | Right flat foot option                                          |
| CGM1.0+ | `--headFlat`     | `-hf`       | `int`    | Head flat option                                               |
| CGM1.0+ | `--markerDiameter` | `-md`    | `float`  | Marker diameter                                                |
| CGM1.0+ | `--pointSuffix`  | `-ps`       | `str`    | Suffix of the model outputs                                    |
| CGM1.0+ | `--check`        |             |  | Force cgm version as model output suffix           |
| CGM1.0+ | `--resetMP`      |             |  | Reset the optional anthropometric parameters                       |
| CGM1.0+ | `--forceMP`      |             |  | Force the use of the MP offsets to compute knee and ankle joint centres |
| CGM1.0+ | `--anomalyException` | `-ae`  |  | Raise an exception if an anomaly is detected                   |
| CGM1.0+ | `--offline`      |             | `nargs=2` | offline mode, need the subject name and the static c3d filename                                |
| CGM2.1+ | `--forceLHJC`    |             | `nargs=3` | Force the position of the left hip joint centre to respect local position into the pelvic coordinate system                      |
| CGM2.1+ | `--forceRHJC`    |             | `nargs=3` | Force the position of the right hip joint centre  to respect local position into the pelvic coordinate system                     |
| CGM2.2 and 2.3 | `--musculoSkeletalModel` | `-msm` |  | enable Musculoskeletal computation                                  |
| CGM2.3+  |          |   `--noIk`          |  | disbale kinematic fitting ( aka inverse kinematics)                                        |


### Fitting 

Add the `-h` to the command (e.g.  `pycgm2.exe NEXUS CGM1.0 Fitting -h`)   to know the input arguments of the CGM1.0 calibration process
( replace `CGM1.0` for other CGM ) 

**example 1**

```bash
pycgm2.exe NEXUS CGM1.0 Fitting -md 16 --proj Proximal --pointSuffix test
```
=>  use 16mm marker diameter, project moment into the proximal coordinate system and add the suffix *_test* to model ouputs

This table resumes all available arguments across CGM

| CGM     | long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| CGM1.0+ | `--markerDiameter` | `-md`    | `float`  | Marker diameter                                                |
| CGM1.0+ | `--pointSuffix`  | `-ps`       | `str`    | Suffix of the model outputs                                    |
| CGM1.0+ | `--check`        |             |  | Force cgm version as model output suffix           |
| CGM1.0+ | `--anomalyException` | `-ae`  |  | Raise an exception if an anomaly is detected                   |
| CGM1.0+ | `--offline`      |             | `nargs=3` | offline mode, need the subject name and the gait c3d filename and the foot force plate assignment                                |
| CGM1.0+ | `--frameInit`      |   `-fi`          | `int` | initial frame to process                                |
| CGM1.0+ | `--frameEnd`      |   `-fe`          | `int` | last frame to process                                |
| CGM1.0+ | `--proj`      |             | `str` | Referential to project joint moment (choice : Distal,Proximal,Global (and JCS for CGM1.1+))                                |
| CGM2.2 and 2.3 | `--musculoSkeletalModel` | `-msm` |  | enable Musculoskeletal computation                                  |
| CGM2.3+  | `--accuracy`         |    `-a`           | `float` | inverse kinematic solver accuracy ()                                        |
| CGM2.3+  | `--noIk`         |             | `store_true` | disbale kinematic fitting ( aka inverse kinematics)                                        |


### CGM2.6

Depending your functional knee calibration method, type  `pycgm2.exe NEXUS CGM2.6 2DOF -h`)  or  `pycgm2.exe NEXUS CGM2.6 SARA -h` to know the input arguments

```bash
pycgm2.exe NEXUS CGM2.6 SARA -fi 300 -fe 600 --side Right
```
=>  calibrate the right knee from frame 300 to 600 

for both methods, the input arguments are
| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--side` | `-s`    | `str`  | body side ( Left or Right)                                                |
| `--frameInit`      |  `-fi`          | `int` | initial frame to process                                |
| `--frameEnd`      |   `-fe`          | `int` | last frame to process                                |


        
## Events

### Zeni et al 2008 - gait event detection 

```bash
pycgm2.exe NEXUS Events Zeni -fso 5
```
=>  add an offset of 5 to all detected foot strike 

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--footStrikeOffset` | `-fso`    | `int`  | systematic foot strike offset on both side                                             |
| `--footOffOffset`      |  `-foo`          | `int` | systematic foot off offset on both side                              |


## Plots

### Spatio temporal plots

```bash
pycgm2.exe NEXUS Plots STP -ps test
```
=> build panel from spatiotemporal variables suffixed *test*

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--pointSuffix`  | `-ps`       | `str`    | consider  model outputs with the given suffix                                   |


### Kinematics and kinetics - Temporal plot

```bash
pycgm2.exe NEXUS Plots Kinematics Temporal -ps test
pycgm2.exe NEXUS Plots Kinetics Temporal -ps test
```

=> build panel from model ouputs  suffixed *test*

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--pointSuffix`  | `-ps`       | `str`    | consider  model outputs with the given suffix                                   |

### Kinematics and kinetics - Time-normalized  and  Comparison Panels

Time-normalized and Comparison panels share similar arguments

type  `NEXUS Plots Kinematics Normalized -h` or  `NEXUS Plots Kinematics Comparison -h`  to know the input arguments ( idem with `Kinetics`) 


```bash
pycgm2.exe NEXUS Plots Kinematics Normalized --consistency -ps test -nd Schwartz2008 -ndm VerySlow
pycgm2.exe NEXUS Plots Kinematics Comparison --consistency -ps test -nd Schwartz2008 -ndm VerySlow
```
=> build kinematic panel from model ouputs suffixed *test*. the panel render all cycles rather the average and the std corridor. the panel also call the modality *Very slow* of the open normative dataset from *Schwartz2008* 

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--consistency`  | `-c`       |     | return consistency trace ( ie all cycles)                                   |
| `--pointSuffix`  | `-ps`       | `str`    | consider  model outputs with the given suffix                                   |
| `--normativeData`  | `-nd`       | `str`    | normative Data set (Schwartz2008 or Pinzone2014)                                |
| `--normativeDataModality`  | `-ndm`       | `str`    | if Schwartz2008 [VerySlow,Slow,Free,Fast,VeryFast] - if Pinzone2014 [CentreOne,CentreTwo]                                  |



### EMG - Temporal plots

type  `NEXUS Plots EMG Temporal -h`  to know the input arguments  

```bash
pycgm2.exe NEXUS Plots EMG Temporal --raw -bpf 200 400 
```
=> render non-rectified emg channels. The process applies a bandpass filter [200-400Hz] 

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--BandpassFrequencies`  | `-bpf`       |     | bandpass frequencies  |
| `--EnvelopLowpassFrequency`  | `-elf`       |     | envelop lowpass cutoff frequency  |
| `--raw`  | `-r`       |     | return non-rectified values  |
| `--ignoreNormalActivity`  | `-ina`       |     | do not display normal activity area in the back ground  |


### EMG - Time-normalized and Comparison Panels

type  `NEXUS Plots EMG Normalized -h` or  `NEXUS Plots EMG Comparison -h`  to know the input arguments  

```bash
pycgm2.exe NEXUS Plots EMG Normalized --consistency -bpf 200 400 -elp 8.9
```
=> render all cycles instead of the average and the std corridor. the process applies a bandpass filter [200-400Hz] and construct the emg envelop with a cut-off frequency of 8.9 

| long options     | short options      | Type     | Description                                                    |
|---------|------------------|--------------------| -------- | -------------------------------------------------------------- |
| `--BandpassFrequencies`  | `-bpf`       |     | bandpass frequencies  |
| `--EnvelopLowpassFrequency`  | `-elf`       |     | envelop lowpass cutoff frequency  |
| `--consistency`  | `-c`       |     | return consistency traces ( ie all cycles)  |

