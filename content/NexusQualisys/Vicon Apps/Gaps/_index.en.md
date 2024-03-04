---
title: "Gaps filling"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 3
---


{{< notice "info" >}}
Before running any commands, be sure your virtual python environment is activated . 
</br>
type `activate pycgm39`
{{< /notice >}}


## Kalman gap filling method

{{< notice "info" >}}
**Code contribution**, we thank Mickael Burke for sharing scripts.
{{< /notice >}}

Our script is an adaptation of the open-access code from [Burke and Lasenby 2016](https://www.sciencedirect.com/science/article/pii/S0021929016304766?via%3Dihub) (Burke and Lasenby 2016)   

Find out  the [theory]({{< ref "blog/KalmanGapTheory" >}}) of this approach in the next section


Load the gait trial, then run the command

  ```bash
  pyCGM2.exe NEXUS Gaps Kalman
  ```

Add ` -h ` to know their input arguments or or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#Kalman) 




## Gloersen gap filling method


This gait event detecto is an implementation [Gløersen et al, 2016](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0152616)

Gløersen, Øyvind; Federolf, Peter (2016) Predicting Missing Marker Trajectories in Human Motion Data Using Marker Intercorrelations. In : PloS one, vol. 11, n° 3, e0152616. DOI: 10.1371/journal.pone.0152616.


Load the gait trial, then run the command

  ```bash
  pyCGM2.exe NEXUS Gaps Gloersen
  ```

Add ` -h ` to know their input arguments or or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#Gloersen) 


