---
title: pyCGM2.Lib.eventDetector
---

# <kbd>module</kbd> `pyCGM2.Lib.eventDetector`





---

## <kbd>function</kbd> `zeni`

```python
zeni(acqGait, footStrikeOffset=0, footOffOffset=0, **kwargs)
```

kinematic-based event detector according Zeni et al(2008). 

This method need the presence of the markers "LPSI","RPSI","LHEE","LTOE","RHEE","RTOE" 



*Reference:* Zeni, J. A.; Richards, J. G.; Higginson, J. S. (2008) Two simple methods for determining gait events during treadmill and overground walking using kinematic data. In : Gait & posture, vol. 27, n° 4, p. 710–714. DOI: 10.1016/j.gaitpost.2007.07.007. 



**Args:**
 
 - <b>`acqGait`</b> (btkAcq):  acquisition instance. 

Keyword Args: 
 - <b>`footStrikeOffset (int)[0]`</b>:  systematic offset to add to all `footStrikeOffset` events. 
 - <b>`footOffOffset (int)[0]`</b>:  systematic offset to add to all `footOffOffset` events. 

Keyword Args (low-level): 
 - <b>`fc_lowPass_marker (double) `</b>:  cut-off frequency of the lowpass filter applied on markers 
 - <b>`order_lowPass_marker`</b> (int):  order of the lowpass filter applied on markers 



**Returns:**
 
 - <b>`btkAcq`</b>:  updated acquisition with detected events. 
 - <b>`bool `</b>:  state of the detector 



