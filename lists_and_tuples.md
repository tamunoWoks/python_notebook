# Lists and Tuples
Lists and tuples can contain multiple values, which makes writing programs that handle large amounts of data easier. And since lists themselves can contain other lists, you can use them to arrange data into hierarchical structures.

## The List Data Type
A list is a value that contains multiple values in an ordered sequence. The term list value refers to the list itself (which you can store in a variable or pass to a function, just like any other value), not the values inside the list value.  
> A list value looks like this: `['cat', 'bat', 'rat', 'elephant']`.

Just as string values use quotation marks to mark where the string begins and ends, a list begins with an opening square bracket and ends with a closing square bracket, [ ].  
> We call values inside the list `items`. Items are separated with commas (that is, they are comma-delimited).

#### Example
```python
[1, 2, 3] # A list of three integers

['cat', 'bat', 'rat', 'elephant'] # A list of four strings

['hello', 3.1415, True, None, 42] # A list of several values

spam = ['cat', 'bat', 'rat', 'elephant'] # A list assigned to a variable

empty = [] # An empty list assigned to a variable
```
The spam variable is assigned only one value: the list value. But the list value itself contains other values.  
> Note that the value [ ] is an empty list that contains no values, similar to '', the empty string.

### Indexes:
Say you have the list `['cat', 'bat', 'rat', 'elephant']` stored in a variable named `spam`. The Python code `spam[0]` would evaluate to `'cat'`, the code `spam[1]` would evaluate to `'bat'`, and so on.  
&nbsp;&nbsp;&nbsp;&nbsp;The integer inside the square brackets that follows the list is called an **INDEX**.  
The first value in the list is at `index 0`, the second value is at `index 1`, the third value is at `index 2`, and so on.  
> Note that because the first index is `0`, the last index is the size of the list minus one. So, a list of four items has `3` as its last index.

#### Example
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[0] # 'cat'
spam[1] # 'bat'
spam[2] # 'rat'
spam[3] # 'elephant'

['cat', 'bat', 'rat', 'elephant'][3] # 'elephant'

'Hello, ' + spam[0] # 'Hello, cat'

'The ' + spam[1] + ' ate the ' + spam[0] + '.' # 'The bat ate the cat.'
```
#### Note
Python will give you an `IndexError` error message if you use an index that exceeds the number of values in your list value:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[10000]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    spam[10000]
IndexError: list index out of range
```
#### Note
Lists can also contain other list values. You can access the values in these lists of lists using multiple indexes, like so:
```python
spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]

spam[0] # ['cat', 'bat']
spam[0][1] # 'bat'
spam[1][4] # 50
```
The first index dictates which list value to use, and the second indicates the value within the list value.

### Negative Indexes:
While indexes start at `0` and go up, you can also use negative integers for the index. For example:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[-1] # 'elephant' > The last index
spam[-3] # 'bat' > The third to last index

'The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.' # 'The elephant is afraid of the bat.'
```
The integer value `-1` refers to the last index in a list, the value `-2` refers to the second to last index in a list, and so on.

### Slices:
Just as an index can get a single value from a list, a slice can get several values from a list, in the form of a new list. We enter a slice between square brackets, like an index, but include two integers separated by a colon.  
Notice the difference between indexes and slices:
  - `spam[2]` is a list with an index (one integer).
  - `spam[1:4]` is a list with a slice (two integers).
