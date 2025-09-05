##  Short-Circuiting Boolean Operators
Boolean operators have a subtle behavior that is easy to miss. Recall that if either of the values combined by an `and` operator is `False`, the entire expression is `False`, and if either value combined by an `or` operator is `True`, the entire expression is `True`. If I presented you with the expression `False` and `spam`, it doesn’t matter whether the `spam` variable is `True` or `False` because the entire expression would be `False` either way. The same goes for `True` or `spam`; this evaluates to `True` no matter the value of `spam`.  
&nbsp;&nbsp;&nbsp;&nbsp;Python (and many other programming languages) use this fact to optimize the code so that it runs a little faster by not examining the right-hand side of the Boolean operator at all. This shortcut is called **short-circuiting**.  
Most of the time, your program will behave the same way it would have if Python checked the entire expression (albeit a few microseconds faster). However, let's consider this short program, where we check whether the first item in a list is 'cat':
```python
spam = ['cat', 'dog']

if spam[0] == 'cat':
  print('A cat is the first item.')
else:
  print('The first item is not a cat.')
```
As written, this program prints `A cat is the first item`. But if the list in `spam` is empty, the `spam[0]` code will cause an `IndexError: list Index out of range` error.  
To fix this, we’ll adjust the if statement’s condition to take advantage of short-circuiting:
```python
spam = []

if len(spam) > 0 and spam[0] == 'cat':
  print('A cat is the first item.')
else:
  print('The first item is not a cat.'
```
This program never has an error, because if `len(spam) > 0` is `False` (that is, the list in `spam` is empty), then short-circuiting the and operator means that Python doesn’t bother running the `spam[0] == 'cat'` code that would cause the `IndexError` error.  
Keep this short-circuiting behavior in mind when you write code that involves the `and` and `or` operators.

## Sequence Data Types
Lists aren’t the only data types that represent ordered sequences of values. Strings and lists are actually similar if you consider a string to be a “list” of single text characters. The Python sequence data types include lists, strings, range objects returned by range(), and tuples.  
&nbsp;&nbsp;&nbsp;&nbsp;Many of the things you can do with lists can also be done with strings and other values of sequence types. For example:
```python
name = 'Zophie'

name[0] # 'Z'
name[-2] # 'i'
name[0:4] # 'Zoph'

'Zo' in name # True
'z' in name # False
'p' not in name # False

for i in name:
  print('* * * ' + i + ' * * *')

# * * * Z * * *
# * * * o * * *
# * * * p * * *
# * * * h * * *
# * * * i * * *
# * * * e * * *
```
You can do all the same things with sequence values that you can do with lists: indexing, slicing, for loops, `len()`, and the  `in` and  `not` in operators.
