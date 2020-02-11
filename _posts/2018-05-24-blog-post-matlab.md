---
title: 'Tricks while Using Matlab'
date: 2018-05-24
permalink: /posts/2018/05/Matlab_Jupyter/
tags:
  - Matlab
  - Jupyter Notebook
categories:
  - Tools
---

## Using Matlab in Jupyter Notebook ##
Jupyter notebook can combine text and code. When you are study new things and take notes, it could be really helpful. The steps are:

1. Make sure you have Anacoda and Matlab installed. Python is added to the PATH.(Python can be called from the command window.)
2. Install [Matlab python engine](https://www.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html) 
3. Install metakernel, matlab_kernel, and pymatbridge. For instance, open Anaconda prompt and run
`pip install metakernel`

Now you can open Jupyter notebook and see Matlab as a language!


## Matlab path at startup ##
If you want to add/remove your personal folder from matlab path, use

`edit pathdef.m`