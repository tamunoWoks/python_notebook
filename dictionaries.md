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
Though dictionaries aren’t ordered, the fact that you can use arbitrary values as keys allows you to organize your data in powerful ways. Say you wanted your program to store data about your friends’ birthdays. You can use a dictionary with the names as keys and the birthdays as values.
```python
birthdays = {'Alice': 'Apr 1', 'Bob': 'Dec 12', 'Carol': 'Mar 4'}

while True:
  print('Enter a name: (blank to quit)')
  name = input()
  if name == '':
    break

  if name in birthdays:
    print(birthdays[name] + ' is the birthday of ' + name)
  else:
    print('I do not have birthday information for ' + name)
    print('What is their birthday?')
    bday = input()
    birthdays[name] = bday
    print('Birthday database updated.')
```
The code creates an initial dictionary and stores it in birthdays. You can see if the entered name exists as a key in the dictionary with the in keyword , just as you did for lists. If the name is in the dictionary, you access the associated value using square brackets; if not, you can add it using the same square bracket syntax combined with the assignment operator.  
Of course, all the data you enter in this program is forgotten when the program terminates.

### Returning Keys and Values:
Three dictionary methods will return list-like values of the dictionary’s keys, values, or both keys and values: `keys()`, `values()`, and `items()`. The values returned by these methods aren’t true lists: they can’t be modified and don’t have an `append(`) method. But these data types (dict_keys, dict_values, and dict_items, respectively) can be used in for loops. Let's see how these methods work:
```python
spam = {'color': 'red', 'age': 42}

for v in spam.values():
  print(v)

# red
# 42
```
Here, a `for` loop iterates over each of the values in the spam dictionary. A for loop can also iterate over the keys or both the keys and values:
```python
for k in spam.keys():
  print(k)

# color
# age

'color' in spam.keys() # True
'age' not in spam.keys() # False
'red' in spam.values() # True

for i in spam.items():
  print(i)

# ('color', 'red')
# ('age', 42)
```
When you use the `keys()`, `values()`, and `items()` methods, a `for` loop can iterate over the keys, values, or key-value pairs in a dictionary, respectively, and you can use the `in` and `not in` operators to determine if a value exists as a key or value in the dictionary. Notice that the values in the `dict_items` value returned by the `items()` method are tuples of the key and value.  

You can also use the `in` and `not in` operators with the dictionary value itself to check for the existence of a key. This is equivalent to using these operators with the `keys()` method:
```python
'color' in spam # True
'color' in spam.keys() # True
```
If you want to get an actual list from one of these methods, pass its listlike return value to the `list()` function:
```python
spam = {'color': 'red', 'age': 42}

spam.keys() # Returns a list-like dict_keys value
# dict_keys(['color', 'age'])

list(spam.keys()) # Returns an actual list value
# ['color', 'age']
```
The `list(spam.keys())` line takes the dict_keys value returned from `keys()` and passes it to `list()`, which then returns a list value of `['color', 'age']`.  
You can also use the multiple assignment trick in a `for` loop to assign the key and value to separate variables. For example:
```python
spam = {'color': 'red', 'age': 42}

for k, v in spam.items():
  print('Key: ' + str(k) + ' Value: ' + str(v))

# Key: color Value: red
# Key: age Value: 42
```
While you can use many values for keys, you cannot use a list or dictionary as the key in a dictionary. These data types are ***unhashable***. If you need a list for a dictionary key, use a tuple instead.

### Checking If a Key Exists:
Checking whether a key exists in a dictionary before accessing that key’s value can be tedious. Fortunately, dictionaries have a `get()` method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key doesn’t exist. For example:
```python
picnic_items = {'apples': 5, 'cups': 2}

'I am bringing ' + str(picnic_items.get('cups', 0)) + ' cups.'
# 'I am bringing 2 cups.'

'I am bringing ' + str(picnic_items.get('eggs', 0)) + ' eggs.'
# 'I am bringing 0 eggs.'
```
Because there is no 'eggs' key in the picnic_items dictionary, the get() method returns the default value `0`. Without using get(), the code would have caused an error message, such as in the following example:
```python
picnic_items = {'apples': 5, 'cups': 2}

'I am bringing ' + str(picnic_items['eggs']) + ' eggs.'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    'I am bringing ' + str(picnic_items['eggs']) + ' eggs.'
KeyError: 'eggs'
```
Checking for the existence of a key before accessing the value for that key can prevent your programs from crashing with an error message.

### Setting Default Values:
You’ll often have to set a value in a dictionary for a certain key only if that key doesn’t already have a value. Your code might look something like this:
```python
spam = {'name': 'Pooka', 'age': 5}

if 'color' not in spam:
  spam['color'] = 'black'

spam # {'name': 'Pooka', 'age': 5, 'color': 'black'}
```
The `setdefault()` method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key doesn’t exist. If the key does exist, the `setdefault()` method returns the key’s value. For example:
```python
spam = {'name': 'Pooka', 'age': 5}

spam.setdefault('color', 'black') # Sets 'color' key to 'black'
# 'black'

spam # {'name': 'Pooka', 'age': 5, 'color': 'black'}

spam.setdefault('color', 'white') # Does nothing
# 'black'

spam # {'name': 'Pooka', 'age': 5, 'color': 'black'}
```

## Nested Dictionaries and Lists
As you model more complicated things, you may find you need dictionaries and lists that contain other dictionaries and lists. Lists are useful for holding an ordered series of values, and dictionaries are useful for associating keys with values.  
**Example:**  
Let's write a program that uses a dictionary to contain dictionaries of items guests are bringing to a picnic.
```python

```
