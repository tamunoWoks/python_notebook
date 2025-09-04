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
&nbsp;&nbsp;&nbsp;&nbsp;The integer inside the square brackets that follows the list is called an **index**. The first value in the list is at `index 0`, the second value is at `index 1`, the third value is at `index 2`, and so on.  
> Note that because the first index is `0`, the last index is the size of the list minus one. So, a list of four items has `3` as its last index.
