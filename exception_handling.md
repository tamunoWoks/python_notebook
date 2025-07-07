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
This is the output you get when you run the previous code:
```text
21.0
3.5
Traceback (most recent call last):
  File "C:/zeroDivide.py", line 6, in <module>
    print(spam(0))
  File "C:/zeroDivide.py", line 2, in spam
    return 42 / divide_by
ZeroDivisionError: division by zero
```
```python

```
