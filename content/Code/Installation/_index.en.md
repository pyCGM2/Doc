---
title: "pyCGM2 Installation"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---

### Install from source

{{< youtube 9faNjsTHVfs >}}

<hr>

* download the last pycgm2 release ( [version 4.0.2-beta](https://github.com/pyCGM2/pyCGM2/releases/tag/version(4.0.2)-beta))
* go to you local downloaded zip file and unzipped it ( place it wherever)
* open the *miniconda prompt*
* activate your virtual python environment with `activate pycgm3`
* go to your local unzipped folder ( folder with the file *setup.py*)
* type `python setup.py install`
* check import of pycgm2, type:
  * `python` to open a python
  * `import pyCGM2`


The installation  :

* generates **scripts** into the virtual environment ( here pycgm3) folder *PATHTO\\Miniconda3\\envs\\pycgm3\\Scripts*)
* creates a folder *C:\\programData\\pycgm2* and gathers in **settings**
* detects your Vicon Nexus version and populates *C:\\Users\\Public\\Documents\\Vicon\\Nexus2.x*
with pre-defined nexus pipelines and nexus skeleton (vst files)
