## The None Value
In Python, a value called `None` represents the absence of a value. The `None` value is the only value of the `NoneType` data type while other programming languages might call this value `null`, `nil`, or `undefined`.  
&nbsp;&nbsp;&nbsp;&nbsp; Just like the Boolean `True` and `False` values, you must always write `None` with a capital *N*.  
Functions also return `None` if you use a `return` statement without a value (that is, just the `return` keyword by itself).

## Named Parameters
Python identifies most arguments by their position in the function call. For example, `random.randint(1, 10)` is different from `random.randint(10, 1)`. The first call returns a random integer between 1 and 10 because the first argument determines the low end of the range and the next argument determines its high end, while the second function call causes an error. On the other hand, Python identifies named parameters by the name placed before them in the function call.
&nbsp;&nbsp;&nbsp;&nbsp; Programmers often use named parameters to provide optional arguments. For example, the `print()` function uses the optional parameters `end` and `sep` to specify separator characters to print at the end of its arguments and between its arguments, respectively.
