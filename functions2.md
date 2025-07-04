## The None Value
In Python, a value called `None` represents the absence of a value. The `None` value is the only value of the `NoneType` data type while other programming languages might call this value `null`, `nil`, or `undefined`.  
&nbsp;&nbsp;&nbsp;&nbsp; Just like the Boolean `True` and `False` values, you must always write `None` with a capital *N*.  
Functions also return `None` if you use a `return` statement without a value (that is, just the `return` keyword by itself).

## Named Parameters
Python identifies most arguments by their position in the function call. For example, `random.randint(1, 10)` is different from `random.randint(10, 1)`. The first call returns a random integer between 1 and 10 because the first argument determines the low end of the range and the next argument determines its high end, while the second function call causes an error. On the other hand, Python identifies named parameters by the name placed before them in the function call.  
&nbsp;&nbsp;&nbsp;&nbsp; Programmers often use named parameters to provide optional arguments. For example, the `print()` function uses the optional parameters `end` and `sep` to specify separator characters to print at the end of its arguments and between its arguments, respectively.  
**Examples:**
1.
```python
print('Hello', end='')
print('World')
```
- In the above example, the `print()` function uses the `end` named parameter to change the newline character to a different string. Hence the output will be **`HelloWorld`**.

2.
```python
print('cats', 'dogs', 'mice', sep=',')
```
- Usually, when you pass multiple string values to `print()`, the function automatically separates them with a single space. You could replace the default separating string by passing the `sep` named parameter a different string as shown above, to give the output **`cats,dogs,mice`**.
#### NOTE
Some functions have optional named parameters you can specify when calling the function. They are mostly for list and dictionary data types.

## The Call Stack
Like a meandering conversation, calling a function doesn’t send the execution on a one-way trip to the top of a function. Python will remember which line of code called the function so that the execution can return there when it encounters a `return` statement. If that original function called other functions, the execution would return to those function calls first, before returning from the original function call. The function call at the top of the stack is the execution’s current location.  
&nbsp;&nbsp;&nbsp;&nbsp; The call stack is a technical detail that you don’t strictly need to know about to write programs. It’s enough to understand that function calls return to the line number they were called from. However, understanding call stacks makes it easier to understand local and global scopes.
