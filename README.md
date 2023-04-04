# Python Aspen Plus Connected Model for the Calculation of Equipment Costs
Python model for the calculation of equipment costs (e.g. for the CSTR reactor, heat exchangers, RADFRAC distillation columns, etc.) that were simulated in Aspen Plus. The python code retrieves data from Aspen Plus, applies cost correlations of Seider et al. (2009) using this data, feeds input variables to Aspen Plus (if necessary), runs the simulation (if necessary) and gives the dimensions as well as equipment costs as output.

## Prerequisites
For this, the connection of Aspen Plus and Python is first required, which is done by pywin32 to provide access, control and automation of Aspen Plus from python. Hence, each package starts with this connection, and the code can be found below. A detailed example for this connection including a python and aspen plus file which is feeding / retrieving data to / from Aspen Plus from python can be found at @edgarsmdn [Aspen Plus Python Connection Example](https://github.com/edgarsmdn/Aspen_Plus_Python#aspen-plus-python-connection-example)

```ruby

# 0) Import packages
import os                          # Import operating system interface
import win32com.client as win32    # Import COM

# 1) Get path to Aspen Plus backup file called simulation
file_name = 'simulation.bkp'
aspen_path = os.path.abspath(file)

# 2) Initiate Aspen Plus application and file
Application = win32.Dispatch('Apwn.Document') # Registered name of Aspen Plus
Application.InitFromArchive2(aspen_path)

# 3) Application becomes visible with 
Application.visible = 1

```
