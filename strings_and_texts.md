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
