---
title: "Changelog"
description: ""
draft: false
---

{{< notice "info" >}}
Please use the issue tracker of github to post your issue </br>
We value your feedback : Submit your suggestions for improvements
{{< /notice >}}


###  BETA pyCGM2 4.2.0 - [june, 2021]

{{< changelog "Added" >}}
  * documentation API generator.  Google style doctrings are parsed and rendered as markdown.
  * new folder *examples**  with basic scripts.
{{</ changelog >}}

{{< changelog "Changed" >}}

  * installation  do not copy  settings into the folder *c:/programData/pycgm2/*. Default settings are called from the *settings* folder of your installed pyCGM2 package     
  * better management of the settings file (emg.settings and CGMi-pycgm2.settings).  `Utils.files.loadModelSettings` looks for a cgm settings file in your data folder if not found. it loads the default cgm settings.  
  *  emg processing functions improved. better management of the emg.settings through a  new class `EMG.EmgManager`  

 {{</ changelog >}}

{{< changelog "Fixed" >}}
  * wrong settings  are called if you have several virtual environment
{{</ changelog >}}

###  pyCGM2 4.1.0 - Phantoms- [april, 2021]



{{< changelog "Added" >}}
 * **Management of  missing markers**. The code no longer detects body part (i.e lower body, Upper body or Lower body + thorax). This new feature allows to process data with markers placed over the left or right leg only

* **Anomaly detectors**.  CGM operations integrate anomaly detectors.  Implemented anomaly detectors check :
     * marker trajectory
     * anthropometric data
     * saturation of force plate
     * gait events

* **new QTM workflows** : CGM2.5 and CGM2.6 implemented
{{</ changelog >}}


{{< changelog "Changed" >}}
  * The *fitting* operation.  The user can specify frames of interest (first and last frame) from script argument. If not specified, the fitting operation automatically detect frames of interest based on tracking makers presence.     
  * Clarification of the log message.
  * the *chord* function was reimplemented from scratch ( former implementation was time consuming)
{{</ changelog >}}

{{< changelog "Fixed" >}}
None
{{</ changelog >}}




**march, 2021**

{{< changelog "changed" >}}
* hugo as static web site generator  
{{</ changelog >}}

<hr>






<!-- ### Changelog label

{{< changelog "Added" >}}
{{</ changelog >}}

{{< changelog "Changed" >}}
{{</ changelog >}}

{{< changelog "Depricated" >}}
{{</ changelog >}}

{{< changelog "Removed" >}}
{{</ changelog >}}

{{< changelog "Fixed" >}}
{{</ changelog >}}

{{< changelog "Security" >}}
{{</ changelog >}}

{{< changelog "Unreleased" >}}
{{</ changelog >}} -->
