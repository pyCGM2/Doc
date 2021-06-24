---
title: "Work with emg "
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 4
---


This tutorial is short. Currently, only the kinematic-based event detector stated by Zeni et al, was implemented

{{< notice "info" >}}
  Contributions are welcome
{{< /notice >}}



### plot rectify emg

The code shows how you can create plot panel reporting temporal traces of the emg.

`trialNames` is the list made up with c3d files.  


`loadEmg` load emg settings.

{{< notice "tip" >}}
By default, this function looks for a file named 'emg.settings' in your data folder.
if not found, it loads the content of the 'emg.settings' located in `pyCGM2.Settings`
{{< /notice >}}


Then, the code applies basic emg processing (bandpass and lowpass filters) and eventually plot temporal traces

```python
import pyCGM2
from pyCGM2.Lib import plot
from pyCGM2.Lib import emg


DATA_PATH = "C:\\myPATH\\"

trialNames = ["03367_05136_20200604-GBNNN-VDEF-01.c3d"]

emgManager = emg.loadEmg(DATA_PATH)

emg.processEMG(DATA_PATH, trialNames, emgManager.getChannels(),
    highPassFrequencies=[20,200],
    envelopFrequency=6.0)

plot.plotTemporalEMG(DATA_PATH, trialNames[0],
        rectify = True)


```

### plot time-normalized emg envelops

Instead of plotting temporal EMG traces, we report the emg envelops normalized on gait event.
For that, we need to construct an `analysis Instance` from the different trials.

here, the function `plotDescriptiveEnvelopEMGpanel` returns the mean traces and the standard deviation corridor.


{{< notice "tip" >}}
  if you want to visualize all cycles. you need to call the function `plotConsistencyEnvelopEMGpanel`
{{< /notice >}}








```python
import pyCGM2
from pyCGM2.Lib import plot
from pyCGM2.Lib import emg
from pyCGM2.Lib import analysis

DATA_PATH = "C:\\myPATH\\"

trialNames = ["03367_05136_20200604-GBNNN-VDEF-01.c3d", "03367_05136_20200604-GBNNN-VDEF-02.c3d"]

emgManager = emg.loadEmg(DATA_PATH)

emg.processEMG(DATA_PATH, trialNames, emgManager.getChannels(),
    highPassFrequencies=[20,200],
    envelopFrequency=6.0)

analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    trialNames,
                    emgChannels = emgManager.getChannels()                )

plot.plotDescriptiveEnvelopEMGpanel(DATA_PATH,analysisInstance)



```
