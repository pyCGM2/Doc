---
title: "Install pyCGM2"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---

{{< notice "info" >}}
  pyCGM2 is implemented for **python 3.7 to python 3.11**. installation was tested for **Microsoft Windows 10**.
{{< /notice >}}

<center>
<figure>
{{< mermaid align="left" theme="neutral" >}}
flowchart LR
    A[Install PYCGM2] -->|nexus User| B(install Nexus API)
{{< /mermaid >}}
<figcaption>installation flowchart</figcaption>
</figure>
</center>

### stage 1 :  install pyCGM2


Launch the **anaconda prompt (miniconda)**, then, for python 3.9, type the commands :

```bash
conda create --name pycgm39 python=3.9
conda activate pycgm39
conda install -c pycgm2 pycgm2
```
If you're using a different version of Python (e.g., 3.10), adjust the commands accordingly. For instance, replace python=3.9 with python=3.10 and update the virtual environment name to pycgm310.

**explanations** The first two commands create and enable the python 3.9 virtual environment named `pycgm39`
and the last command install pyCGM2 from its [conda channel](https://anaconda.org/pyCGM2) 

{{< notice "info" >}}
If either you simply want to access the pyCGM2 executables, or you are not a python developper, you can skip the creation and activation of the virtual environement. Just ensure you have an Anaconda versions 3.7 to 3.11 installed on your system and run the last command
{{< /notice >}}


### stage 2 : For vicon user -  install the Nexus API

If you are a **Vicon Nexus User**, type the command below to enable interaction with Vicon Nexus

```bash
cd C:\Program Files\Vicon\Nexus2.15\SDK\Win64\Python
install_vicon_nexus_api.bat
install_vicon_nexus_utils.bat
```
*note:* 
 
 * this commands may require to be run in **administrator mode**
 * installer only tested for nexus 2.15


