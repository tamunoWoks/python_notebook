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

In a slice, the first integer is the index where the slice starts. The second integer is the index where the slice ends.  
The list created from a slice will go up to, but will not include, the value at the second index. For example:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[0:4] # ['cat', 'bat', 'rat', 'elephant']
spam[1:3] # ['bat', 'rat']
spam[0:-1] # ['cat', 'bat', 'rat']
```
#### Note
As a shortcut, you can leave out one or both of the indexes on either side of the colon in the slice:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[:2] # ['cat', 'bat']
spam[1:] # ['bat', 'rat', 'elephant']
spam[:] # ['cat', 'bat', 'rat', 'elephant']
```
Leaving out the first index is the same as using `0`, or the beginning of the list.  
Leaving out the second index is the same as using the length of the list, which will slice to the end of the list.

### The len() Function:
The len() function will return the number of values in a list value passed to it. For example:
```python
spam = ['cat', 'dog', 'moose']

len(spam) # 3
```
This behavior is similar to how the function counts the number of characters in a string value.

### Value Updates:
Normally, a variable name goes on the left side of an assignment statement, as in spam = 42. However, you can also use an index of a list to change the value at that index:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

spam[1] = 'aardvark' # spam = ['cat', 'aardvark', 'rat', 'elephant']
spam[2] = spam[1] # spam = ['cat', 'aardvark', 'aardvark', 'elephant']
spam[-1] = 12345 # spam = ['cat', 'aardvark', 'aardvark', 12345]
```

### Concatenation and Replication:
You can concatenate and replicate lists with the `+` and `*` operators, just like strings:
```python
[1, 2, 3] + ['A', 'B', 'C'] # [1, 2, 3, 'A', 'B', 'C']

['X', 'Y', 'Z'] * 3 # ['X', 'Y', 'Z', 'X', 'Y', 'Z', 'X', 'Y', 'Z']

spam = [1, 2, 3]
spam = spam + ['A', 'B', 'C'] # [1, 2, 3, 'A', 'B', 'C']
```
The `+` operator combines two lists to create a new list value, and the `*` operator combines a list and an integer value to replicate the list.

### del Statements:
The `del` statement will delete values at an index in a list. All of the values in the list after the deleted value will be moved up one index. For example:
```python
spam = ['cat', 'bat', 'rat', 'elephant']

del spam[2] # spam = ['cat', 'bat', 'elephant']
del spam[2] # spam = ['cat', 'bat']
```
The `del` statement can also operate on a simple variable to delete it, as if it were an “unassignment” statement. If you try to use the variable after deleting it, you’ll get a `NameError` error because the variable no longer exists.  
In practice, you almost never need to delete simple variables, however, and the `del` statement is most useful for deleting values from lists.

## Working with Lists
When you first begin writing programs, you may be tempted to create many individual variables to store a group of similar values. It turns out that this is a bad way to write code. For one thing, if the number of values changes , your program
will never be able to store more cats than you have variables.  
&nbsp;&nbsp;&nbsp;&nbsp;Instead of using multiple, repetitive variables, you can use a single variable that contains a list value. The benefit of using a list is that your data is now in a structure, so your program can process the data much more flexibly than it could with several repetitive variables.

### `for` loops and Lists:
Technically, a `for` loop repeats the code block once for each item in a list value. A common Python technique is to use `range(len(some_list))` with a `for` loop to iterate over the indexes of a list. For example:
```python
supplies = ['pens', 'staplers', 'flamethrowers', 'binders']

for i in range(len(supplies)):
  print('Index ' + str(i) + ' in supplies is: ' + supplies[i])

# Index 0 in supplies is: pens
# Index 1 in supplies is: staplers
# Index 2 in supplies is: flamethrowers
# Index 3 in supplies is: binders
```
Using `range(len(supplies))` is handy because the code in the loop can access the index (as the variable `i`) and the value at that index (as `supplies[i]`). Best of all, `range(len(supplies))` will iterate through all the indexes of supplies, no matter how many items the list contains.

### The `in` and `not in` Operators:
You can determine whether a value is or isn’t in a list with the `in` and `not in` operators. Like other operators, `in` and `not in` occur in expressions and connect two values: a value to look for in a list and the list where it may be found. These expressions will evaluate to a Boolean value. For example:
```python
'howdy' in ['hello', 'hi', 'howdy', 'heyas'] # True

spam = ['hello', 'hi', 'howdy', 'heyas']
'cat' in spam # False
'howdy' not in spam # False
'cat' not in spam # True
```
The following program lets the user enter a pet name and then checks whether the name is in a list of pets.
```python
my_pets = ['Zophie', 'Pooka', 'Fat-tail']
print('Enter a pet name:')
name = input()
if name not in my_pets:
  print('I do not have a pet named ' + name)
else:
  print(name + ' is my pet.')
```
The output may look something like this:
```txt
Enter a pet name:
Footfoot
I do not have a pet named Footfoot
```
> Keep in mind that the `not in` operator is distinct from the Boolean `not` operator.

### The Multiple Assignment Trick:
The multiple assignment trick (technically called `tuple unpacking`) is a shortcut that lets you assign multiple variables with the values in a list in one line of code. So, instead of doing this:
```python
cat = ['fat', 'gray', 'loud']
size = cat[0]
color = cat[1]
disposition = cat[2]
```
you could enter this line of code:
```python
cat = ['fat', 'gray', 'loud']
size, color, disposition = cat
```
The number of variables and the length of the list must be exactly equal, or Python will give you a ValueError:
```python
cat = ['fat', 'gray', 'loud']
size, color, disposition, name = cat

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    size, color, disposition, name = cat
ValueError: not enough values to unpack (expected 4, got 3)
```
### List Item Enumeration:
Instead of using the `range(len(some_list))` technique with a `for loop` to obtain the integer index of the items in the list, you can call the `enumerate()` function.  
&nbsp;&nbsp;&nbsp;&nbsp;On each iteration of the loop, `enumerate()` will return two values: the `index` of the item in the list, and the `item` in the list itself.  
&nbsp;&nbsp;&nbsp;&nbsp;For example, this code is equivalent to the code in “Using `for` Loops with Lists”:
```python
supplies = ['pens', 'staplers', 'flamethrowers', 'binders']
for index, item in enumerate(supplies):
  print('Index ' + str(index) + ' in supplies is: ' + item)

# Index 0 in supplies is: pens
# Index 1 in supplies is: staplers
# Index 2 in supplies is: flamethrowers
# Index 3 in supplies is: binders
```
The `enumerate()` function is useful if you need both the `item` and the item’s `index` in the loop’s block.

### Random Selection and Ordering:
The `random` module has a couple of functions that accept lists for arguments. 

#### `random.choice()`:
The `random.choice()` function will return a randomly selected item from the list. For example:
```python
import random

pets = ['Dog', 'Cat', 'Moose']

random.choice(pets) # 'Moose'
random.choice(pets) # 'Cat'
random.choice(pets) # 'Cat'
random.choice(pets) # 'Dog'
```
You can consider `random.choice(some_list)` to be a shorter form of `someList[random.randint(0, len(some_list) – 1]`.

#### `random.shuffle()`:
The `random.shuffle()` function will reorder the items in a list in place. For example:
```python
import random

people = ['Alice', 'Bob', 'Carol', 'David']

random.shuffle(people) # people = ['Carol', 'David', 'Alice', 'Bob']
random.shuffle(people) # people = ['Alice', 'David', 'Bob', 'Carol']
```
This function modifies the list in place, rather than returning a new list.

## Augmented Assignment Operators
The `+` and `*` operators that work with strings also work with lists, so let’s take a short detour to learn about augmented assignment operators.
&nbsp;&nbsp;&nbsp;&nbsp;When assigning a value to a variable, you’ll frequently use the variable itself. For example, after assigning `42` to the variable `spam`, you would increase the value in `spam` by `1` with the following code:
```python
spam = 42
spam = spam + 1 # spam = 43
```
As a shortcut, you can use the augmented assignment operator `+=` (which is the regular operator followed by one equal sign) to do the same thing:
```python
spam = 42
spam += 1 # spam = 43
```
There are augmented assignment operators for the `+`, `-`, `*`, `/`, and `% operators, described in the table below:  

| Augmented assignment statement | Equivalent assignment statement |
|:-------------------------------|:--------------------------------|
| spam += 1                      | spam = spam + 1                 |
| spam -= 1                      | spam = spam - 1                 |
| spam *= 1                      | spam = spam * 1                 |
| spam /= 1                      | spam = spam / 1                 |
| spam %= 1                      | spam = spam % 1                 |

#### Note:
The `+=` operator can also do string and list concatenation and the `*=` operator can do string and list replication. For example:
```python
spam = 'Hello,'

spam += ' world!' # spam = 'Hello, world!'

bacon = ['Zophie']
pie = ['Scoobie']

bacon *= 3 # bacon = ['Zophie', 'Zophie', 'Zophie']
bacon += pie # bacon = ['Zophie', 'Scoobie']
```

## Methods
A *method* is the same thing as a function, except it is *called* on a value. For example, if a list value were stored in `spam`, you would call the `index()` list method on that list like so: s`pam .index('hello')`.  
&nbsp;&nbsp;&nbsp;&nbsp;The method part comes after the value, separated by a period.
