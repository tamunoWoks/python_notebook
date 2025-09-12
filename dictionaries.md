## The Dictionary Data Type
Like a list, a ***dictionary*** is a mutable collection of many values. But unlike indexes for lists, indexes for dictionaries can use many different data types, not just integers. These dictionary indexes are called ***keys***, and a key with its associated value is called a ***key-value pair***.  
In code, a dictionary is entered between curly brackets `{}`. For example:
```python
my_cat = {'size': 'fat', 'color': 'gray', 'age': 17}
```
This assigns a dictionary to the `my_cat` variable. This dictionary’s keys are `'size'`, `'color'`, and `'age'`. The values for these keys are `'fat'`, `'gray'`, and `17`, respectively. You can access these values through their keys:
```python
my_cat['size'] # 'fat'

'My cat has ' + my_cat['color'] + ' fur.' # 'My cat has gray fur.'
```
Using dictionaries, you can store multiple pieces of data about the same thing in a single variable. This `my_cat` variable contains three different strings describing my cat, and I can use it as an argument or return value in a function call, saving me from needing to create three separate variables.  
Dictionaries can still use integer values as keys, just like lists use integers for indexes, but they don’t have to start at 0 and can be any number:
```python
spam = {12345: 'Luggage Combination', 42: 'The Answer'}

spam[12345] # 'Luggage Combination'
spam[42] # 'The Answer'
spam[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 0
```
Dictionaries have keys, not indexes. In this example, while the dictionary in `spam` has integer keys `12345` and `42`, it doesn’t have an index `0` through `41` like a list would.

### Comparing Dictionaries and Lists:
Unlike lists, items in dictionaries are unordered. The first item in a list named `spam` would be `spam[0]`. But there is no “first” item in a dictionary.  
While the order of items matters for determining whether two lists are the same, you can enter the key-value pairs of a dictionary in any order. For example:
```python
spam = ['cats', 'dogs', 'moose']
bacon = ['dogs', 'moose', 'cats']

spam == bacon # False (The order of the list matters.)

eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}

>>> eggs == ham # True (The order of dictionary key-value pairs doesn't matter.)
```
The `eggs` and `ham` dictionaries are identical values even though we entered their key-value pairs in different orders. Because a dictionary isn’t ordered, it isn’t a sequence data type and can’t be sliced like a list.  

Trying to access a key that doesn’t exist in a dictionary will result in a `KeyError` error message, much like a list’s “out-of-range” `IndexError` error message. For example:
```python
spam = {'name': 'Zophie', 'age': 7}

spam['color']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    spam['color']
KeyError: 'color'
```
