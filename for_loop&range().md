## for Loops and the range() Function
if you want to execute a block of code only a certain number of times? You can do this with a `for` loop statement and the
`range()` function.  

In code, a `for` statement looks something like for i in range(5): and includes the following:  
- The `for` keyword  
- A variable name  
- The `in` keyword  
- A call to the `range()` function with up to three integers passed to it  
- A colon  
- Starting on the next line, an indented block of code (called the for clause or for block)  

Let’s create a program called to see a for loop in action:
```python
print('Hello!')
for i in range(5):
    print('On this iteration, i is set to ' + str(i))
print('Goodbye!')
```
You can use `break` and `continue` statements inside `for` loops as well. The `continue` statement will continue to the next value of the `for` loop’s counter, as if the program execution had reached the end of the loop and returned to the start.

### Arguments to range():
Some functions can be called with multiple arguments separated by a comma, and `range()` is one of them. This lets you change the integer passed to `range()` to follow any sequence of integers, including starting at a number other than zero:
```python

```
