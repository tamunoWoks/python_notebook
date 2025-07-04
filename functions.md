## Functions
A function is like a mini program within a program.  
Python provides several built-in functions, such as the print(), input(), and len() functions, but you can also write your own.

#### Creating Functions in Python:
In Python, functions are created using the `def` keyword followed by the function name, parentheses `()`, and a colon `:`. The function body is written with indentation underneath the definition line.  

To call a function in Python, you simply write the function name followed by parentheses `()`, and pass any required arguments inside the parentheses.

##### Example:
This is a simple function with no parameters:
```python
def greet():
    print("Hello, world!")
greet()
```
A major purpose of functions is to group code that gets executed multiple times. Without a function defined, you would have to copy and paste this code each time you wanted to run it.  
    In general, you always want to avoid duplicating code, because if you ever decide to update the code you’ll have to remember to change the code in every place you copied it.
