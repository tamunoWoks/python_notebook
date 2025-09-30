## Strings and Text Editing
Text is one of the most common forms of data your programs will handle. Let’s look at some of the ways Python lets you write, print, and access strings in your code.

###  String Literals:
While string `values` are stored in the program’s memory, the string values that literally appear in our code are called `string literals`. Writing string literals in Python code seems straightforward: they begin and end with a single quotation mark, with the text of the string value in between. But how can you use quotes inside a string? Entering 'That is Alice's cat.' won’t work, because Python will think the string ends after Alice and will treat the rest (s cat.') as invalid Python code. Fortunately, there are multiple ways to write string literals.

#### Double Quotes:
String literals can begin and end with double quotes as well as with single quotes. One benefit of using double quotes is that the string can have a single quote character in it. 
```python
spam = "That is Alice's cat."
```
Because the string begins with a double quote, Python knows that the single quote is part of the string and is not marking the end of the string. However, if you need to use both single quotes and double quotes in the string, you’ll need to use escape characters.

#### Escape Characters:
An escape character lets you use characters that are otherwise impossible to put into a string literal. An escape character consists of a backslash (\) followed by the character you want to add to the string. For example, `\'` is the escape character for a single quote and `\n` is the escape character for a newline character. (Despite consisting of two characters, it is commonly referred to as a singular escape character.) You can use this syntax inside a string that begins and ends with single quotes:
```python
spam = 'Say hi to Bob\'s mother.'
```
Python knows that since the single quote in `Bob\'s` has a backslash, it is not a single quote meant to end the string value. The escape characters `\'` and `\"` let you put single quotes and double quotes inside your strings, respectively.  

**List of Escape Characters:**  
| Escape character | Prints as... |
|:-----------------|:-------------|
| \'               | Single quote |
| \"               | Double quote |
| \t               | Tab          |
| \n               | New line     |
| \\               | Backslash    |

**Example:** 
```python
print("Hello there!\nHow are you?\nI\'m doing fine.")

# Hello there!
# How are you?
# I'm doing fine.
```
Keep in mind that because the`\` backslash begins an escape character, if you want an actual backslash in your string, you must use the `\\` escape character.

#### Raw Strings:
You can place an `r` before the beginning quotation mark of a string literal to make it a raw string literal. A raw string makes it easier to enter string values that have backslashes by ignoring all escape characters. For example:
```python
print(r'The file is in C:\Users\Alice\Desktop')

# The file is in C:\Users\Alice\Desktop
```
Because this is a raw string, Python considers the backslash to be part of the string and not the start of an escape character:
```python
print('Hello...\n\n...world!')  # Without a raw string
Hello...

...world!

 print(r'Hello...\n\n...world!')  # With a raw string
 # Hello...\n\n...world!
```
Raw strings are helpful if your string values contain many backslashes, such as the strings used for Windows filepaths like `r'C:\Users\Al\Desktop'` or regular expression strings.

####  Multiline Strings:
While you can use the `\n` escape character to insert a newline into a string, it’s often easier to use multiline strings. A multiline string in Python begins and ends with either three single quotes or three double quotes. Any quotes, tabs, or newlines in between the “triple quotes” are considered part of the string. Python’s indentation rules for blocks don’t apply to lines inside a multiline string. For example:
```python
 print('''Dear Alice,

 Can you feed Eve's cat this weekend?

 Sincerely,
 Bob''')
```
The output will look like this:
```txt
Dear Alice,

Can you feed Eve's cat this weekend?

Sincerely,
Bob
```
Notice that the single quote character in `Eve's` doesn’t need to be escaped. Escaping single and double quotes is optional in multiline strings:
```python
print('Dear Alice,\n\nCan you feed Eve's cat this weekend?\n\nSincerely,\nBob')
```
This `print()` call prints identical text but doesn’t use a multiline string.

#### Multiline Comments:
While the hash character (#) marks the beginning of a comment for the rest of the line, a multiline string is often used for comments that span multiple lines:
```python
"""This is a test Python program.
Written by Al Sweigart al@inventwithpython .com

This program was designed for Python 3, not Python 2.
"""
def say_hello():
    """This function prints hello.
    It does not return anything."""
    print('Hello!')
```
The multiline string in this example is perfectly valid Python code.

### Indexes & Slices:
Strings use indexes and slices the same way lists do. You can think of the string 'Hello, world!' as a list and each character in the string as an item with a corresponding index and negative index. The space and exclamation mark are included in the character count, so 'Hello, world!' is 13 characters long, from H at index 0 to ! at index 12.
```python
greeting = 'Hello, world!'

greeting[0] # 'H'
greeting [4] # 'o'
greeting[-1] # '!'
greeting[0:5] # 'Hello'
greeting[:5] # 'Hello'
greeting[7:-1] # 'world'
greeting[7:] # 'world!'
```
If you specify an index, you’ll get the character at that position in the string. If you specify a range from one index to another, the starting index is included and the ending index is not.  

**Note:**  
Slicing a string doesn’t modify the original string. You can capture a slice from one variable in a separate variable. 
```python
greeting = 'Hello, world!'

greeting_slice = greeting[0:5]

greeting_slice # 'Hello'
greeting # 'Hello, world!'
```

### The in and not in Operators:
You can use the `in` and `not in` operators with strings just as you can with list values. An expression with two strings joined using in or not in will evaluate to a Boolean True or False. 
```python
'Hello' in 'Hello, World' # True
'Hello' in 'Hello' # True
'HELLO' in 'Hello, World' # False
'' in 'spam' # True
'cats' not in 'cats and dogs' # False
```
These expressions test whether the first string (including its capitalization) can be found within the second string.

## F-Strings
Putting strings inside other strings is a common operation in programming. So far, we’ve been using the + operator and string concatenation to do this:
```python
name = 'Al'
age = 4000

print('Hello, my name is ' + name + '. I am ' + str(age) + ' years old.') # 'Hello, my name is Al. I am 4000 years old.'
print('In ten years I will be ' + str(age + 10)') # 'In ten years I will be 4010'
```
However, this requires a lot of tedious typing. A simpler approach is to use `f-strings`, which let you place variable names or entire expressions within a string. Like the `r` prefix in raw strings, f-strings have an `f` prefix before the 
starting quotation mark. For example:
```python
name = 'Al'
age = 4000

print(f'My name is {name}. I am {age} years old.') # 'My name is Al. I am 4000 years old.'
print(f'In ten years I will be {age + 10}') # 'In ten years I will be 4010'
```
Everything between the curly brackets ({}) is interpreted as if it were passed to `str()` and concatenated with the `+` operator in the middle of the string. If you need to use literal curly bracket characters in an f-string, use two curly brackets:
```python
name = 'Zophie'
print(f'{name}') # 'Zophie'

print(f'{{name}}') # '{name}'
```
F-strings are a useful feature in Python, but the language only added them in version 3.6. In older Python code, you may need alternative techniques.

## Useful String Methods
Several string methods analyze strings or create transformed string values. 

####  Changing the Case:
- **upper()** = Returns a new string with all the letters in the original converted to uppercase.
- **lower()** = Returns a new string with all the letters in the original converted to lowercase.
- **isupper()** = Returns a Boolean `True` value if the string has at least one letter and all the letters are uppercase.
- **islower()** = Returns a Boolean `True` value if the string has at least one letter and all the letters are lowercase.

Note that these methods don’t change the string itself, but return new string values. If you want to change the original string, you have to call `upper()` or `lower()` on the string and then assign the new string to the variable that stored the original.  

The `upper()` and `lower()` methods are helpful if you need to make a case insensitive comparison. Since the `upper()` and `lower()` string methods themselves return strings, you can call string methods on those returned string values as well.

#### Checking String Characteristics:
Along with `islower()` and `isupper()`, several other string methods have names beginning with the word `is`. These methods return a Boolean value that describes the nature of the string. Here are some common `isX()` string methods:  
- **isalpha()** = Returns `True` if the string consists only of letters and isn’t blank
- **isalnum()** = Returns `True` if the string consists only of letters and numbers (alphanumerics) and isn’t blank
- **isdecimal()** = Returns `True` if the string consists only of numeric characters and isn’t blank
- **isspace()** = Returns `True` if the string consists only of spaces, tabs, and newlines and isn’t blank
- **istitle()** = Returns `True` if the string consists only of words that begin with an uppercase letter followed by only lowercase letters.

The `isX()` string methods are helpful when you need to validate user input. For example, the following program repeatedly asks users for their age and a password until they provide valid input:
```python
while True:
  print('Enter your age:')
  age = input()
  if age.isdecimal():
    break
  print('Please enter a number for your age.')

while True:
  print('Select a new password (letters and numbers only):')
  password = input()
  if password.isalnum():
    break
  print('Passwords can only have letters and numbers.')
```
In the first `while` loop, we ask the user for their age and store their input in `age`. If `age` is a valid (decimal) value, we break out of this first `while` loop and move on to the second, which asks for a password. Otherwise, we inform the user that they need to enter a number and again ask them to enter their age. In the second `while` loop, we ask for a password, store the user’s input in `password`, and break out of the loop if the input was alphanumeric. If it wasn’t, we’re not satisfied, so we tell the user the password needs to be alphanumeric and again ask them to enter a password.

#### Checking the Start or End of a String:
The `startswith()` and `endswith()` methods return `True` if the string value on which they’re called begins or ends (respectively) with the string passed to the method; otherwise, they return `False`.
```python
'Hello, world!'.startswith('Hello') # True

'Hello, world!'.endswith('world!') # True

'abc123'.startswith('abcdef') # False

'abc123'.endswith('12') # False

'Hello, world!'.startswith('Hello, world!') # True

'Hello, world!'.endswith('Hello, world!') # True
```
These methods are useful alternatives to the equals operator (==) if you need to check only whether the first or last part of the string, rather than the whole thing, is equal to another string.

#### join():
The `join()` method is useful when you have a list of strings that need to be joined together into a single string value. We call the `join()` method on a string and pass it a list of strings, and it returns the concatenation of each string in the passed-in list. For example, notice that the string on which `join()` is called is inserted between each string of the list argument.  
```python
', '.join(['cats', 'rats', 'bats']) # 'cats, rats, bats'

' '.join(['My', 'name', 'is', 'Simon']) # 'My name is Simon'

'ABC'.join(['My', 'name', 'is', 'Simon']) # 'MyABCnameABCisABCSimon'
```
Remember that we call `join()` on a string value and pass it a list value. (It’s easy to accidentally call it the other way around.)
#### split()
The `split()` method works the opposite way: we call it on a string value, and it returns a list of strings.
```python
'My name is Simon'.split() # ['My', 'name', 'is', 'Simon']
```
By default, the method splits the string 'My name is Simon' wherever it finds whitespace such as the space, tab, or newline characters. These whitespace characters aren’t included in the strings in the returned list. You can pass a delimiter string to the `split(`) method to specify a different string to split upon. For example:
```python
'MyABCnameABCisABCSimon'.split('ABC') # ['My', 'name', 'is', 'Simon']

'My name is Simon'.split('m') # ['My na', 'e is Si', 'on']
```
A common use of `split()` is to split a multiline string along the newline characters. For example:
```python
spam = '''Dear Alice,
There is a milk bottle in the fridge
that is labeled "Milk Experiment."

Please do not drink it.
Sincerely,
Bob'''

>>> spam.split('\n')
['Dear Alice,', 'There is a milk bottle in the fridge', 'that is labeled "Milk Experiment."', '', 'Please do not drink it.', 'Sincerely,', 'Bob']
```
Passing `split()` the argument `'\n'` lets us split the multiline string stored in spam along the newlines and return a list in which each item corresponds to one line of the string.

### rjust() and ljust():
The `rjust()` and `ljust()` string methods return a padded version of the string on which they’re called, with spaces inserted to justify the text. The first argument to both methods is an integer length for the justified string. For example:
```python
'Hello'.rjust(10) # '     Hello'

'Hello'.rjust(20) # '               Hello'

'Hello, World'.rjust(20) # '        Hello, World'

'Hello'.ljust(10) # 'Hello     '
```
The code `'Hello'.rjust(10)` says that we want to right-justify 'Hello' in a string of total length 10. 'Hello' is five characters, so five spaces will be added to its left, giving us a string of 10 characters with 'Hello' right-justified.  

An optional second argument to `rjust()` and `ljust()` will specify a fill character other than a space character.
```python
'Hello'.rjust(20, '*') # '***************Hello'

'Hello'.ljust(20, '-') # 'Hello---------------'
```
#### center():
The `center()` string method works like `ljust()` and `rjust()` but centers the text, rather than justifying it to the left or right.
```python
'Hello'.center(20) # ' Hello '

'Hello'.center(20, '=') # '=======Hello========'
```
