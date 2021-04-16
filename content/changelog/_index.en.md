---
title: "Changelog posts"
description: ""
draft: false
---

{{< notice "info" >}}
Please use the issue tracker of github to post your issue </br>
We value your feedback : Submit your suggestions for improvements
{{< /notice >}}



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
