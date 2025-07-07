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
### Optional Blocks:
- `else`: runs if no exception occurred
- `finally`: runs no matter what — good for cleanup
```python
try:
    f = open("data.txt")
    data = f.read()
except FileNotFoundError:
    print("File not found.")
else:
    print("File read successfully.")
finally:
    f.close()  # Always executed
```
### Common Built-in Exceptions:
| Exception           | Raised When...                         |
| ------------------- | -------------------------------------- |
| `ZeroDivisionError` | You divide by zero                     |
| `ValueError`        | Invalid value passed (e.g. to `int()`) |
| `TypeError`         | Invalid type used in operation         |
| `FileNotFoundError` | File not found                         |
| `IndexError`        | List index out of range                |
| `KeyError`          | Dict key not found                     |

### Best Practices:
- Catch specific exceptions, not just `except:`
- Use `finally` for closing resources (files, DBs)
- Avoid using `try` for control flow — use only when needed.
