# Run Python Natively In Blueprism #

Python VBO - The Python VBO facilitates seamless integration of Python scripting within Blue Prism processes. This VBO leverages the PythonNet library to execute Python scripts directly within Blue Prism, enabling users to harness the power of Python alongside Blue Prism's automation capabilities.

### Actions ###

#### Create Instance ####
This action is used to create an instance of the PythonEngine and should be called before using other actions in this VBO.<br>
<b>Input Parameters:</b> <br>
<b>Python Root Folder Path:</b> Path where Python is installed. <br>
<b>IsDebugMode:</b> Boolean, if enabled, console output will be shown. <br>
<b>Python Version:</b> Python installed version number. Global Script Execution <br>
<b>Time Out:</b> Timeout for each action execution. <br><br>

#### Close Instance ####
This action closes the instance created by the "Create Instance" action.<br><br>

#### Execute Py Script (No Output) ####
This action executes a Python script provided as text.<br>
Input Parameters: <br>
Python_script: Python script text.<br>
Output Variables:<br>
Success: Boolean indicating whether the script executed successfully. <br>
Error_Message: Text containing exception details if Success is false.<br><br>

#### Execute Py Script File (No Output) ####
This action executes a Python script file (.py/.pyc).<br>
Input Parameters:<br>
Python_ScriptFilePath: (Text) - Path to the Python script file.<br>
Output Variables:<br>
Success: Boolean indicating whether the script executed successfully. <br>
Error_Message: Text containing exception details if Success is false.<br><br>

#### Get Text #### (and other data types) 
These actions execute a Python script and retrieve the output as various data types (Text, Binary, Collection, Date, DateTime, Flag, Image, Number, Time, TimeSpan).<br>
Input Parameters:<br>
PyScriptTextOrPyFilePath: Text or file path of the Python script. <br>
Callback Function Name: Name of the callback function. <br>
Parameters: Collection of parameters. <br>
Output Variables:<br>
Success: Boolean indicating whether the script executed successfully.<br>
Error_Message: Text containing exception details if Success is false.<br>
Script_Output: Output data in the specified data type.<br><br>

#### Get Module List ####
This action returns a list of installed Python modules.<br>
Output Variables: <br>
Modules_List: Collection containing the list of installed modules. <br><br>

#### Set Module Search Path ####
This action sets the search path where Python modules are stored.<br>
Input Parameters: <br>
Module_Search_Path: Search path for modules. <br><br>

#### Install Pip Module ####
This action installs a Python module using pip.<br>
Input Parameters:<br>
Module Name: Name of the module to install. Output Variables:<br>
Success: Boolean indicating whether the installation was successful. <br>
Error_Message: Text containing installation error details if Success is false. <br><br>

#### Uninstall Pip Module ####
This action uninstalls a Python module using pip.<br>
Input Parameters:<br>
Module Name: Name of the module to uninstall. Output Variables:<br>
Success: Boolean indicating whether the uninstallation was successful. <br>
Error_Message: Text containing uninstallation error details if Success is false.<br><br>

Support For any issues, questions, or feature requests related to the Python VBO, please open an issue on GitHub.
