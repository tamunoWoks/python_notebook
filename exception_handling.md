## Exception Handling
Getting an error, or exception, in your Python program means the entire program will crash. We want the program to detect errors, handle them, and then continue to run.  

For example, consider the following program, which has a divide-by-zero error:
```python
def spam(divide_by):
  return 42 / divide_by

print(spam(2))
print(spam(12))
print(spam(0))
print(spam(1))
```
```python

```
