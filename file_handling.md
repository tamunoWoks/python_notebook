## File Handling
File handling in Python allows you to work with files on your computer. You can read from and write to files, which is useful for storing and retrieving data. Python provides built-in functions and methods to handle files efficiently.
#### Opening a File
To work with a file, you first need to open it using the open() function.
```python
file = open("filename.txt", "mode")
```
- filename.txt: The name of the file (include the path if necessary)
- mode: Specifies the purpose of opening the file:
  - "r": Read (default mode). Opens the file for reading.
  - "w": Write. Opens the file for writing (creates a new file or overwrites an existing file).
  - "a": Append. Opens the file for appending data (does not overwrite existing data).
  - "x": Exclusive creation. Creates a new file but raises an error if the file already exists.
  - "b": Binary mode (e.g., "rb" or "wb" for reading/writing binary files).
  - "t": Text mode (default).
  - "+": Read and write (e.g., "r+" or "w+").
#### File Methods
Here are some commonly used file methods:
- read(size): Reads a specified number of bytes (or the entire file if no size is given).
- readline(): Reads one line from the file.
- readlines(): Reads all lines into a list.
- write(string): Writes a string to the file.
- writelines(list): Writes a list of strings to the file.
- seek(offset): Moves the file pointer to a specific location.
- tell(): Returns the current position of the file pointer.
- close(): Closes the file.  

Sample code: [File Handling](https://github.com/tamunoWoks/python_notebook/blob/main/file_handling.ipynb)
