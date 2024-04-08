# Run Python Natively In Blueprism #

Python VBO - The Python VBO facilitates seamless integration of Python scripting within Blue Prism processes. This VBO leverages the PythonNet library to execute Python scripts directly within Blue Prism, enabling users to harness the power of Python alongside Blue Prism's automation capabilities.

### Actions ###

#### Create Instance ####
This action is used to create an instance of the PythonEngine and should be called before using other actions in this VBO.<br>
Input Parameters: <br>
`Python Root Folder Path: Path where Python is installed. 
IsDebugMode: Boolean, if enabled, console output will be shown. 
Python Version: Python installed version number. Global Script Execution 
Time Out: Timeout for each action execution.`

#### Close Instance ####
This action closes the instance created by the "Create Instance" action.

#### Execute Py Script (No Output) ####
This action executes a Python script provided as text.
Input Parameters: 
`Python_script: Python script text. `
Output Variables:
`Success: Boolean indicating whether the script executed successfully. 
Error_Message: Text containing exception details if Success is false. `
#### Execute Py Script File (No Output) ####
This action executes a Python script file (.py/.pyc).
Input Parameters:
`Python_ScriptFilePath: (Text) - Path to the Python script file.
Callback Function Name*: (Text) - Function name which should call from script.
Parameters**: (Collection) - parameters to the function.`
Output Variables:
`Success: Boolean indicating whether the script executed successfully. 
Error_Message: Text containing exception details if Success is false. `
5. Get Text (and other data types) 
These actions execute a Python script and retrieve the output as various data types (Text, Binary, Collection, Date, DateTime, Flag, Image, Number, Time, TimeSpan).

Input Parameters:

PyScriptTextOrPyFilePath: Text or file path of the Python script. Callback Function Name: Name of the callback function. Parameters: Collection of parameters. Output Variables:

Success: Boolean indicating whether the script executed successfully. Error_Message: Text containing exception details if Success is false. Script_Output: Output data in the specified data type. 16. Get Module List This action returns a list of installed Python modules.

Output Variables: Modules_List: Collection containing the list of installed modules. 17. Set Module Search Path This action sets the search path where Python modules are stored.

Input Parameters: Module_Search_Path: Search path for modules. 18. Install Pip Module This action installs a Python module using pip.

Input Parameters:

Module Name: Name of the module to install. Output Variables:

Success: Boolean indicating whether the installation was successful. Error_Message: Text containing installation error details if Success is false. 19. Uninstall Pip Module This action uninstalls a Python module using pip.

Input Parameters:

Module Name: Name of the module to uninstall. Output Variables:

Success: Boolean indicating whether the uninstallation was successful. Error_Message: Text containing uninstallation error details if Success is false. Installation To utilize the Python VBO(x64)v3.0 in your Blue Prism environment, follow the instructions in the Installation Guide.

Support For any issues, questions, or feature requests related to the Python VBO(x64)v3.0, please open an issue on GitHub.
