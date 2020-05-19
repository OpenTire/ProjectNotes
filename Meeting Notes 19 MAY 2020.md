## Present:
- ho1, mafurta

## mfeval vs. OpenTire Differneces
### Function vs. Instance
- mfeval is not an instance of the model, but is called as a function withe parameter
- OpenTirePython uses an instance
- There can be performance advantages with having an instance if the model require significant setup 

### TireState
- Mfeval has a fixed “inputsMF” which is an ordered array/vector
- Opentire has a “TireState” which can depend on the model and is a dictionary

### Default Model
- Mfeval – you have to have a TIR file or a Structure (which is way faster)
- Can have incomplete TIR, but 3 examples provided and if a value is missing it assigns it zero?
- OpenTire – default values exist

### UseMode vs SolverMode
- mfeval uses “UseMode” to mimic dteval behavior – which is an “array of digits”
- OpenTire uses SolverMode dictionary – but they should be dependent on the type of tire model

## Discussion about Future Direction
- We are OK with mfeval and OpenTirePython having different structures
    - Due to the history of mfeval and current usage, we don’t want to change it immediately
    - If there is a good reason in the future to change it, we will do so
    - Document differences on the website/Github

- OpenTire should be an umbrella for open-source tire models of any kind, in any language
    - Requirement is that it need to have a documentation, examples and some sort of wrapper to be able to call it from Python/MATLAB/or something?
    - Test environment is using Python to call any model to evaluate it’s performance and make sure the results make sense
    - TireState as a dictionary could make sense, if the wrapper has to be responsible to adapt it to the specific models requirements

- Update to OpenTire.org to reflect mfeval + Python
    - Keep the webpage simple and link to GitHub for “dynamic content” ex. Wiki

- For OpenTire we want to take the following steps
    - Review/redefine the “model interface”
    - Example: Function vs. Instance, Parameters as an input or living in the instance, UseMode/SolverMode etc.
    - Update PAC2002 to Py3
    - Add BrushModel to Py3/OpenTirePython
    - Add MF6.x to Py3

- Also come up with a test environment to compare mfeval to OpenTirePython
    - Possibly be a Jupyter notebook that calls both Python and MATLAB or a MATLAB equivalent
    - Creating a unit test environment before any commits… there are features in GitHub
    
- LongTerm Goals:
    - Compiled version of the tire models for faster computation (for use in simulations/games etc.)
    - Having a common “STI” or helpers function to get you to a known coordinate system etc (ISO-C vs. ISO-W).
    - Having a wrapper to call any model, including C models
    - Provide example TIR of car/truck/bus/aircraft/motorcycle tires





