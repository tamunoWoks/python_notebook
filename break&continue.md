## break Statements
There is a shortcut to getting the program execution to break out of a while loop’s clause early. If the execution reaches a `break` statement, it immediately exits the while loop’s clause. In code, a `break` statement simply contains the `break` keyword.  

Here’s a program that uses a break statement to escape the loop:
```python
while True:
    print('Please type your name.')
    name = input('>')
    if name == 'your name':
        break
print('Thank you!') 
```
The first line creates an infinite loop; it is a `while` loop whose condition is always True. (The expression True, after all, always evaluates to the value True.) After the program execution enters this loop, it will exit the loop only when a `break` statement is executed.

## continue Statements
Like `break` statements, we use `continue` statements inside loops. When the program execution reaches a `continue` statement, the program execution immediately jumps back to the start of the loop and reevaluates the loop’s condition. (This is also what happens when the execution reaches the end of the loop.)
