# Debugging
Debugging in programming is the process of finding and fixing errors (bugs) in your code so that it runs correctly and produces the expected results.  

A bug can be anything that makes your program behave unexpectedly such as syntax mistakes, logic errors, or runtime crashes. Debugging is basically detective work: you trace through the code, test assumptions, and figure out why the program isn’t working as intended.

### Key steps in debugging:
1. **Identify the bug:**
    - Notice an error message, unexpected output, or crash.
    - Reproduce the problem consistently.
2. **Isolate the cause:**
    - Narrow down the part of the code causing the issue.
    - Use tools like print statements, breakpoints, or debuggers to track the program flow.
3. **Understand the error:**
    - Check what the code was supposed to do vs. what it’s actually doing.
    - Look for mistakes in logic, data types, conditions, or external dependencies.
4. **Fix the bug:**
    - Correct the faulty code or logic.
    - Ensure the fix doesn’t break other parts of the program.
5. **Test thoroughly:**
    - Run tests to confirm the bug is gone.
    - Check edge cases to ensure stability.

> Your computer will do only what you tell it to do; it won’t read your mind and do what you intended it to do. Even professional programmers create bugs all the time, so don’t feel discouraged if your program has a problem. Fortunately, a few tools and techniques can identify exactly what your code is doing and where it’s going wrong.

### Common debugging techniques:
- **Print debugging** – inserting print/logging statements to track variable values.
- **Interactive debugger** – stepping through code line by line with tools like `pdb` in Python, or IDE debuggers.
- **Rubber duck debugging** – explaining your code out loud (often reveals mistakes).
- **Unit testing** – writing tests to catch bugs early.

> You can also make your programs raise custom exceptions to indicate errors. Two features that can help you detect bugs early are logging and assertions. In general, the earlier you catch bugs, the easier they will be to fix.

## Raising Exceptions
Python raises an exception whenever it tries to execute invalid code. We can handle Python exceptions with `try` and `except` statements so that our program could recover from exceptions we anticipated. But we can also raise our own exceptions in our code.  
&nbsp;&nbsp;&nbsp;&nbsp;Raising an exception is a way of saying, “Stop running this code, and move the program execution to the except statement.”  

We raise exceptions with a `raise` statement, which consists of the following:
- The `raise` keyword
- A call to the `Exception()` function
- A string with a helpful error message passed to the `Exception()` function.

If no `try` and `except` statements cover the `raise` statement that raised the exception, the program simply crashes and displays the exception’s error message.  
&nbsp;&nbsp;&nbsp;&nbsp;Often, it’s the code that calls the function containing a `raise` statement, rather than the function itself, that knows how to handle an exception. That means you’ll commonly see a `raise` statement inside a function, and the `try` and `except` statements in the code calling the function.  

**Example:**
```python
def box_print(symbol, width, height):
    if len(symbol) != 1:
        raise Exception('Symbol must be a single character string.')
    if width <= 2:
        raise Exception('Width must be greater than 2.')
    if height <= 2:
        raise Exception('Height must be greater than 2.')

    print(symbol * width)
    for i in range(height - 2):
        print(symbol + (' ' * (width - 2)) + symbol)
    print(symbol * width)

try:
    box_print('*', 4, 4)
    box_print('O', 20, 5)
    box_print('x', 1, 3)
    box_print('ZZ', 3, 3)
except Exception as err:
    print('An exception happened: ' + str(err))
try:
    box_print('ZZ', 3, 3)
except Exception as err:
    print('An exception happened: ' + str(err))
```
&nbsp;&nbsp;&nbsp;&nbsp;Here, we’ve defined a `box_print()` function that takes a character, a width, and a height, and uses the character to make a little picture of a box with that width and height, printed to the screen.  
&nbsp;&nbsp;&nbsp;&nbsp;Say we want the function to accept a single character only, and we expect the width and height to be greater than 2. We add `if` statements to raise exceptions if these requirements aren’t satisfied. Later, when we call `box _print()` with various arguments, our `try/except` will handle invalid arguments.  
&nbsp;&nbsp;&nbsp;&nbsp;This program uses the `except Exception` as `err` form of the `except` statement. If an `Exception` object is returned from `box_print()`, this `except` statement will store it in a variable named `err`. We can then convert the `Exception` object to a string by passing it to `str()` to produce a userfriendly error message.  

## Assertions
An assertion is a check to make sure your code isn’t doing something obviously wrong. We perform these checks with `assert` statements. If the check fails, the code raises an `AssertionError` exception.  

An `assert` statement consists of the following:
- The assert keyword
- A condition (that is, an expression that evaluates to True or False)
- A comma
- A string to display when the condition is False.

In plain English, an `assert` statement says, “I assert that the condition holds true, and if not, there is a bug somewhere, so immediately stop the program."

**Example:**
```python
>>> ages = [26, 57, 92, 54, 22, 15, 17, 80, 47, 73]
>>> ages.sort()
>>> ages
[15, 17, 22, 26, 47, 54, 57, 73, 80, 92]
>>> assert ages[0] <= ages[-1] # Assert that the first age is <= the last age.
```
The `assert` statement here asserts that the first item in ages should be less than or equal to the last one. This is a sanity check; if the code in `sort()` is bug-free and did its job, then the assertion would be true. Because the ages[0] <= ages[-1] expression evaluates to `True`, the `assert` statement does nothing.  
&nbsp;&nbsp;&nbsp;&nbsp;However, let’s pretend we had a bug in our code. Say we accidentally called the `reverse()` list method instead of the `sort()` list method. When we enter the following in the interactive shell, the `assert` statement raises an `AssertionError`:
```python
>>> ages = [26, 57, 92, 54, 22, 15, 17, 80, 47, 73]
>>> ages.sort()
>>> ages
[15, 17, 22, 26, 47, 54, 57, 73, 80, 92]
>>> assert ages[0] <= ages[-1] # Assert that the first age is <= the last age.
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
AssertionError
```
### Tip:
Unlike `exceptions`, your code should not handle `assert` statements with `try` and `except`; if an `assert` fails, your program should crash. By “failing fast” like this, you shorten the time between the original cause of the bug and the moment you first notice it, reducing the amount of code you’ll have to check before finding the bug’s cause.  
&nbsp;&nbsp;&nbsp;&nbsp;Assertions are for programmer errors, not user errors. Assertions should fail only while the program is under development; a user should never see an assertion error in a finished program.  
&nbsp;&nbsp;&nbsp;&nbsp;For errors that your program can encounter as a normal part of its operation (such as a file not being found or the user entering invalid data), raise an exception instead of detecting it with an assert statement.

## Logging
When you put a `print()` function in your code to output some variable’s value while your program is running, you’ve used a form of logging to debug your code.Logging is a great way to understand what’s happening in your program and in what order it’s happening.  
&nbsp;&nbsp;&nbsp;&nbsp;Python’s logging module makes it easy to create a record of custom messages that you write. These log messages will describe when the program execution has reached the logging function call and will list any variables you’ve specified at that point in time, providing a trail of breadcrumbs that can help you figure out when things started to go wrong. On the other hand, a missing log message indicates a part of the code was skipped and never executed.  
### The `logging` Module:
To enable the `logging` module to display log messages on your screen as your program runs, you will need the following to the top of your program:
```python
import logging
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s -  %(levelname)s -  %(message)s'
)
logging.debug('Start of program')
```
The `logging` module’s `basicConfig()` function lets you specify what details you want to see and how you want those details displayed.
### Logfiles:
Instead of displaying the log messages to the screen, you can write them to a text file. The logging.basicConfig() function takes a filename named parameter, like so:
```python
import logging
logging.basicConfig(filename='myProgramLog.txt', level=logging.DEBUG,
format=' %(asctime)s - %(levelname)s - %(message)s')
```
This code will save the log messages to myProgramLog.txt.
&nbsp;&nbsp;&nbsp;&nbsp;While logging messages are helpful, they can clutter your screen and make it hard to read the program’s output. Writing the logging messages to a file will keep your screen clear and enable you to read the messages after running the program. You can open this text file in any text editor, such as Notepad or TextEdit.

## Setting Breakpoints
Setting a breakpoint on a specific line of code forces the debugger to pause whenever the program execution reaches that line.
#### Example:
```python
import random
heads = 0
for i in range(1, 1001):
    if random.randint(0, 1) == 1:
        heads = heads + 1
    if i == 500:
        print('Halfway done!')
print('Heads came up ' + str(heads) + ' times.')
```
