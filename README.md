# Python tutorial
This repository is strictly for learning key python syntax.

Here are the concepts documented:
[String Slicing and Striding](#string_slicing_and_striding)

## String slicing and striding
- String slicing in Python is a powerful feature that allows you to extract a portion of a string (substring) by specifying a start index, an end index, and an optional step size.  
- String striding in Python refers to the process of accessing characters in a string at regular intervals by specifying a step value in the slicing syntax. It allows you to skip characters or traverse the string in a specific pattern.  
The syntax for string slicing & striding is:  
```python
string[start:end:step]
```
#### Parameters:
- start: The starting index of the slice (inclusive). If omitted, it defaults to 0 (the beginning of the string).
- end: The ending index of the slice (exclusive). If omitted, it defaults to the length of the string (the end of the string).
- step: It determines the stride between indices. If omitted, it defaults to 1. The step size is optional for slicing but necessary for striding.

#### Key Points:
- Python uses zero-based indexing, meaning the first character of the string has an index of 0.
- The slice includes the character at the start index but excludes the character at the end index.
- Negative indices can be used to count from the end of the string. For example, -1 refers to the last character, -2 to the second last, and so on.
- If the step is negative, the slice is taken in reverse order.

#### Key Points to Remember
- Python uses zero-based indexing, meaning the first character of the string has an index of 0.
- The slice includes the character at the start index but excludes the character at the end index.
- The step value determines the direction and interval of traversal.
- A positive step moves from left to right.
- A negative step moves from right to left.
- If the step is 1, the string is traversed normally (no skipping).
- If the step is greater than 1, characters are skipped.
- If the step is -1, the string is reversed

#### Common Use Cases:
- Extracting substrings.
- Extracting alternate characters
- Reversing strings.
- Skipping characters at regular intervals.
- Creating patterns.
