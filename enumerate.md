## enumerate()
The enumerate() function in Python is a built-in function that adds a counter to an iterable (like a list, tuple, or string) and returns it as an enumerate object.  
&nbsp;&nbsp;&nbsp;&nbsp;This object can then be used in loops to access both the index and the value of each item in the iterable.  

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
