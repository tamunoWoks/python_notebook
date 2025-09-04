## Lists and Tuples
Lists and tuples can contain multiple values, which makes writing programs that handle large amounts of data easier. And since lists themselves can contain other lists, you can use them to arrange data into hierarchical structures.

### The List Data Type
A list is a value that contains multiple values in an ordered sequence. The term list value refers to the list itself (which you can store in a variable or pass to a function, just like any other value), not the values inside the list value.  
> A list value looks like this: `['cat', 'bat', 'rat', 'elephant']`.

Just as string values use quotation marks to mark where the string begins and ends, a list begins with an opening square bracket and ends with a closing square bracket, [ ].  
> We call values inside the list `items`. Items are separated with commas (that is, they are comma-delimited).

##### Example
```python
[1, 2, 3] # A list of three integers

['cat', 'bat', 'rat', 'elephant'] # A list of four strings

['hello', 3.1415, True, None, 42] # A list of several values

spam = ['cat', 'bat', 'rat', 'elephant'] # A list value assigned to a variable

empty = [] # An empty list assigned to a variable
```
