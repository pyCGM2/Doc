---
title: "Install pyCGM2 alternative"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 3
---

{{< notice "info" >}}
  pyCGM2 is implemented for **python 3.7 to python 3.11**. installation was tested for **Microsoft Windows 10**.
{{< /notice >}}

<center>
<figure>
{{< mermaid align="left" theme="neutral" >}}
flowchart LR
    A[download the source code] --> B[Install PYCGM2] -->|nexus User| C(install Nexus API)
{{< /mermaid >}}
<figcaption>installation flowchart</figcaption>
</figure>
</center>

In comparison with the previous installation guidelines, the guidelines below explains how you can install pyCGM2 from a local folder containing the source code. 

### stage 1 : download the source code

First, you need to download the pyCGM2 source code on your laptop. you have 2 options

 * download  [pyCGM2 4.3rc2]( https://github.com/pyCGM2/pyCGM2/releases/tag/4.3-rc2) , then unzipping it 
or
 * clone the github [master branch](https://github.com/pyCGM2/pyCGM2) with your subversion software (github desktop, sourceTree, ...)

### stage 2 : create a virtual environment and install pyCGM2 from your local folder

 * open the **anaconda prompt (miniconda)**
 * type the commands

```bash
cd C:/PATH/TO/YOUR/LOCAL/PYCGM2/FOLDER
conda env create -f environment_39.yml
conda activate activate pycgm39
pip install .
```
*developper* : use replace the last command by 
```bash
pip install -e .
```

**Explanations**

 * `cd C:/PATH/TO/YOUR/LOCAL/PYCGM2/FOLDER`
  Explanation: This command is used to navigate to a specific directory (or folder) on your computer. In this case, you're being directed to go to the location where you've saved or downloaded the PYCGM2 project. The C:/PATH/TO/YOUR/LOCAL/PYCGM2/FOLDER is a placeholder, and you should replace it with the actual path to the folder on your computer.

  * `conda env create -f environment_39.yml`
  This command is used to create a new environment using the Conda package manager. An environment is like an isolated workspace for Python projects, ensuring that the dependencies of one project don't interfere with another. The -f flag indicates that the environment should be created based on a file, in this case, environment_39.yml. This file contains a list of all the packages and specific versions that are needed for the PYCGM2 project.

  <div class="container">
    <div class="alert alert-info" role="alert">
      Note `environment_37.yml`, `environment_38.yml` of `environment_310.yml` generates Python 3.7 (resp. 3.8 and 3.10) virtual environments named pycgm37 (resp. pycgm38, pycgm310)
    </div>
  </div>


 * `conda activate activate pycgm39`
  This command is used to activate (or switch to) the specific conda environment, named pycgm39, constructed from previous command..

  * `pip install .`
  This command is used to install a Python package through the pip tool. The . (dot) at the end of the command indicates that pip should install the package located in the current directory (which should be the PYCGM2 project, based on the first command). This means you're installing the PYCGM2 project as a package on your computer.

  * `pip install -e .`
  This command is used to install a Python package through pip in "editable" mode. The -e flag indicates that the package should be installed in a way that any changes made to its source code will immediately affect the installed version. The . (dot) signifies that the package to be installed is located in the current directory. This is especially useful for developers who want to test changes to a package without repeatedly reinstalling it


### stage 3 : For vicon user -  install the Nexus API

if you are a **Vicon Nexus Users**, type the command below to interfere with Vicon Nexus

```bash
cd C:\Program Files\Vicon\Nexus2.15\SDK\Win64\Python\viconnexusapi
pip install .
cd C:\Program Files\Vicon\Nexus2.15\SDK\Win64\Python\viconnexusutils
pip install .
```
you can also use `pip install -e .`



