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
