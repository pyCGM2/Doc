---
title: " Modify the default EMG configuration"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 5
---


{{< notice "info" >}}
Before running any commands, be sure your virtual python environment is activated. Type `activate pycgm39`
{{< /notice >}}


Default EMG settings are configured in the file: *CONDA_PATH/envs/ENV_NAME/Lib/site-packages/pyCGM2/Settings/emg.settings*

We predefined the location of 16 emg devices as follow

| EMG channel   | Muscle            | Side    |
|:-------------:|:-----------------:|:-------:|
| EMG1          | rectus femoris    | Left    |
| EMG2          | rectus femoris    | Right   |
| EMG3          | vastus lateralis  | Left    |
| EMG4          | vastus lateralis  | Right   |
| EMG5          | semitendinosus    | Left    |
| EMG6          | semitendinosus    | Right   |
| EMG7          | tibialis anterior | Left    |
| EMG8          | tibialis anterior | Right   |
| EMG9          | soleus            | Left    |
| EMG10         | soleus            | Right   |
| EMG11         | None              | None    |
| EMG12         | None              | None    |
| EMG13         | None              | None    |
| EMG14         | None              | None    |
| EMG15         | None              | None    |
| EMG16         | None              | None    |  

If your session does not match with this configuration, you can place the  `emg.settings` file into your data folder, then amend it.

Do it manually or through the command
 * open a miniconda prompt
 * change your current directory to target the data folder
 * run the command `pycgm2.exe SETTINGS Edit -e ` or `pycgm2.exe SETTINGS Edit --emg `


For instance, if your emg 1 and 2 are placed on the gluteus medius rather than the rectus femoris, open the `emg.settings` and edit the section

```yaml
CHANNELS:
    Voltage.EMG1 :
        Muscle : GLUMED 
        Context : Left 
        NormalActivity : GLUMED 

    Voltage.EMG2 :
        Muscle : GLUMED
        Context : Right
        NormalActivity : GLUMED
```


{{< notice "warning" >}}
  You can also **permanantly** alter the emg settings. 
  </br>
  Find and ammend the `emg.settings` file
{{< /notice >}} 



