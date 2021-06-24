---
title: "Detect gait events "
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 3
---


This tutorial is short. Currently, only the kinematic-based event detector stated by Zeni et al, was implemented

{{< notice "info" >}}
  Contributions are welcome
{{< /notice >}}


You just need to load a `BtkAcquisition` from your gait trial. then, run the function `Zeni` from the file `eventDetector` of  the module `Lib`


```python
import pyCGM2
from pyCGM2.Lib import eventDetector
from pyCGM2.Tools import btkTools

DATA_PATH = "C:\\myPATH\\"

trialName = "03367_05136_20200604-GBNNN-VDEF-01.c3d"
acqGait = btkTools.smartReader(DATA_PATH+trialName)
eventDetector.zeni(acqGait)
btkTools.smartWriter(acqGait, DATA_PATH+trialName[:-4]+"-event.c3d")

```
