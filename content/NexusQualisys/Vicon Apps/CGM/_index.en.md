---
title: "CGM"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 1
---


The use of the CGM in nexus is a **two-step process**. First your need to **calibrate** your static file, then, for your gait trials, you need to **fit** a CGM. 

We thus introduce two operations:

 * Calibration
 * Fitting

{{< notice "info" >}}
For the experienced-Vicon Plugin gait user, Calibration and Fitting are similar to the operations *Process static Plugin gait calibration* and *process dynamic Plugin gait model*
{{< /notice >}}


please refer to the [CGM pages]({{< ref "CGM" >}}) to know the model details


Except the CGM2.6, CGM1.0 to CGM2.5 can be run with similar commands, detailed below. 


## Preliminary

* run Vicon nexus
* open  *miniconda prompt*
* activate your pycgm2 virtual environment (type  `activate pycgm39`)


## Calibration

Once your static file loaded in nexus. 

* type `pycgm2.exe NEXUS CGM1.0 Calibration` in the  *miniconda console*

{{< notice "info" >}}
you can replace `CGM1.0` with `CGM1.1`, `CGM2.1`, `CGM2.2`, `CGM2.3`, `CGM2.4` or `CGM2.5` 
{{< /notice >}}


{{< notice "warning" >}}
Notice the Calibration process, do not accept gap. Please crop or fill gaps of your trial
{{< /notice >}}

**By default**, the calibration of all CGM :
 * align the longitudinal foot axis with the ground. It's the *flat foot option*, familiar to vicon PiG user, which repositions the heel marker at the same height as the toe marker.   
 * align the medio-lateral axis of the head (head flat option)
 * consider 14mm marker diameter.   

There are different ways to alter these default settings: 
 * add input arguments to the command.  Type  `pycgm2.exe NEXUS CGM1.0 Calibration -h` to know the input arguments. Refer to the [argument reference]({{< ref "argumentReferences" >}}) page for details 
 * manipulate the setting files. see [how to]({{< ref "howto" >}})      



## Fitting

For each  gait trial loaded in nexus. 

* type `pycgm2.exe NEXUS CGM1.0 Fitting` in the  *miniconda console*

{{< notice "info" >}}
you can replace `CGM1.0` with `CGM1.1`, `CGM2.1`, `CGM2.2`, `CGM2.3`, `CGM2.4` or `CGM2.5` 
{{< /notice >}}

**By default** 
 *  like the Vicon Pig, the CGM1 projects joint moment into the distal segment
 *  with CGM1.1 to 2.5 : joint moments are projected into the joint coordinate system

There are different ways to alter these default settings: 
 * add input arguments to the command.  Type  `pycgm2.exe NEXUS CGM1.0 Fitting -h` to know the input arguments. Refer to the [argument reference]({{< ref "argumentReferences" >}}) page for details 
 * manipulate the setting files. see [how to]({{< ref "howto" >}})      



## CGM2.6 

The CGM2.6 introduces two methods for calibrating the knee , i.e. the **SARA** and the **calibration2Dof** functional methods ( see [CGM2.6 section]({{< ref "CGM/CGM2.6" >}})

If you want to run the CGM2.6. The process is: 

* calibrate your trial with the CGM2.5 `pycgm2.exe NEXUS CGM2.5 Calibration`
* load your left knee flexion extension trial into Nexus
* run the command `pycgm2.exe NEXUS CGM2.6 SARA`  or `pycgm2.exe NEXUS CGM2.6 2DOF`
* repeat for the right side
* fit your gait trial `pycgm2.exe NEXUS CGM2.5 Fitting` 

Type  `pycgm2.exe NEXUS CGM2.6 2DOF -h` or `pycgm2.exe NEXUS CGM2.6 SARA -h` to know the input arguments. . Refer to the [argument reference]({{< ref "argumentReferences" >}}) page for details. 


