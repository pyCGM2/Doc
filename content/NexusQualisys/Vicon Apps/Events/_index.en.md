---
title: "Events"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---


{{< notice "info" >}}
Before running any commands, be sure your virtual python environment is activated. Type `activate pycgm39`
{{< /notice >}}

## Gait event methods

### Zeni et al 2008 - gait event detection 


{{< notice "note" >}}
  Zeni's algorithm is kinematic-based methdo. It requires pelvic markers ( LPSI-RPSI) and foot markers (LHEE, LTOE and  RHEE, RTOE repectively) for detecting foot contacts </br>
  Zeni, J.A., Richards, J.G., Higginson, J.S., 2008. Two simple methods for determining gait events during treadmill and overground walking using kinematic data 27, 710–714. https://doi.org/10.1016/j.gaitpost.2007.07.007
{{< /notice >}}


Load the gait Trial, then run the command

  ```bash
  pyCGM2.exe NEXUS Events Zeni
  ```

Add ` -h ` to know their input arguments or or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#Zeni) 


