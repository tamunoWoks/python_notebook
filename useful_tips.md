## Useful Python Tips  

- You can view the step-by-step execution of a program using the Python Tutor visualization tool at [Python Tutor](http://pythontutor.com). Click the forward button to move through each step of the program’s execution. You’ll be able to see how the variables’ values and the output change.
  
- **VARIABLE NAMES:**  
  A good variable name describes the data it contains, and though you can name your variables almost anything, Python does have some naming restrictions. Your variable name must obey the following four rules:
    - It can’t have spaces.
    - It can use only letters, numbers, and the underscore (_) character.
    - It can’t begin with a number.
    - It can’t be a Python keyword, such as if, for, return, or other keywords
you’ll learn in this book.

- **BOOLEAN VALUES:**  
  The ***Boolean*** data type has only two values: **True** and **False**. (Boolean is capitalized because the data type is named after mathematician George Boole.)  
  Note that these Boolean values don’t have quotes, because they are different from the string values 'True' and 'False'.
  
- Boolean operators `and`, `or` and `not` have an order of operations just like the math operators do. After any math and comparison operators evaluate, Python evaluates the `not` operators first, then the `and` operators, and then the `or` operators.

- **THE DIFFERENCE BETWEEN THE == AND = OPERATORS:**  
  The `==` operator (equal to) has two equal signs, while the `=` operator (assignment) has just one equal sign.
    - The `==` operator asks whether two values are the same as each other.
    - The `=` operator puts the value on the right into the variable on the left.

- **INFINITE LOOP:**  
If you ever run a program that has a bug causing it to get stuck in an infinite loop, press CTRL-C. This will send a KeyboardInterrupt error to your program and cause it to stop immediately.

- **“TRUTHY” AND “FALSEY” VALUES AND THE BOOL( ) FUNCTION:**  
Conditions will consider some values in other data types equivalent to `True` or `False`. When used in conditions, 0, 0.0, and '' (the empty string) are considered `False`, while all other values are considered `True`.  
If you want to know if a value is truthy or falsey, pass it to the bool() function:
```python
bool(0) # = False
bool(42) # =True
bool('Hello') # = True
bool('') # =False
```

- You can use `continue` and `break` statements only inside `while` and `for` loops. If you try to use these statements elsewhere, Python will give you an error.

- **range():**  
The `range()` function in `for` loops has you specify the number that the loop goes up to, minus one.  
In programming, ranges are often specified in a “closed, open” format that includes the starting number but excludes the ending number.

- **Module names:**  
When you save your Python scripts, take care not to give them a name that is used by one of Python’s modules, such as random.py, sys.py, os.py, or math.py.  
&nbsp&If you accidentally name one of your programs, say, random.py, and use an import random statement in another program, your program will import your random.py file instead of Python’s random module.  
&nbsp&This can lead to errors such as AttributeError: module 'random' has no attribute 'randint', since your random.py file doesn’t have the functions that the real random module has. 
