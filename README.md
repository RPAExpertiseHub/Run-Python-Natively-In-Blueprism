# Python VBO for Blue Prism #

This repository contains the source code for a custom Python Visual Business Object (VBO) for Blue Prism. With this VBO, you can run Python scripts natively within Blue Prism, allowing you to leverage Python's power for complex data processing, machine learning, and automation tasks directly from Blue Prism processes. The VBO supports various .NET data types, ensuring compatibility with Blue Prism’s supported types, and includes actions for managing Python scripts, installing modules, and handling errors.

---------------

# Features #
* Execute Python Scripts in Blue Prism: Run Python scripts with specified parameters and receive output in .NET-compatible types (e.g., Text, Number, Flag, Binary, Image, DateTime, TimeSpan, Collection).
* Package Management: Install and uninstall Python packages using pip.
* Dynamic Parameter Support: Pass data dynamically to Python functions via Blue Prism’s Collection type.
* Timeouts and Error Handling: Set timeouts for script execution and capture error details.

# Requirements #
* Python: Ensure you have Python installed (both 32-bit and 64-bit versions are supported, depending on the VBO version used).
* Blue Prism: Blue Prism installation with the ability to import custom VBOs.
* .NET Types Support: Make sure that the output types used in the Python script are compatible with Blue Prism’s .NET types.
* Install pythonnet module using pip (ex. pip install pythonnet)
~~~
Note: The Python runtime (32-bit or 64-bit) must match the bit version of the VBO in Blue Prism. For example, if using a 32-bit VBO, your Python installation must also be 32-bit.
~~~
---------------
# Installation #
1. Download the Repository: Clone or download the repository from GitHub.

```
git clone https://github.com/your-username/python-vbo-for-blueprism.git
```
2. Import the VBO into Blue Prism:

  * Open Blue Prism, navigate to Studio > Objects, and import the VBO .bpobject or .bprelease file included in the repository.
  * You should see the Python VBO_V3 added to your Objects list.
3. Set the Python Runtime DLL Path:

  * Use the CreateInstance action in the VBO to specify the path to the python.dll file that matches your Python installation (e.g., C:\Python39\python39.dll for a 64-bit version of Python 3.9).
----
# Actions Overview #
Each action in the Python VBO corresponds to a specific .NET type or utility operation. Below is a breakdown of each action, its purpose, parameters, and example usage.

## 1. Create Instance ##
 * Description: Initializes the Python environment in Blue Prism. This action must be called before any Python script can be run.
 * Parameters:
    * PythonRuntimeDLLFilePath (Text): Path to the python.dll file for your Python installation.
    * ScriptExecutorTimeout(Number):  Timeout for script execution.
 * Usage: Create Instance must be the first action called to initialize the Python environment.
 * Example:
~~~
  Ensure the correct path to python.dll
  E.g., "C:\Python39\python39.dll" for Python 3.9
~~~
---------------
## 2. Get Text ##
 * Description: Executes a Python script and retrieves a Text output.
 * Parameters:
   * ScriptOrFilePath (Text): Python script text or file path.
   * CallBackFunctionName (Text, optional): Function name to invoke within the script.
   * Parameters (Collection, optional): Parameters to pass to the function(only 1st row of columns passed as parameters column name is not important order of columns is important).
 * Output:
   * Success (Boolean): True if the script executed successfully.
   * ErrorMessage (Text): Error message if the script fails.
   * Output (Text): Output from the Python function.
 * Example Python Script:
```python
def get_text():
    return "Hello from Python"
```
---------------
## 3. Get Number ##
 * Description: Executes a Python script and retrieves a Number output (decimal).
 * Example Python Script:
```python
def get_number():
    return 42.0
```
---------------
## 4. Get Flag ##
 * Description: Executes a Python script and retrieves a Flag output (Boolean).
 * Example Python Script:
```python
def get_flag():
    return True
```
---------------
## 5. Get Binary ##
 * Description: Executes a Python script and retrieves a Binary output (byte[]).
 * Example Python Script:
```python
import clr
clr.AddReference("System") #System is .Net dll file we can use .Net modules as well as python modules.
from System import * 
from System.IO import File
def getBinary(filePath):
 return File.ReadAllBytes(filePath) #ReadAllBytes will return Byte array, in BP Binary data item is Byte array.
```
---------------
## 6. Get Image ##
 *  Description: Executes a Python script and retrieves an Image (Bitmap).
 * Example Python Script:
```python
import clr
clr.AddReference('System.Drawing')
from System.Drawing import Bitmap
def getImage():
 image = Bitmap(r"C:\Users\Naveen\Desktop\sunrise.jpg") # rplace any image file
 return image
 
```
---------------
## 7. Get DateTime ##
 * Description: Executes a Python script and retrieves a DateTime output.
 * Example Python Script:
```python
import clr
clr.AddReference("System")
from System import DateTime

def get_date_time():
    return DateTime.Now
```
---------------
## 8. Get TimeSpan ##
 * Description: Executes a Python script and retrieves a TimeSpan output.
 * Example Python Script:
```python
import clr
clr.AddReference("System")
from System import TimeSpan

def get_time_span():
    return TimeSpan.FromMinutes(5)
```
## 9. Get Collection ##
 * Description: Executes a Python script and retrieves a Collection (DataTable).
 * Example Python Script:
```python
import clr
clr.AddReference("System")
clr.AddReference("System.Data")
from System.Data import DataTable

def get_collection():
    dt = DataTable()
    dt.Columns.Add("Name")
    dt.Columns.Add("Age")
    row = dt.NewRow()
    row["Name"] = "Naveen"
    row["Age"] = 30
    dt.Rows.Add(row)
    return dt
```
## 10. Install Pip Module ##
 * Description: Installs a Python package using pip.
 * Parameters: Package name (Text).
 * Example:
~~~
Package Name: "numpy"
~~~
---------------
## 11. Uninstall Pip Module ##
 * Description: Uninstalls a Python package using pip.
 * Parameters: Package name (Text).
 * Example:
~~~
Package Name: "numpy"
~~~
## 12. Get ModuleList ##
 * Description: Retrieves a list of installed Python packages.
## 13. Close Instance ##
 * Description: Shuts down the Python environment in Blue Prism. This should be called after all Python processing is complete to release resources.

----

# Example Blue Prism Process #
To demonstrate each action, an example Blue Prism process is included in the repository. This process shows how to:

1. Initialize Python with CreateInstance.
2. Run Python Scripts using various actions (e.g., GetText, GetNumber, GetCollection).
3. Install/Uninstall Modules dynamically using Install Pip Module and Uninstall Pip Module.
4. Close the Python Instance using CloseInstance.

# Troubleshooting #
 * Bit Version Mismatch: Ensure that the Python runtime and VBO have matching bit versions (32-bit or 64-bit). If they don’t match, the Python environment will fail to initialize.
 * DLL Path Errors: Double-check the path to python.dll in the CreateInstance action. It should point to your Python installation directory.
 * Module Import Errors: Ensure that any modules you need are installed in the Python environment by using the Install Pip Module action.
