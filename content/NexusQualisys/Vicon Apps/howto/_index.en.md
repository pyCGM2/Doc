---
title: "How to"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 6
---

## 1. Change default CGM settings temporarly

Both *calibration* and *fitting* commands (e.g `pycgm2.exe NEXUS CGM1.0 Calibration` and ( resp `pycgm2.exe NEXUS CGM1.0 Fitting`))) 
called default settings, you can alter with   [input arguments]({{< relref "../argumentReferences" >}})

An alternative to input arguments is to place a CGM settings file (e.g [`CGM2_3-pyCGM2.settings` for the CGM2.3) in the data folder. we dedicated a commmand to do that. 

 * open a miniconda prompt
 * activate your python virtual environment `activate pycgm39`
 * change your current dicectory to target the data folder
 * run the command `pyCGM2.exe GLOBAL LocalSettings -m CGM2.3` or `pyCGM2.exe GLOBAL LocalSettings --model CGM2.3` fro the CGM2.3

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

The local CGM setting file, rather the default settings, will be loaded each time you run the *calibration* and *fitting* CGM commands 


{{< notice "warning" >}}
  You can also **permanantly** alter the CGM settings. 
  </br>
  Find and ammend the `CGM2_3-pyCGM2.settings` or another one, located in the folder *Settings** of your pyCGM2 folder( *C:/Users/username/Miniconda3/envs/yourVirtualEnvironment/Lib/site-packages/pyCGM2*) 
{{< /notice >}} 


## 2. Modify the default EMG configuration

We predefined the position of 16 emg devices as follow

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

If your session does not match with this configuration, you can place the  `emg.settings` file into your data folder, then amend it

 * open a miniconda prompt
 * activate your python virtual environment `activate pycgm39`
 * change your current dicectory to target the data folder
 * run the command `pyCGM2.exe GLOBAL LocalSettings -e ` or `pyCGM2.exe GLOBAL LocalSettings --emg `


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
  Find and ammend the `emg.settings` file , located in the folder *Settings** of your pyCGM2 folder( *C:/Users/username/Miniconda3/envs/yourVirtualEnvironment/Lib/site-packages/pyCGM2*) and edit it 
{{< /notice >}} 


## 3. Integrate an pyCGM2 command as operation of a nexus pipeline

{{< notice "note" >}}
  As you could see below, all commands  were configured to work with the virtual python 3.9 environnent, named `pycgm39`
{{< /notice >}}

To integrate a pyCGM2 operation into a Vicon nexus pipeline, you need to insert a *run python operation* into your pipeline and configure it as follow :

![nexusOp](Nexus_pipelineOpSettings.png)


 * **the python script file** must target :  `yourMinicondapath/Miniconda3/envs/pycgm39/Scripts/pyCGM2-script.py`
 * place the input arguments in the **script arguments** text box. 
 In this example, we want to calibrate our static trial with the CGM1.0
 * In **Environment activation**, you need to place the bat file that activate your virtual python environment -( here `pycgm39`).
   * create a new file named `environementActivation.bat` and edit it with a text editor (notepad)
   * place into the file, the following content   
    ```bash
    @echo off
    
    rem Set the path to your Miniconda installation directory
    set "CONDA_PATH=C:\Users\fleboeuf\Miniconda3"
    
    rem Set the name of your virtual environment
    set "ENV_NAME=pycgm39"
    
    call "%CONDA_PATH%\Scripts\activate.bat" %ENV_NAME%
    ```
    * edit `CONDA_PATH` to the folder containg the command `conda.exe` and et the appropriate virtual environment name `ENV_NAME`
    * save your file. 

{{< notice "tip" >}} 
  For those who instal pyCGM2 from local source, you can find a preconfigured file `environementActivation.bat`
  in the folder `pyCGM2\Apps\ViconApps` 
{{< /notice >}}

