## Local and Global Scopes
Only code within a called function can access the parameters and variables assigned in that function. These variables are said to exist in that function’s ***local scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; By contrast, code anywhere in a program can access variables that are assigned outside all functions. These variables are said to exist in the ***global scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; A variable that exists in a local scope is called a ***local variable***, while a variable that exists in a global scope is called a ***global variable***. A variable must be one or the other; it cannot be both local and global.  
&nbsp;&nbsp;&nbsp;&nbsp; Think of a `scope` as a container for variables. There is only one global scope, created when your program begins. When your program terminates, it destroys the global scope, and all of its variables get forgotten.  
&nbsp;&nbsp;&nbsp;&nbsp; A new local scope gets created whenever a program calls a function. Any variables assigned in the function exist within the function’s local scope. When the function returns, the local scope gets destroyed, along with these variables.
#### NOTE:
- Python uses scoping because it enables a function to modify its variables, yet interact with the rest of the program through its parameters and its return value only.
- If your program contained nothing but global variables, and contained a bug caused by a variable set to a bad value, you might struggle to track down the location of this bad value. But if the bug occurred in a local variable, you can restrict your search to a single function.
- While using global variables in small programs is fine, it’s a bad habit to rely on global variables as your programs get larger and larger.
