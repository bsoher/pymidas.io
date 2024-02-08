---
sort: 2
---

# Upgrading PyMIDAS

## Overview

The instructions below assume that you already have PyMIDAS installed. 

## Upgrade PyMIDAS 

Start a command shell in the conda environment in which PyMIDAS is installed.

Run this command:

`>pip install pymidas --upgrade`

This should install the most recent version of the PyMIDAS package.  After it is done, please check your Python dependencies by running:

`>python -m pymidas.check_dependencies `

If you are missing any packages, or the versions of packages you have installed are outside PyMIDAS's dependencies, you will be given information about what changes are needed before you can run PyMIDAS.


