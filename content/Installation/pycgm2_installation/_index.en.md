---
title: "Install pyCGM2"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 2
---


The easiest option to install pyCGM2 is to pull the [pyCGM2 conda package](https://anaconda.org/pyCGM2/pycgm2)

Beforehand, we recommand to create a virtual python environment to isolate your pycgm2 project from other projects and applications on your system.

* open the **anaconda prompt (miniconda)**
* type `conda create --name pycgm39 python=3.9`. 
* type `activate pycgm39` to activate your environment

Then, pull the pycgm2 conda package with the command   

* `conda install -c pycgm2 pycgm2` 

The last command install the latests pycgm2 version (ie version 4.3.0) an all its dependancies in your PC. 

{{< notice "info" >}}
  Instead of python 3.9, you can use the same commands for python 3.7 and 3.8
{{< /notice >}}

## Alternative installation


If you encounter any problems with the conda package or are a developer who wants to work on pyCGM2 API, there is an alternative installation method that you can use 


First, you need to download the pyCGM2 source code on your laptop. you have different options

 * download  [pyCGM2 4.3rc2]( https://github.com/pyCGM2/pyCGM2/releases/tag/4.3-rc2) , then unzipping it 
or
 * clone the github [master branch](https://github.com/pyCGM2/pyCGM2) with your subversion software (github desktop, sourceTree, ...)

then : 

 * open the **anaconda prompt (miniconda)**
 * navigate  to the local pycgm2 folder with the command  `cd C:/PATH/TO/PYCGM2/`
 * type : `conda env create -f environment_39.yml`. This command creates a  python 3.9 virtual environment named `pycgm39` with all pyCGM2 dependancies. 

<div class="container">
  <div class="alert alert-info" role="alert">
    Note `environment_37.yml` or `environment_38.yml` generates Python 3.7 (resp. 3.8) virtual environments named pycgm37 (resp. pycgm38)
  </div>
</div>

 * type `activate pycgm39` 

if you are a developper or want to keep up-to-date with any modifications of the source code 
 * type `pip install -e .` ( do not forget the dot). 
  This command will create a symbolic link in the site-packages folder that points to your local pyCGM2 folder.   

Alternatively, if you only want to install pyCGM2 and not modify the source code

 * type `pip install .` ( do not forget the dot). 
  This command will install pyCGM2 into the *site-package* folder of your virtual python environement ( i.e. *C:\Users\fleboeuf\Miniconda3\envs\pycgm39\Lib\site-packages*). Once the installation is complete, you can safely remove the downloaded pyCGM2 folder.


