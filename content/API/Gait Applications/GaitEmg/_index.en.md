---
title: "Work with emg "
#date: 2018-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description:
# type dont remove or customize
type :
weight: 4
---

Before running following code, the analyst must define the emg configuration of his data collection.
As default, pyCGM2 considers the content of the file `emg.settings`, located in the folder `pyCGM2/Settings`.

Here is a part of `emg.settings`
```
CHANNELS:
    Voltage.EMG1 :
        Muscle : RECFEM
        Context : Left
        NormalActivity : RECFEM

    Voltage.EMG2 :
        Muscle : RECFEM
        Context : Right
        NormalActivity : RECFEM
    ...
    Voltage.EMG16 :
        Muscle :
        Context :
        NormalActivity :

```

 - 16 channels are predefined.
 - Channels are named `Voltage.EMG1` to `Voltage.EMG16` and matched with analog label of your c3d.
 - for each channel, the label of the muscle (`muscle`) is given as well as its side location (`Context`)
 - the item `NormalActivity` is the muscle label used for displaying the instant of normal activity in the background of the plot.
 Unlike, the `muscle` item, user must select a `NormalActivity` label in the list:

```
ADDBRE , ADDLON, ADDMAG, BICFEM, CALF, EXTDIGLON, EXTHALLON, FLEDIGLON, FLEHALLON,
GASTRO, GLUMAX, GLUMED, GLUMIN, GRACIL, HAMSTR, HIPABD, HIPADD, HIPEXT, HIPFLE,
ILIACU, ILIOPS, LATHAM, LATQUA, MEDHAM, MEDQUA, PERBRE, PERLON, POPLIT, RECFEM,
SARTOR, SEMIME, SEMITE, SOLEUS, TENFACLAT, TIBANT, TIBPOS, VASINT, VASLAT,
VASMEDLON, VASMEDOBL
```

{{< notice "info" >}}
  Alter the `emg.settings` located in the folder `pyCGM2/Settings` if you want to configure your emg routine.
{{< /notice >}}

{{< notice "tip" >}}
  Exceptionally, if your gait data collection does not match with your routine, you can copy/paste
  the `emg.settings` in the data folder, then edit it.
{{< /notice >}}

### plot rectify emg

The code shows how you can create plot panel reporting temporal traces of the emg.


```python
import pyCGM2
from pyCGM2.Lib import plot
from pyCGM2.Lib import emg

# data
DATA_PATH = "C:\\myPATH\\"
trialNames = ["03367_05136_20200604-GBNNN-VDEF-01.c3d"]

# load emg manager
emgManager = emg.loadEmg(DATA_PATH)

# process emg channels
emg.processEMG(DATA_PATH, trialNames, emgManager.getChannels(),
    highPassFrequencies=[20,200],
    envelopFrequency=6.0)

# plot
plot.plotTemporalEMG(DATA_PATH, trialNames[0],
        rectify = True)
```



### plot time-normalized emg envelops

Instead of plotting temporal EMG traces, we show how to report the emg envelops normalized on gait event.
This requires the construction of an `analysis Instance`.


```python
import pyCGM2
from pyCGM2.Lib import plot
from pyCGM2.Lib import emg
from pyCGM2.Lib import analysis

# data
DATA_PATH = "C:\\myPATH\\"
trialNames = ["03367_05136_20200604-GBNNN-VDEF-01.c3d", "03367_05136_20200604-GBNNN-VDEF-02.c3d"]

# emg manager
emgManager = emg.loadEmg(DATA_PATH)

# process emg analog channels
emg.processEMG(DATA_PATH, trialNames, emgManager.getChannels(),
    highPassFrequencies=[20,200],
    envelopFrequency=6.0)

# construct the analysis instance
analysisInstance = analysis.makeAnalysis(DATA_PATH,
                    trialNames,
                    emgChannels = emgManager.getChannels()                )

# plot descriptive and consistancy plot panels
plot.plotDescriptiveEnvelopEMGpanel(DATA_PATH,analysisInstance)
plot.plotConsistencyEnvelopEMGpanel(DATA_PATH,analysisInstance)
```
