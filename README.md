# Python VBO for Blue Prism #

This repository contains the source code for a custom Python Visual Business Object (VBO) for Blue Prism. With this VBO, you can run Python scripts natively within Blue Prism, allowing you to leverage Python's power for complex data processing, machine learning, and automation tasks directly from Blue Prism processes. The VBO supports various .NET data types, ensuring compatibility with Blue Prism’s supported types, and includes actions for managing Python scripts, installing modules, and handling errors.

----

# Features #
* Execute Python Scripts in Blue Prism: Run Python scripts with specified parameters and receive output in .NET-compatible types (e.g., Text, Number, Flag, Binary, Image, DateTime, TimeSpan, Collection).
* Package Management: Install and uninstall Python packages using pip.
* Dynamic Parameter Support: Pass data dynamically to Python functions via Blue Prism’s Collection type.
* Timeouts and Error Handling: Set timeouts for script execution and capture error details.
