## Part 1
- Install GitHub Desktop to push, branch and fetch code from your local folder to the repository.
- MATLAB Git Source Control can´t deal very well with external files, is not recommended to use. 
- Visual Studio Code is free and is a great editor for Python and C++. Although marfurta and waterdog1 had issues to get it working with Conda distribution. (had to manually uninstall and reinstall numpy) 
- We will all work with Python 3.7
- PyCharm is a good alternative to Visual Studio Code
- Both PyCharm and Visual Studio Code create subfolders with user settings. These folders will not be committed to the Repository. Use the “ignore” option from GitHub Desktop
- Godjka wants to have a to do list with tasks. 
- Actions: 
  - ho1 to print a basic wiki to get started with Python: what anaconda distribution, editor, etc)
  - marfurta to set up a project with tasks

## Part 2

- We will work with one single repository with all the languages organized in different folders. 
- The repositories “” and “” will eventually be deleted
- Waterdog1 raised some concerns regarding privacy. It is agreed by all members that only the GitHub usernames will be used in public documents. Real names and email addresses are kept for emails only. 
- For now, we will work with waterdog1 private repository
- Actions:
  - Delete old repositories
  - Create a naming convention and coding style in the wiki for function names, variables names, tire slang (e.g. alpha, slip angle or SA)
  - Review waterdog1 implementation that works in Python and MATLAB and they have the same methods. 

## Part 3

- waterdog1 has a C++ implementation of the magic formula model that has already be modified to be used by MATLAB by compiling .mex files. He recons 99% of that code can be recycled to be used in other languages (e.g. Python) and only the entry file will be modified. 
- At this stage code duplication is not that bad and is manageable. We will duplicate the brush and magic formula models in MATLAB and Python until we define a path for code binding. 

## Part 4

- h01 shows a presentation. 
- waterdog1 has a Simulink home license and is exploring the S functions concept. 
- waterdog1 reckons that parallel implementations in different languages is OK for now. But any long-term professional application will inevitably end up doing all the coding in C/C++ with bindings to other languages. 
- pgr might help with Python C code binding and code generation
- The core maths of the models can be easily done in any language. But the loading/saving/metadata and other generic management tasks is very specific to each language. 
- Something waterdog1 and marfurta have learned is that passing the model parameters in the form of a long vector is much faster and efficient. So all models will need a name2index and index2name function to convert from “parameterStruct.PKY2” to “parmeterArray[32]” and vice versa. 
- We can distinguish 3 levels of coding:
  - Core maths (very generic to any language)
  - The load/save/metadata functions (semi dependent on the language)
  - Plotting /end-user tools (extremely dependant on the language)
- h01 likes Jupyter Notebooks to make OpenTire accessible and share tutorials
- Actions:
  - Transfer the load/save/metadata functions from MATLAB to Python

## Part 5

- To get a feeling of waterdog1 architecture in Phython
- Explore how to gerate C code from Python using the brush and magic formula models
- We will skip the load/save/metadata functions for now by using default values. 
- Actions:
  - waterdog will update the repo to include the brush model in Python
  - h01 and Godjka will work on the python side
  - A catch-up email will be sent on Wednesday to see if we have a meeting on Friday. 
