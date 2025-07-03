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
- The first line creates an infinite loop; it is a `while` loop whose condition is always True. (The expression True, after all, always evaluates to the value True.)
- After the program execution enters this loop, it will exit the loop only when a `break` statement is executed.

#### When to Use:
- To terminate the loop immediately when a condition is met (e.g., correct guess, invalid input, target found).
- Works in both `for` and `while` loops.

#### NOTE:
- **Avoid nested loops confusion:** `break` only exits the innermost loop. Use flags or functions for nested cases.
- Overusing break can make code harder to debug. Prefer modifying loop conditions when possible, eg.:
```python
# Instead of:
while True:
    if condition:
        break
# Consider:
while not condition:
    ...
```

## continue Statements
Like `break` statements, we use `continue` statements inside loops. When the program execution reaches a `continue` statement, the program execution immediately jumps back to the start of the loop and reevaluates the loop’s condition. (This is also what happens when the execution reaches the end of the loop.)  

Let’s use continue to write a program that asks for a name and password;  
```python
while True:
    print('Who are you?')
    name = input('>')
    if name != 'Joe':
      continue
    print('Hello, Joe. What is the password? (It is a fish.)')
    password = input('>')
    if password == 'swordfish':
        break
print('Access granted.')
```
- If the user enters any name besides Joe, the `continue` statement causes the program execution to jump back to the start of the loop.
- When the program reevaluates the condition, the execution will always enter the loop, because the condition is simply the value True.
- Once the user makes it past that `if` statement, they are asked for a password. If the password entered is swordfish, the `break` statement is run, and the execution jumps out of the `while` loop to print Access granted. 
- Otherwise, the execution continues to the end of the `while` loop, where it then jumps back to the start of the loop.

#### When to Use:
- To skip specific iterations but keep the loop running (e.g., filtering values, avoiding edge cases).

### Tips:
- `continue` can be used for filtering, eg.:
```python
for num in range(10):
    if num % 2 == 0:
        continue  # Skip even numbers
    print(num)    # Prints odds: 1, 3, 5, 7, 9
```
- **Place it early:** Put continue at the start of the loop to avoid unnecessary computations.
- Forgetting to update variables before continue accidentally creates infinite loops.
