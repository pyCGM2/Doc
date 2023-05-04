---
title: "Vicon and QTM Apps"
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: "call pyCGM2 apps from your mocap software  "
# type dont remove or customize
type : "docs"
weight: 4
---


<p class="text-danger">This website only covers the use of the <b>release candidate pyCGM2 4.3-rc1</b>. This release has not been internally tested  by Vicon and Qualisys developers yet</p>


{{< notice "info" >}}
We also remind this website only cover the external use of pyCGM2 (i.e from command line, not from user inteface) 
</br>
Please refer to the official manuals if you use a Nexus-integrated or QTM-integrated version.  
{{< /notice >}}


**pyCGM2 Version 4.3.0** heavily improves its interactions with Nexus or QTM.

The user interacts with pyCGM2 and Nexus/QTM from a single and more explicit command `pyCGM2.exe`. 

{{< notice "tip" >}}
  type `pyCGM2.exe -h` if you want to explore the content of `pyCGM2.exe`
{{< /notice >}}

## Quickstart

### Vicon users

Check out this video, you will see how to calibrate your static trial, then fit a gait trial with the CGM1.0, and eventually plot the time-normalized kinematics.  

{{< youtube tOKeB5vLhe4 >}}

Here are the subsequent steps described in the video :

  * load your static file into nexus
  * open anaconda prompt console 
  * (optional) activate your python environment  `activate pycgm39` ( here i activate the python 3.9 version of pycgm2)
  * Go to your data folder in the console with the current directory command `cd` 
  * type :  `pyCGM2.exe NEXUS CGM1.0 Calibration` to calibrate your static
  * load your gait trial into nexus
  * run :  `pyCGM2.exe NEXUS CGM1.0 Fitting` to fit your gait trial
  * if you already identified gait event, type :  `pyCGM2.exe NEXUS Plots Kinematics Normalized` to plot the time-normalized kinematics


The section  [Vicon apps]({{< relref "Vicon Apps" >}})  presents the different scripts callable from the command `pyCGM2.exe NEXUS`


### QTM users

Check out this video to see how to run the CGM2.1 QTM workflow 


{{< youtube b0v1RopkNB4 >}}


Here are the subsequent steps described in the video :
  * open Qtm and load your project
  * generate the   `session.xml` file, 
  * open anaconda prompt console 
  * (optional) activate your python environment  `activate pycgm39` ( here i activate the python 3.9 version of pycgm2)
  * Go to your data folder in the console with the current directory command `cd` 
  * run `pyCGM2.exe QTM CGM2.1`
  

The section  [Vicon apps]({{< relref "Qtm Apps" >}})  presents the different scripts callable from the command `pyCGM2.exe QTM`







  




