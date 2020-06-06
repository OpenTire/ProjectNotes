## Present:
* ho1, mafurta, crayolle, Godjka, mjschroeder,gregorysmithuk, ricardo.ferreira94

## Definitions:
* Functional Mock-Up Units (FMUs): are compiled dynamic models compliant with the Functional Mock-Up Interface (FMI). 
FMUs basically contain the entire tire model packaged, compiled and ready to be plugged into a compatible software. 
You can think of the FMU like a zip. file with all the entire model inside.
* Standard Tire Interface (STI): defined by the TYDEX group in 1996, it's the standard way to integrate tire models into vehicle models and it's widely used by simulation software such as CarMaker, Simpack or ADAMS. The interface basically defines the inputs and outputs of the tire model.
It is a bit old fashioned, e.g. CDTire and FTire have their own interfaces. Maybe OpenTire should define a new interface: Open Tire Interface (OTI).

## Poll about coding languades:
* MATLAB: Greg, Carlos (but understand Python), Ricardo (open for Python), Matt, Marco.
* Python: Henning, Joao, Matt (is OK), Marco.

## Round the table:
Marco:
* Initially, OpenTire was thought to be a repository to help for R&D, when you need something going, but perhaps code performance was not so important. 
* The concept of OpenTire seems to be steering towards a code architecture instead of a repository.  
* MATLAB is probably the best language for C code generation and FMUs.
* Code performance is important for professional applications of OpenTire 

Greg:
* Integration between simulation softwares and the tire models is really important. 
* OpenTire to be used like a hub to intercontect tire models and simulation softwares.

Joao:
* We could use MATLAB as a pre-prototyping tool.

Henning:
* Does it make sense to use Python as the base language?

Matt:
* I have no problem calling Python from MATLAB. The only challenges I have is the Python versioning etc.

Joao:
* There are some good tools for Python.

Greg: 
* Who would be using OpenTire?
* MATLAB should be able to call native Python code, it's easier.

## Conclusions:

* Write the code in Python, since it can be called by MATLAB without having to be complied or converted.

* Write MATLAB and Python utilities to help with plotting etc. (but still called the original Python code for the solver).

* Down the line, we can use (free) Python tools to automatically generate high performing C code or dll's.

* We would then have to update the MATLAB and Python utilities to call the C code or dll's instead of the Python code. (I think this is what TNO does for dteval and simulink blocks)

* But if the interface is the same between C and Pyhton, that shouldn’t be too bad?

* There is a PyFMI for loading FMUs in Python. https://pypi.org/project/PyFMI/
  
* There should not be any code duplication on the OpenTire maintained models. For example, if the MF6.2 core is written in MATLAB there shouldn't be a Python version. 
