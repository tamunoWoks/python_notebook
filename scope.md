## Local and Global Scopes
Only code within a called function can access the parameters and variables assigned in that function. These variables are said to exist in that function’s ***local scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; By contrast, code anywhere in a program can access variables that are assigned outside all functions. These variables are said to exist in the ***global scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; A variable that exists in a local scope is called a ***local variable***, while a variable that exists in a global scope is called a ***global variable***. A variable must be one or the other; it cannot be both local and global.  
&nbsp;&nbsp;&nbsp;&nbsp; Think of a `scope` as a container for variables. There is only one global scope, created when your program begins. When your program terminates, it destroys the global scope, and all of its variables get forgotten.  
&nbsp;&nbsp;&nbsp;&nbsp; A new local scope gets created whenever a program calls a function. Any variables assigned in the function exist within the function’s local scope. When the function returns, the local scope gets destroyed, along with these variables.

### Scope Rules:
When working with local and global variables, keep the following rules in mind:
- Code that is in the global scope, outside all functions, can’t use local variables.
- Code that is in one function’s local scope can’t use variables in any other local scope.
- Code in a local scope can access global variables.
- You can use the same name for different variables if they are in different scopes. That is, there can be a local variable named spam and a global variable also named spam.

#### NOTE:
- Python uses scoping because it enables a function to modify its variables, yet interact with the rest of the program through its parameters and its return value only.
- If your program contained nothing but global variables, and contained a bug caused by a variable set to a bad value, you might struggle to track down the location of this bad value. But if the bug occurred in a local variable, you can restrict your search to a single function.
- While using global variables in small programs is fine, it’s a bad habit to rely on global variables as your programs get larger and larger.

#### Examples:
1. **Code That Is in the Global Scope Can’t Use Local Variables:**
```python
def spam():
  eggs = 'sss'
spam()
print(eggs)
```
**Output:**  
```txt
Traceback (most recent call last):
  File "C:/test1.py", line 4, in <module>
    print(eggs)
NameError: name 'eggs' is not defined
```
The error happens because the eggs variable exists only in the local scope created when `spam()` is called. This is because when the program execution is in the global scope, no local scopes exist, so there can’t be any local variables. This is why you can only reference global variables in the global scope.  

2. **Code That Is in a Local Scope Can’t Use Variables in Other Local Scopes:**
Python creates a new local scope whenever a program calls a function, even when the function is called from another function.
```python
def spam():
  eggs = 'SPAMSPAM'
  bacon()
  print(eggs) # prints 'SPAMSPAM'

def bacon():
  ham = 'hamham'
  eggs = 'BACONBACON'

spam()
```
When the program starts, it calls the `spam()` function, creating a local scope. The `spam()` function sets the local variable eggs to 'SPAMSPAM', then calls the `bacon()` function, creating a second local scope.  
&nbsp;&nbsp;&nbsp;&nbsp; Multiple local scopes can exist at the same time. In this new local scope, the local variable ham gets set to 'hamham', and a local variable eggs (which differs from the one in `spam()`’s local scope) gets created and set to 'BACONBACON'. At this point, the program has two local variables named eggs that exist simultaneously: one that is local to `spam()` and one that is local to `bacon()`.  
&nbsp;&nbsp;&nbsp;&nbsp; When `bacon()` returns, Python destroys the local scope for that call, including its eggs variable. The program execution continues in the `spam()` function, printing the value of eggs. Because the local scope for the call  to `spam(`) still exists, the only eggs variable is the `spam()` function’s eggs variable, which was set to 'SPAMSPAM'. This is what the program prints as output.

3. **Code That Is in a Local Scope Can Use Global Variables:**
```python
def spam():
  print(eggs) # prints 'GLOBALGLOBAL'
eggs = 'GLOBALGLOBAL'
spam()
print(eggs)
```
Because the `spam()` function has no parameter named eggs, nor any code that assigns eggs a value, Python considers the function’s use of eggs a reference to the global variable eggs. This is why the program prints 'GLOBALGLOBAL' when it’s run.
