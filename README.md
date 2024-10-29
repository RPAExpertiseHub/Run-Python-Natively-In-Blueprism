# Python VBO for Blue Prism #

This repository contains the source code for a custom Python Visual Business Object (VBO) for Blue Prism. With this VBO, you can run Python scripts natively within Blue Prism, allowing you to leverage Python's power for complex data processing, machine learning, and automation tasks directly from Blue Prism processes. The VBO supports various .NET data types, ensuring compatibility with Blue Prism’s supported types, and includes actions for managing Python scripts, installing modules, and handling errors.

----

# Features #
* Execute Python Scripts in Blue Prism: Run Python scripts with specified parameters and receive output in .NET-compatible types (e.g., Text, Number, Flag, Binary, Image, DateTime, TimeSpan, Collection).
* Package Management: Install and uninstall Python packages using pip.
* Dynamic Parameter Support: Pass data dynamically to Python functions via Blue Prism’s Collection type.
* Timeouts and Error Handling: Set timeouts for script execution and capture error details.

# Requirements #
* Python: Ensure you have Python installed (both 32-bit and 64-bit versions are supported, depending on the VBO version used).
* Blue Prism: Blue Prism installation with the ability to import custom VBOs.
* .NET Types Support: Make sure that the output types used in the Python script are compatible with Blue Prism’s .NET types.
~~~
Note: The Python runtime (32-bit or 64-bit) must match the bit version of the VBO in Blue Prism. For example, if using a 32-bit VBO, your Python installation must also be 32-bit.
~~~
----
# Installation #
1. Download the Repository: Clone or download the repository from GitHub.

```
git clone https://github.com/your-username/python-vbo-for-blueprism.git
```
2. Import the VBO into Blue Prism:

  * Open Blue Prism, navigate to Studio > Objects, and import the VBO .bprelease file included in the repository.
  * You should see the PythonExecutor VBO added to your Objects list.
3.Set the Python Runtime DLL Path:

  * Use the CreateInstance action in the VBO to specify the path to the python.dll file that matches your Python installation (e.g., C:\Python39\python39.dll for a 64-bit version of Python 3.9).
----
# Actions Overview #
Each action in the Python VBO corresponds to a specific .NET type or utility operation. Below is a breakdown of each action, its purpose, parameters, and example usage.

1. CreateInstance
 * Description: Initializes the Python environment in Blue Prism. This action must be called before any Python script can be run.
 * Parameters:
    * PythonRuntimeDllPath (Text): Path to the python.dll file for your Python installation.
 * Usage: CreateInstance must be the first action called to initialize the Python environment.
 * Example:
~~~
  Ensure the correct path to python.dll
  E.g., "C:\Python39\python39.dll" for Python 3.9
~~~
