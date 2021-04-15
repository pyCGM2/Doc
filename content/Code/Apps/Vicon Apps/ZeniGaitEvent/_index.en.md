---
title: "Kinematic-Based Zeni's method"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 8
---

{{< notice "note" >}}
  Zeni's algorithm is kinematic-based methdo. It requires pelvic markers ( LPSI-RPSI) and foot markers (LHEE, LTOE and  RHEE, RTOE repectively) for detecting foot contacts </br>
  Zeni, J.A., Richards, J.G., Higginson, J.S., 2008. Two simple methods for determining gait events during treadmill and overground walking using kinematic data 27, 710–714. https://doi.org/10.1016/j.gaitpost.2007.07.007
{{< /notice >}}




* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm3`)


{{< youtube 1uIKHmQhnpI   >}}

As you can see, the procedure is :

* [Nexus] load your static file
* [miniconda Console] type `Nexus_zeniDetector.exe`
