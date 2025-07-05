## Local and Global Scopes
Only code within a called function can access the parameters and variables assigned in that function. These variables are said to exist in that function’s ***local scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; By contrast, code anywhere in a program can access variables that are assigned outside all functions. These variables are said to exist in the ***global scope***.  
&nbsp;&nbsp;&nbsp;&nbsp; A variable that exists in a local scope is called a ***local variable***, while a variable that exists in a global scope is called a ***global variable***. A variable must be one or the other; it cannot be both local and global.  
&nbsp;&nbsp;&nbsp;&nbsp; Think of a `scope` as a container for variables. There is only one global scope, created when your program begins. When your program terminates, it destroys the global scope, and all of its variables get forgotten.
