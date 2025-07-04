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
- You can use `break` and `continue` statements inside `for` loops as well. The `continue` statement will continue to the next value of the `for` loop’s counter, as if the program execution had reached the end of the loop and returned to the start.

### Arguments to range():
Some functions can be called with multiple arguments separated by a comma, and `range()` is one of them.  
This lets you change the integer passed to `range()` to follow any sequence of integers, including starting at a number other than zero:
```python
for i in range(12, 16):
    print(i)
```
The first argument will be where the `for` loop’s variable starts, and the second argument will be up to, but not including, the number to stop at.

- The `range()` function can also be called with three arguments. The first two arguments will be the start and stop values, and the third will be the step argument. The step is the amount by which the variable is increased after each iteration:
```python
for i in range(0, 10, 2):
    print(i)
```
So, calling range(0, 10, 2) will count from zero to eight by intervals of two.

- The `range()` function is flexible in the sequence of numbers it produces for `for` loops. For example you can even use
a negative number for the step argument to make the `for` loop count down instead of up:
```python
for i in range(5, -1, -1):
    print(i)
```
Running a `for` loop to print i with range(5, -1, -1) should print the numbers from five down to zero.
