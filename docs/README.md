#  Overview of the PyMIDAS Package

The pymidas package is an integrated, open source, open development port of the MIDAS (Metabolite Imaging and Data Analysis System) software package, which was initially programmed in IDL. It contains multiple applications that can be combined into a pipeline, including: 

1. **importer** - beta - code to import Siemens and GE data (MRIs and EPSI) into MIDAS projects. 
2. **volumizer** - beta - code to volumize Siemens and GE data (MRIs and EPSI) into MIDAS format. 
3. **common** - code used by two or more applications in PyMidas. Includes the libxml.py module used to access MIDAS XML files.
4. **midas_browser** - beta - GUI based selection tool for picking MIDAS Subject.xml nodes on which to act.
5. **epsi** - alpha - porting the IDL epsi2 code to Python.
6. **fdft** - alpha - code to perform FFT and other processing steps
7. **grappa** - alpha - code to perform GRAPPA combination processing steps
8. **lite** - alpha - code to remove lipid contamination via Papoulis-Gerschberg algorithm
9. **mrmask** - alpha - code to create brain and lipid mask from MRI data but at EPSI resolution
10. **pyseg** - alpha - app to segment T1 MRI into gray/white/CSF tissue moieties
11. **qmaps** - alpha - app to evaluate data quality in EPSI brain volume
12. **refdat** - alpha - app uses EPSI water Reference data to calculate data processing corrections
13. **sinorm** - alpha - app to normalize metabolite maps to internal water estimates
14. **util** - alpha - useful code and utilities for running/testing code

All (some) modules have built in examples for running/using the code. Though the test data may not exist in your repository ... sorry. Typically just type:

## History

The MIDAS project provides an integrated set of MRI and MRSI processing functions. The PyMIDAS software supports a "whole-brain" MRSI acquisition method that has been implemented on MRI systems from three major manufacturers.

## Credits

This effort is based on code initially funded by NIH grant 1R01EB008387-01A1 that became the Vespa project. Other funding sources include NIH grants: U01CA264039, and many others

We've had a lot of people support this effort, but I'd like to mention Philip Semanchuk (http://pyspoken.com), Dr. Jeffrey Alger and Dr. Alexander Giuffrida for their early contributions as well as all the Emory contributions from Dr. Hyunsuk Shim, Abinand Rejimon, Anuradha Trivedi, and Karthik Ramesh. 

## License

This project is currently licensed BSD 3-Clause License, see [LICENSE.md](LICENSE.md) file for details 

## Authors

* **Brian J. Soher** - *Principal Investigator* - [Duke Radiology](https://radiology.duke.edu/faculty/brian-j-soher-phd/)

## Acknowledgments

Many.  To be included later.

* Lots of online ('google') searches have inspired this work.  We have tried to list these in each module as relevant.

