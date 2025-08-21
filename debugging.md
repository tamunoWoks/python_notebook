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
• The `raise` keyword
• A call to the `Exception()` function
• A string with a helpful error message passed to the `Exception()` function
