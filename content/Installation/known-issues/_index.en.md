---
title: "Known issues"
#date: 2021-12-28T11:02:05+06:00
icon: "ti-credit-card" # themify icon pack : https://themify.me/themify-icons
description: ""
# type dont remove or customize
weight: 4
---


{{< notice "warning" >}}
  If you face with any issues , please report it through the [github issue page](https://github.com/pyCGM2/pyCGM2/issues)  
{{< /notice >}}

## Known-issues

### SSL error

**with the conda command**

You may face with **SSL ERROR** when you run `conda`. 

You can deactivate SSL security.  

For `conda`  :

* open the **miniconda prompt**
* type  `conda config --set ssl_verify False`.   

**SSL error with the pip install command**

Under a secure proxy, the command  `pip install .` may return an SSL warning. 

To deactivate SSL checking, when you want to install a package with pip, add the following argument to your command :    `--trusted-host pypi.org --trusted-host files.pythonhosted.org`.

for instance:

 * type `pip install . --trusted-host pypi.org --trusted-host files.pythonhosted.org`


###  'viconnexusapi' installation failed

{{< notice "warning" >}}
  Administrator rights might be necessary. Open the miniconda console in admin mode.      
{{< /notice >}}

The issue **ModuleNotFoundError** simply indicates you have not installed both vicon-made packages ('viconnexusapi' or  'viconnexusutils') within your python environment.  

These packages are located in the folder `C:\Program Files\Vicon\Nexus2.15\SDK\Win64\Python`. 

To fix this issue: 

 * open your **miniconda prompt**
 * activate your environment (e.g `conda activate pycgm39`)
 * go to the folder `C:\Program Files\Vicon\Nexus2.15\SDK\Win64\Python`
 * type `install_vicon_nexus_api.bat` then `install_vicon_nexus_utils.bat`

this will install the packages in your site-packages folder (`\Miniconda3\envs\(virtualEnvName)\Lib\site-packages`)

