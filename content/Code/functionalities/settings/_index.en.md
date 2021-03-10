---
title: "The settings folder"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---


The **Settings** folder located in the *C:\\programData\\pycgm2* initiated pyCGM2 scripts. For instance the file `CGM1-pyCGM2.settings` gathers default options of the CGM1,

![cgm1s](CGM1settings.PNG)

{{< notice "info" >}}
**These *-pyCGM2.settings* are representative of your routine**. As you can see in the  above illustration, the flat foot options are enable ( the longitudinal axis of the foot is set parallel to the ground), the joint moments are projected into the Distal segment (ie default option of the Vicon Plugin gait) .
{{< /notice >}}



### What to do if your gait analysis does not match the predefined settings   

For instance, if your patient has a left equinus foot in static pose, you cannot apply the default settings. You need to disable the left flat foot option.

There are two options :

1. copy paste the *#model#-pyCGM2.settings* into the patient data folder. Then amend the copied file.
2. use the input arguments of the python script
