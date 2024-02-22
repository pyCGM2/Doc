---
title: "CGM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 1
---

{{< notice "info" >}}
Before running any commands, be sure your virtual python environment is activated. Type `activate pycgm39`
{{< /notice >}}



The use of the CGM in nexus is a **two-step process**. First your need to **calibrate** your static file, then, for your gait trials, you need to **fit** a CGM. 

We thus introduce two operations:

 * Calibration
 * Fitting

{{< notice "info" >}}
For the experienced-Vicon Plugin gait user, Calibration and Fitting are similar to the operations *Process static Plugin gait calibration* and *process dynamic Plugin gait model*
{{< /notice >}}


please refer to the [CGM pages]({{< ref "CGM" >}}) to know the model details


Except the CGM2.6, CGM1.0 to CGM2.5 can be run with similar commands, detailed below. 


## CGM1.0 to CGM2.5 commands



<center>
<figure>
{{< mermaid align="left" theme="neutral" >}}
flowchart LR
  subgraph Calibration
    id11[Load a static file into nexus]
    id12[call a pyCGM2 Calibration operation]
  end

  subgraph Fitting
    id21[Load a gait Trial into nexus]
    id22[call a pyCGM2 Fitting operation]
  end

  id11-->id12
  id21-->id22
  Calibration--->Fitting


{{< /mermaid >}}
</center>

### Calibration


{{< notice "warning" >}}
Notice the Calibration process, do not accept gap. Please crop or fill gaps of your trial
{{< /notice >}}

The callable **calibration** operations are : 

```bash 
pycgm2.exe NEXUS CGM1.0 Calibration
pycgm2.exe NEXUS CGM1.1 Calibration
pycgm2.exe NEXUS CGM2.1 Calibration
pycgm2.exe NEXUS CGM2.2 Calibration
pycgm2.exe NEXUS CGM2.3 Calibration
pycgm2.exe NEXUS CGM2.4 Calibration
pycgm2.exe NEXUS CGM2.5 Calibration
```  


<div class="alert alert-dismissible alert-warning">
  <strong> By default</strong>
  <ul>
  <li>align the longitudinal foot axis with the ground. It's the *flat foot option*, familiar to vicon PiG user, which repositions the heel marker at the same height as the toe marker. </li>
  <li>align the medio-lateral axis of the head (head flat option)</li>
  <li>consider 14mm marker diameter.   </li>
</ul> 
</div>


**To alter these default settings** 
 * use input arguments to the command.  To know the input arguments, type  `pycgm2.exe NEXUS CGM1.0 Calibration -h ` ( or any CGM#i) or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#CGM1.0)  
 * manipulate the setting files. see [how to]({{< ref "howto" >}})      



### Fitting

The callable **fitting**  operations are : 

```bash 
pycgm2.exe NEXUS CGM1.0 Fitting
pycgm2.exe NEXUS CGM1.1 Fitting
pycgm2.exe NEXUS CGM2.1 Fitting
pycgm2.exe NEXUS CGM2.2 Fitting
pycgm2.exe NEXUS CGM2.3 Fitting
pycgm2.exe NEXUS CGM2.4 Fitting
pycgm2.exe NEXUS CGM2.5 Fitting
``` 

{{< notice "info" >}}
you can replace `CGM1.0` with `CGM1.1`, `CGM2.1`, `CGM2.2`, `CGM2.3`, `CGM2.4` or `CGM2.5` 
{{< /notice >}}


<div class="alert alert-dismissible alert-warning">
  <strong> By default</strong>
  <ul>
  <li>like the Vicon Pig, the CGM1.0 projects joint moment into the distal segment </li>
  <li>with CGM1.1 to 2.5 : joint moments are projected into the joint coordinate system</li>
  </ul> 
</div>

**To alter these default settings** 
 * use input arguments to the command.  To know the input arguments, type  `pycgm2.exe NEXUS CGM1.0 Fitting -h ` (e.g for CGM1.0) 
   or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#CGM1.0) 
 * manipulate the setting files. see [how to]({{< ref "howto" >}})     


## CGM2.6 

{{< notice "warning" >}}
we recommand to collect a left and a right functional knee calibration trial separately.
{{< /notice >}}

The CGM2.6 incorporates a knee functional calibration into the CGM2.3 to CGM2.5 operations

<center>
<figure>
{{< mermaid align="left" theme="neutral" >}}
flowchart LR
  subgraph Calibration
    id11[Load a static file into nexus]
    id12[call a pyCGM2 Calibration operation]
  end

  subgraph KneeCalibration
    id21[Load a left knee functional calibration trial file into nexus]
    id22[call a CGM2.6 operation]
    id23[Load a right knee functional calibration trial file into nexus]
    id24[call a CGM2.6 operation]
  end

  subgraph Fitting
    id31[Load a gait Trial into nexus]
    id32[call a pyCGM2 Fitting operation]
  end

  id11-->id12
  Calibration--->KneeCalibration
  id21-->id22
  id22-->id23
  id23-->id24
  KneeCalibration--->Fitting
  id31-->id32

{{< /mermaid >}}
</center>


After calibrating a CGM2.3+ model, you can refine the knee joints from functional calibration trial with the one of the CGM2.6 operations


```bash
pycgm2.exe NEXUS CGM2.6 SARA
pycgm2.exe NEXUS CGM2.6 2DOF
```

*SARA* and *2DOF* refer to [Baker et al. 1999](http://dx.doi.org/10.1016/S0167-9457%2899%2900027-5) and [Ehrig et al, 2007](http://dx.doi.org/S0021-9290%2806%2900415-5) methods 


Add ` -h ` to know their input arguments or or refer to the [documentation API](https://pycgm2.github.io/pyCGM2/Apps/nexus.html#2DOF) 



