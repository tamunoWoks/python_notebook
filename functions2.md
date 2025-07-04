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
- Some functions have optional named parameters you can specify when calling the function. They are mostly for list and dictionary data types.
