# Run Python Natively In Blueprism #

Python VBO - The Python VBO facilitates seamless integration of Python scripting within Blue Prism processes. This VBO leverages the PythonNet library to execute Python scripts directly within Blue Prism, enabling users to harness the power of Python alongside Blue Prism's automation capabilities.

#### Here are the installation instructions for using the Python VBO in Blue Prism: ####

Download and Install Python:<br><br>

Download Python from the official website: python.org<br>
Follow the installation instructions provided by the Python installer.<br><br>
Download VBO Files:<br>

Download the .bprelease file and Python.Runtime.dll from the repository.<br>
Place Python.Runtime.dll File:<br>

Place the Python.Runtime.dll file in the root directory where Blue Prism is installed.<br>
Import the .bprelease File:<br>

Open Blue Prism and navigate to File.<br>
click on Import and select Relase.<br>
Choose the downloaded .bprelease file and import it into Blue Prism.<br>
Configure Python Instance:<br>

Open the Blue Prism Example-Python process .<br>
Double-click on the "Create Instance" action.<br>
Provide the following input parameters:<br>
Python Root Folder Path: Path where Python is installed.<br>
IsDebugMode: Boolean, set it to true if you want to see console output.<br>
Python Version: Python installed version number.<br>
Global Script Execution Time Out: Timeout for each action execution.<br>
Save the changes to the action.<br><br>

Execute the process to verify that the Python VBO is functioning correctly.<br><br>

### Actions ###

#### Create Instance ####
This action is used to create an instance of the PythonEngine and should be called before using other actions in this VBO.<br>
Input Parameters: <br>
<b>Python Root Folder Path:</b> Path where Python is installed. <br>
<b>IsDebugMode:</b> Boolean, if enabled, console output will be shown. <br>
<b>Python Version:</b> Python installed version number.
<b>Global Script Execution Time Out:</b> Timeout for each action execution. <br><br>

#### Close Instance ####
This action closes the instance created by the "Create Instance" action.<br><br>

#### Execute Py Script (No Output) ####
This action executes a Python script provided as text.<br>
Input Parameters: <br>
<b>Python_script:</b> Python script text.<br>
Output Variables:<br>
<b>Success:</b> Boolean indicating whether the script executed successfully. <br>
<b>Error_Message:</b> Text containing exception details if Success is false.<br><br>

#### Execute Py Script File (No Output) ####
This action executes a Python script file (.py/.pyc).<br>
Input Parameters:<br>
<b>Python_ScriptFilePath:</b> (Text) - Path to the Python script file.<br>
Output Variables:<br>
<b>Success:</b> Boolean indicating whether the script executed successfully. <br>
<b>Error_Message:</b> Text containing exception details if Success is false.<br><br>

#### Get Text (and other data types) ####
These actions execute a Python script and retrieve the output as various data types (Text, Binary, Collection, Date, DateTime, Flag, Image, Number, Time, TimeSpan).<br>
Input Parameters:<br>
<b>PyScriptTextOrPyFilePath:</b> Text or file path of the Python script. <br>
<b>Callback Function Name:</b> Name of the callback function. <br>
<b>Parameters:</b> Collection of parameters. <br>
Output Variables:<br>
<b>Success:</b> Boolean indicating whether the script executed successfully.<br>
<b>Error_Message:</b> Text containing exception details if Success is false.<br>
<b>Script_Output:</b> Output data in the specified data type.<br><br>

#### Get Module List ####
This action returns a list of installed Python modules.<br>
Output Variables: <br>
<b>Modules_List:</b> Collection containing the list of installed modules. <br><br>

#### Set Module Search Path ####
This action sets the search path where Python modules are stored.<br>
Input Parameters: <br>
<b>Module_Search_Path:</b> Search path for modules. <br><br>

#### Install Pip Module ####
This action installs a Python module using pip.<br>
Input Parameters:<br>
<b>Module Name:</b> Name of the module to install. Output Variables:<br>
<b>Success:</b> Boolean indicating whether the installation was successful. <br>
<b>Error_Message:</b> Text containing installation error details if Success is false. <br><br>

#### Uninstall Pip Module ####
This action uninstalls a Python module using pip.<br>
Input Parameters:<br>
<b>Module Name:</b> Name of the module to uninstall.<br> 
Output Variables:<br>
<b>Success:</b> Boolean indicating whether the uninstallation was successful. <br>
<b>Error_Message:</b> Text containing uninstallation error details if Success is false.<br><br>

Support For any issues, questions, or feature requests related to the Python VBO, please open an issue on GitHub.
