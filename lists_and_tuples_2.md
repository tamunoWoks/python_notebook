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

###  Mutable and Immutable Data Types:
Lists and strings differ in an important way. A list value is a *mutable* data type: you can add, remove, or change its values. However, a string is *immutable*: it cannot be changed. Trying to reassign a single character in a string results in a `TypeError` error. For example:
```python
name = 'Zophie a cat'
name[7] = 'the'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    name[7] = 'the'
TypeError: 'str' object does not support item assignment
```
The proper way to “mutate” a string is to use slicing and concatenation to build a *new* string by copying from parts of the old string:
```python
name = 'Zophie a cat'

new_name = name[0:7] + 'the' + name[8:12]
name # 'Zophie a cat'
new_name # 'Zophie the cat'
```
We used [0:7] and [8:12] to refer to the characters we don’t wish to replace. Notice that the original 'Zophie a cat' string isn’t modified, because strings are immutable.  
&nbsp;&nbsp;&nbsp;&nbsp;Although a list value is mutable, the second line in the following code doesn’t modify the list `eggs`:
```python
eggs = ['A', 'B', 'C']
eggs = [ 'x', 'y', 'z']
eggs # ['x', 'y', 'z']
```
The list value in eggs isn’t being changed here; rather, a new and entirely different list value (['x', 'y', 'z']) is replacing the old list value (['A', 'B', 'C']).  
&nbsp;&nbsp;&nbsp;&nbsp;If you wanted to actually modify the original list in eggs to contain ['x', 'y', 'z'], you would have to use `del` statements and the `append()` method, like this:
```python
eggs = ['A', 'B', 'C']

del eggs[2]
del eggs[1]
del eggs[0]

eggs.append('x')
eggs.append('y')
eggs.append('z')

eggs # ['x', 'y', 'z']
```
In this example, the `eggs` variable ends up with the same list value it started with. It’s just that this list has been changed (mutated) rather than overwritten. We call this *changing the list in place*.

### The Tuple Data Type:
There are only two differences between the *tuple* data type and the list data type. The first difference is that you write tuples using parentheses instead of square brackets. For example:
```python
eggs = ('hello', 42, 0.5)

eggs[0] # 'hello'
eggs[1:3] # (42, 0.5)
len(eggs) # 3
```
The second and primary way that tuples are different from lists is that tuples, like strings, are immutable: you can’t modify, append, or remove their values. For example:
```python
eggs = ('hello', 42, 0.5)

eggs[1] = 99
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    eggs[1] = 99
TypeError: 'tuple' object does not support item assignment
```
You can use tuples to convey to anyone reading your code that you don’t intend for that sequence of values to change. If you need an ordered sequence of values that never changes, use a tuple. A second benefit of using tuples instead of lists is that, because they’re immutable and their contents don’t change, Python can implement optimizations that make code using tuples slightly faster than code using lists.

### List and Tuple Type Conversion:
Just as `str(42)` will return `'42'`, the string representation of the integer 42, the functions  `list()` and `tuple()` will return list and tuple versions of the values passed to them. For example:
```python
tuple(['cat', 'dog', 5]) # ('cat', 'dog', 5)

list(('cat', 'dog', 5)) # ['cat', 'dog', 5]

list('hello') # ['h', 'e', 'l', 'l', 'o']

tuple('hello) # ('h', 'e', 'l', 'l', 'o')
```
Converting a tuple to a list is handy if you need a mutable version of a tuple value.

## References
A common metaphor is that variables are boxes that “store” values like strings and integers. However, this explanation is a simplification of what Python is actually doing. A better metaphor is that variables are paper name tags attached to values with string.  
&nbsp;&nbsp;&nbsp;&nbsp;When you assign a value to a variable, you’re actually creating the value in the computer’s memory and storing a reference to it in the variable. When you copy the value and assign it to another variable, you’re copying the reference. Both variables refer to the value in the computer’s memory.  
&nbsp;&nbsp;&nbsp;&nbsp;Using the name tag metaphor for variables, you’ve attached both variables name tags to the same 
value. When you assign the forst variable a new value, you’ve changed its name tag references. The change doesn’t affect the second variable, which still refers to the initial value. For example:
```python
spam = 42
eggs = spam
spam = 99

spam # 99
eggs # 42
```
But lists don’t work this way, because list values are *mutable* and can change. Here is code that will make this distinction easier to understand:
```python
spam = [0, 1, 2, 3]
eggs = spam  # The reference, not the list, is being copied.

eggs[1] = 'Hello!'  # This changes the list value.

spam # [0, 'Hello!', 2, 3]
eggs  # [0, 'Hello!', 2, 3] = The eggs variable refers to the same list.
```
When you create the list , you assign a reference to it in the `spam` variable. But the next line copies only the list reference in `spam` to `eggs`, not the list value itself. There is still only one list, and `spam` and `eggs` now both refer 
to it. The reason there is only one underlying list is that the list itself was never actually copied. So, when you modify the first element of `eggs`, you’re modifying the same list that `spam` refers to.  
&nbsp;&nbsp;&nbsp;&nbsp;It becomes a bit more complicated, as lists also don’t contain a sequence of values directly, but rather a sequence of references to values.  
#### Note:
Although Python variables technically contain references to values, people often casually say that the variable contains the value. But keep these two rules in mind:
- In Python, variables never contain values. They contain only references to values.
- In Python, the = assignment operator copies only references. It never copies values.

For the most part, you don’t need to know these details, but at times, these simple rules have surprising effects, and you should understand exactly what Python is doing.

### Arguments:
References are particularly important for understanding how arguments get passed to functions. When a function is called, Python copies to the parameter variables the reference to the arguments. For mutable values like lists and dictionaries, this means the code in the function modifies the original value in place. Let's see the consequences of this fact:
```python
def eggs(some_parameter):
    some_parameter.append('Hello')
spam = [1, 2, 3]
eggs(spam)
print(spam)  # Prints [1, 2, 3, 'Hello']
```
Notice that when you call `eggs()`, a return value doesn’t assign a new value to `spam`. Instead, it directly modifies the list in place.  
&nbsp;&nbsp;&nbsp;&nbsp;Even though `spam` and `some_parameter` contain separate references, they both refer to the same list. This is why the `append('Hello')` method call inside the function affects the list even after the function call has returned.
&nbsp;&nbsp;&nbsp;&nbsp;Keep this behavior in mind. Forgetting that Python handles list and dictionary variables in this way can lead to unexpected behavior and confusing bugs.

###  The copy() and deepcopy() Functions:
Although passing around references is often the handiest way to deal with lists and dictionaries, if the function modifies the list or dictionary passed to it, you may not want these changes in the original list or dictionary value. To control this behavior, Python provides a module named `copy` that provides both the `copy()` and `deepcopy()` functions. The first of these, `copy.copy()`, can make a duplicate copy of a mutable value like a list or dictionary, not just a copy of a reference. For example:
```python
import copy

spam = ['A', 'B', 'C']

cheese = copy .copy(spam)  # Creates a duplicate copy of the list

cheese[1] = 42  # Changes cheese
spam  # ['A', 'B', 'C'] = The spam variable is unchanged.
cheese  # ['A', 42, 'C'] = The cheese variable is changed.
```
