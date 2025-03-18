---
sort: 1
---

# New PyMIDAS Installation

## Installation Steps

PyMIDAS is a Python package. It requires a Python environment be installed with certain dependencies (all easily obtained) and then PyMIDAS can be automatically installed from the Test PyPI web site (only Test PyPI for now). The package on Test PyPI is called pymidas. 

PyMIDAS is an actively developed project with ongoing releases. Once you have it installed, it is simple to upgrade with pip. 

_Note. PyMIDAS is being developed mainly under Python 3.12, but has previously been tested under Python 3.11 as well._

The following instructions are based on using the 'Miniconda' installation, part of the Conda package management sytem, to install the dependencies that PyMIDAS requires. We are only installing the packages we need for simplicity. You could install these packages yourself using other means, but these instructions use conda. 

You'll need to use the command line for most of these instructions. Be careful of typos.

### Step 1 - Install Python (using Miniconda)

PyMIDAS is being developed under Python 3.12. These instructions assume that you used Miniconda to install 64-bit Python as described below.

Download [the 64-bit Miniconda3 package](https://docs.conda.io/en/latest/miniconda.html) for your system. Note - we recommend installing miniconda 'for yourself' vs 'all users' as this installs the 'miniconda3' subdirectory in your home directory. We assume for some hard coded paths below that this is the case.

This will install conda with a very recent base version of Python like 3.12 or newer. Not to worry, Miniconda allow you to create virtual environments with any version of Python 3, and this is what we will use to install/run the PyMIDAS package. So, fire up the conda base command window and create your first environment. This is simple (see below) and it is good to do your actual work in a Python environment outside of the base environment.

Start an Anaconda (aka 'miniconda') command prompt (on Win10) by clicking the Start button, scrolling down the Programs file list to Anaconda, and selecting "Anaconda Prompt".

In the Anaconda prompt, create a new environment within your miniconda installation called 'python39' (or whatever you want to name it) by typing:  

`>conda create --name python312 python=3.12` 

conda will think for a bit, then list the files it will install and ask you to confirm. Type 'y' and return. Conda will then download packages and install them.

The last step here is to activate the new python312 environment by typing: 

`>conda activate python312` 

This switches you from whatever virtual conda environment you are currently in, into the 'python312' (or whatever name you chose) environment you just created. All the additional software installation steps will now be applied to that environment.

### Step 2 - Install PyMIDAS Dependencies

2.1 At the command line, run this command:
 
`>conda install numpy scipy matplotlib configobj packaging lxml `  (if these do not install, try from conda-forge, as in 2.3)` 

2.2 Then run this command:

`>conda install -c conda-forge wxpython  (this may take a long time to finish)`

2.3 Then run this command:

`>conda install -c conda-forge astropy pydicom nibabel nipype tzlocal`

2.4 Then run this command (needed for pydicom to process compressed files):

`>pip install -U pylibjpeg[all]`

### Step 3 - Now Install the PyMIDAS Package 

At the command line, run this command:
 
`>pip install -i https://test.pypi.org/simple/ pymidas`

Just FYI, for now we are distributing pymidas from the TestPyPI server

### Step 4 (optional) - Doublecheck PyMIDAS Dependencies 

At the command line, run this command:
 
`>python -m pymidas.check_dependencies `

### Step 5 (optional) - Create Windows Shortcut to Importer and Volumizer

(Apologies, but for now we do not have Linux or OSX shortcut instruction)

In a text editor, edit the following line(s) to reflect the location of your miniconda 'pymidas312' (or whatever name) environment, and your pymidas Importer or Volumizer GUI modules. To test these, you should be able to cut/paste them into any CMD window and the app will run. It does not have to be a miniconda cmd window.

`%windir%\System32\cmd.exe /k ""D:\bsoher\miniconda3\Scripts\activate.bat" "D:\bsoher\miniconda3\envs\pymidas312" && python "D:\bsoher\miniconda3\envs\pymidas311\Lib\site-packages\pymidas\importer\importer_gui.py" && exit"`

and

`%windir%\System32\cmd.exe /k ""D:\bsoher\miniconda3\Scripts\activate.bat" "D:\bsoher\miniconda3\envs\pymidas312" && python "D:\bsoher\miniconda3\envs\pymidas311\Lib\site-packages\pymidas\volumizer\volumizer_gui.py" && exit"`

On your desktop, right click and select New->Shortcut. When asked to 'Type location of the item:' cut/paste one of the above lines into the dialog box. Click Next and name the Shortcut (typically Importer or Volumizer) and hit Enter.
