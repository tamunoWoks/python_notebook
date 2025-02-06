# Python Notebook
This repository is strictly for learning key python syntax.

Here are the concepts documented:  
- [enumerate()](#enumerate_(_))
- [File Handling](#file_handling)
- [Lambda Functions](#lambda_functions)
- [Object-Oriented Programming](#object-oriented_programming)
- [String Slicing and Striding](#string_slicing_and_striding)
---


## enumerate()
The enumerate() function in Python is a built-in function that adds a counter to an iterable (like a list, tuple, or string) and returns it as an enumerate object. This object can then be used in loops to access both the index and the value of each item in the iterable.  

The syntax for enumerate() is:  
```python
enumerate(iterable, start=0)
```
#### Parameters:
- iterable: The sequence you want to iterate over (e.g., list, tuple, string).
- start: The starting value of the counter (default is 0).
#### How It Works
- enumerate() pairs each element of the iterable with an index, starting from start.
- It returns an enumerate object, which is an iterator yielding tuples of the form (index, value).
#### Why Use enumerate()?
- It eliminates the need to manually manage a counter variable in loops.
- It makes code cleaner and more readable when you need both the index and the value.
- It works with any iterable, including lists, tuples, strings, and more.
  
Sample code: [enumerate](https://github.com/tamunoWoks/python_tutorial/blob/main/enumerate.ipynb)


## File Handling
File handling in Python allows you to work with files on your computer. You can read from and write to files, which is useful for storing and retrieving data. Python provides built-in functions and methods to handle files efficiently.
#### Opening a File
To work with a file, you first need to open it using the open() function.
```python
file = open("filename.txt", "mode")
```
- filename.txt: The name of the file (include the path if necessary)
- mode: Specifies the purpose of opening the file:
  - "r": Read (default mode). Opens the file for reading.
  - "w": Write. Opens the file for writing (creates a new file or overwrites an existing file).
  - "a": Append. Opens the file for appending data (does not overwrite existing data).
  - "x": Exclusive creation. Creates a new file but raises an error if the file already exists.
  - "b": Binary mode (e.g., "rb" or "wb" for reading/writing binary files).
  - "t": Text mode (default).
  - "+": Read and write (e.g., "r+" or "w+").
#### File Methods
Here are some commonly used file methods:
- read(size): Reads a specified number of bytes (or the entire file if no size is given).
- readline(): Reads one line from the file.
- readlines(): Reads all lines into a list.
- write(string): Writes a string to the file.
- writelines(list): Writes a list of strings to the file.
- seek(offset): Moves the file pointer to a specific location.
- tell(): Returns the current position of the file pointer.
- close(): Closes the file.  

Sample code: [File Handling](https://github.com/tamunoWoks/python_notebook/blob/main/file_handling.ipynb)

## Lambda Functions
Lambda functions in Python are small, anonymous functions defined using the lambda keyword. They are often used for short, simple operations where a full function definition is unnecessary. Lambda functions can take any number of arguments but can only have one expression.
The syntax for enumerate() is:  
```python
lambda arguments: expression
```
#### Key Characteristics:
- Anonymous: Lambda functions don't have a name (they are not bound to an identifier).
- Single Expression: They can only contain one expression, which is evaluated and returned.
- Inline Use: Often used inline, such as in map(), filter(), or sorted().
#### When to Use Lambda Functions:
- For simple, one-off operations.
- When passing a function as an argument to higher-order functions like map(), filter(), or sorted().
- When you want to avoid defining a full function for a small task.
#### When Not to Use Lambda Functions:
- For complex logic (use a regular def function instead).
- When the function needs to be reused multiple times (lambda functions are anonymous and harder to reuse).
- When readability is a priority (lambda functions can make code harder to understand if overused).
  
Sample code: [Lambda functions](https://github.com/tamunoWoks/python_tutorial/blob/main/lambda.ipynb)


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

## Object-Oriented Programming
Object-Oriented Programming (OOP) is a programming paradigm that organizes code into objects, which are instances of classes. Python is an object-oriented language, and it supports all the core concepts of OOP, such as encapsulation, inheritance, polymorphism, and abstraction.
#### Key Concepts of OOP in Python:
- **Class:**
  - A blueprint for creating objects.
  - Defines attributes (data) and methods (functions) that the objects will have.
- **Object:**
  - An instance of a class.
  - Represents a specific entity with its own data and behavior.
- **Encapsulation:**
  - Bundling data (attributes) and methods (functions) that operate on the data into a single unit (class).
  - Restricting direct access to some of an object's components (using private/protected members).
  **How It Works:**
    - Use private attributes (e.g., self.__balance) to hide data.
    - Provide public methods to interact with the data (e.g., deposit, withdraw).  
  **Benefits:**
    - Improves security by preventing unauthorized access.
    - Makes code easier to maintain and modify.
    - Reduces complexity by hiding implementation details.
- **Inheritance:**
  - A mechanism where a new class (child class) derives properties and behaviors from an existing class (parent class).
  - Promotes code reuse and hierarchical classification.  
  **How It Works:**
    - Use the syntax class ChildClass(ParentClass) to inherit from a parent class.
    - Child classes can override or extend parent class methods.  
  **Benefits:**
    - Reduces code duplication.
    - Makes code more organized and easier to maintain.
    - Supports the "is-a" relationship (e.g., a Dog is an Animal).
- **Polymorphism:**
  - The ability of different classes to be treated as instances of the same class through a common interface.
  - Allows methods to behave differently based on the object that calls them.  
  **How It Works:**
    - Achieved through method overriding (child classes provide their own implementation of a method).
    - A single function or method can work with objects of different classes.  
  **Benefits:**
    - Simplifies code by allowing a single interface to represent different types.
    - Makes code more flexible and scalable.
    - Supports the "one interface, multiple implementations" principle.  
- **Abstraction:**
  - Hiding complex implementation details and exposing only the necessary features.
  - Achieved through abstract classes and interfaces.  
  **Key Points:**
    1. Abstract Class:
        - Cannot be instantiated directly.
        - Serves as a blueprint for other classes.
        - Ensures that subclasses implement specific methods.
    2. Abstract Methods:
        - Declared in the abstract class but have no implementation.
        - Must be implemented by any subclass.
    3. Concrete Class:
        - Inherits from the abstract class.
        - Provides implementations for all abstract methods.
    4. Abstraction:
        - Hides complex implementation details.
        - Exposes only the necessary features (e.g., area and perimeter methods).    
  **Why Use Abstraction?**
    - Enforces Structure: Ensures that subclasses adhere to a specific interface.
    - Improves Maintainability: Makes code easier to understand and modify.
    - Promotes Reusability: Common functionality is defined in the abstract class, and subclasses can reuse it.
#### Magic/Dunder Methods:
Python classes can define special methods (e.g., __init__, __str__, __add__) to enable operator overloading and other behaviors.
#### Why Use OOP in Python?
- Modularity: Code is organized into reusable components.
- Reusability: Inheritance allows code reuse.
- Maintainability: Easier to debug and maintain.
- Scalability: Suitable for large and complex applications.

Sample code: [Object-Oriented Programming](https://github.com/tamunoWoks/python_tutorial/blob/main/oop.ipynb)


## String slicing and striding
- String slicing in Python is a powerful feature that allows you to extract a portion of a string (substring) by specifying a start index, an end index, and an optional step size.  
- String striding in Python refers to the process of accessing characters in a string at regular intervals by specifying a step value in the slicing syntax. It allows you to skip characters or traverse the string in a specific pattern.  

The syntax for string slicing & striding is:  
```python
string[start:end:step]
```
#### Parameters:
- start: The starting index of the slice (inclusive). If omitted, it defaults to 0 (the beginning of the string).
- end: The ending index of the slice (exclusive). If omitted, it defaults to the length of the string (the end of the string).
- step: It determines the stride between indices. If omitted, it defaults to 1. The step size is optional for slicing but necessary for striding.
#### Key Points to Remember
- Python uses zero-based indexing, meaning the first character of the string has an index of 0.
- The slice includes the character at the start index but excludes the character at the end index.
- The step value determines the direction and interval of traversal.
- A positive step moves from left to right.
- A negative step moves from right to left.
- If the step is 1, the string is traversed normally (no skipping).
- If the step is greater than 1, characters are skipped.
- If the step is -1, the string is reversed
#### Common Use Cases:
- Extracting substrings.
- Extracting alternate characters
- Reversing strings.
- Skipping characters at regular intervals.
- Creating patterns.
  
Sample code: [Slicing & Striding](https://github.com/tamunoWoks/python_tutorial/blob/main/slicing_and_striding.ipynb)
