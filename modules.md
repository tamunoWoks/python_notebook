## Python Modules
All Python programs can call a basic set of functions called built-in functions, including the print(), input(), and len() functions you’ve seen before. Python also comes with a set of modules called the standard library.  

Each module is a Python program that contains a related group of functions, classes, variables, etc, that can be embedded in your programs. They help organize code, promote reusability, and make programs more modular and maintainable. Python comes with a rich standard library of modules, and you can also create your own custom modules.  
#### Types of Modules
1. Built-in Modules: Pre-installed with Python (e.g., math, os, sys, random).
2. Third-party Modules: Created by the community and installed via tools like pip (e.g., numpy, pandas, requests).
3. Custom Modules: Created by you for your own projects.
#### Using Modules
Before you can use the functions in a module, you must import the module with an `import` statement. In code, an import statement consists of the following:
- The import keyword
- The name of the module
- Optionally, more module names, as long as they are separated by commas
```
import math
```
Once you import a module, you can use all the cool functions of that module.  
Here’s an example of an import statement that imports four different modules:  
```python
import random, sys, os, math
```
Now we can use any of the functions in these four modules.

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

### `from`
An alternative form of the import statement is composed of the `from` keyword, followed by the module name, the `import` keyword, and a star `*`; for example, 
```python
from random import *
```
With this form of import statement, calls to functions in `random` won’t need the `random.` prefix. However, using the full name makes for more readable code, so it is better to use the `import random` form of the statement.  

**Example:**
```python
# Import the 'sqrt' function from the 'math' module
from math import sqrt

# Use the imported function
number = 16
result = sqrt(number)

print(f"The square root of {number} is {result}")
```
