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
