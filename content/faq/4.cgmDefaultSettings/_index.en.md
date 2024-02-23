---
title: "Change default CGM settings temporarly or permanantly"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 4
---

{{< notice "info" >}}
Before running any commands presented below, be sure your virtual python environment is activated. Type `activate pycgm39`
{{< /notice >}}

Default CGM settings are configured in the folder: *CONDA_PATH/envs/ENV_NAME/Lib/site-packages/pyCGM2/Settings*


Instead of to call the input arguments of the CGM commands, like, e.g for the CGM2.3

```bash
pycgm2.exe NEXUS CGM2.3 Calibration
pycgm2.exe NEXUS CGM2.3 Fitting
```
an alternative is to place a the default `CGM2_3-pyCGM2.settings` settings file into the data folder. 


you can do it : 

Do it manually or through a command : 

 * open a miniconda prompt
 * change your current directory to target the data folder
 * run the command 

 ```bash
pycgm2.exe SETTINGS Edit -m CGM2.3
or
pycgm2.exe SETTINGS Edit --model CGM2.3
```
The command will place the `CGM2_3-pyCGM2.settings` file into your data folder so you can amend it. 

For instance, you can disable the flat foot options in the calibration section

```yaml
Calibration:
    HJC:
        Left: Hara #[string](choice: Hara only)
        Right: Hara
    Left flat foot: 0 #[integer](choice: 0 or 1)
    Right flat foot: 0
    Head flat : 0
```

{{< notice "warning" >}}
  You can also **permanantly** alter the default CGM settings. 
  </br>
  Find and ammend the `CGM2_3-pyCGM2.settings` 
{{< /notice >}} 




