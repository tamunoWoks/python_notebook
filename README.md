# Python tutorial
This repository is strictly for learning key python syntax.

Here are the concepts documented:
## String slicing and striding
String slicing in Python is a powerful feature that allows you to extract a portion of a string (substring) by specifying a start index, an end index, and an optional step size. The syntax for string slicing is:  
```python
string[start:end:step]
```
#### Parameters:
- start: The starting index of the slice (inclusive). If omitted, it defaults to 0 (the beginning of the string).
- end: The ending index of the slice (exclusive). If omitted, it defaults to the length of the string (the end of the string).
- step: The step size (optional). It determines the stride between indices. If omitted, it defaults to 1.

#### Key Points:
- Python uses zero-based indexing, meaning the first character of the string has an index of 0.
- The slice includes the character at the start index but excludes the character at the end index.
- Negative indices can be used to count from the end of the string. For example, -1 refers to the last character, -2 to the second last, and so on.
- If the step is negative, the slice is taken in reverse order.
