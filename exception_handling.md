## Exception Handling
Getting an error, or exception, in your Python program means the entire program will crash. We want the program to detect errors, handle them, and then continue to run.  

**Exception handling** is how Python deals with errors during program execution (like dividing by zero or reading a missing file). Instead of crashing, you can catch and handle the error gracefully using `try` and `except`.  

### Basic Syntax:
```python
try:
    # Code that might raise an exception
    risky_code()
except SomeException:
    # Code to run if an exception occurs
    handle_error()
```
**Example:**  
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print("Result:", result)
except ZeroDivisionError:
    print("Error: Cannot divide by zero.")
except ValueError:
    print("Error: Invalid input. Please enter a number.")
```
