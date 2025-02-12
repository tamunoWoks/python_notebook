## Python Modules
Python modules are files containing Python code (functions, classes, variables, etc.) that can be reused in other programs. They help organize code, promote reusability, and make programs more modular and maintainable. Python comes with a rich standard library of modules, and you can also create your own custom modules.  
#### Types of Modules
1. Built-in Modules: Pre-installed with Python (e.g., math, os, sys, random).
2. Third-party Modules: Created by the community and installed via tools like pip (e.g., numpy, pandas, requests).
3. Custom Modules: Created by you for your own projects.
#### Using Modules
To use a module, you need to import it into your program using the import statement.
```
import math
```
#### Common Built-in Modules
Here are some commonly used built-in modules:

| Module	| Description |
|---------|-------------|
| math	| Provides mathematical functions (e.g., sqrt, sin, cos). |
| os	| Interacts with the operating system (e.g., file/directory operations).|
| sys	| Provides access to system-specific parameters and functions. |
| random	| Generates random numbers and performs random operations. |
| datetime	| Handles dates and times. |
| json	| Encodes and decodes JSON data. |
| re	| Provides regular expression operations for pattern matching. |
| collections	| Provides specialized container data types (e.g., Counter, deque). |
| itertools	| Provides functions for creating iterators for efficient looping. |  
#### Module Search Path
When you import a module, Python searches for it in the following locations:
1. The current directory.
2. Directories listed in the PYTHONPATH environment variable.
3. Installation-dependent default paths (e.g., Python's standard library).  
You can view the search path using:
```python
import sys
print(sys.path)
```
#### Best Practices
1. Use meaningful names for custom modules.
2. Avoid naming your scripts the same as standard library modules (e.g., math.py).
3. Use if __name__ == "__main__": to define executable code in a module.
``` python 
# mymodule.py
def greet(name):
    return f"Hello, {name}!"

if __name__ == "__main__":
    print(greet("World"))  # Runs only when the script is executed directly
```
Sample code: [Modules](https://github.com/tamunoWoks/python_tutorial/blob/main/modules.ipynb)
