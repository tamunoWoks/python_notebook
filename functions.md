## Functions
A function is like a mini program within a program.  
Python provides several built-in functions, such as the print(), input(), and len() functions, but you can also write your own.

#### Creating Functions in Python:
In Python, functions are created using the `def` keyword followed by the function name, parentheses `()`, and a colon `:`. The function body is written with indentation underneath the definition line.  

To call a function in Python, you simply write the function name followed by parentheses `()`, and pass any required arguments inside the parentheses.

##### Example:
This is a simple function with no parameters:
```python
def greet():
    print("Hello, world!")
greet()
```
A major purpose of functions is to group code that gets executed multiple times. Without a function defined, you would have to copy and paste this code each time you wanted to run it.   
    In general, you always want to avoid duplicating code, because if you ever decide to update the code you’ll have to remember to change the code in every place you copied it.

## Arguments and Parameters
When you call the `print()` or `len()` function, you pass it values, called **arguments**, by entering them between the parentheses. You can also define your own functions that accept arguments.  


#### Tips:
- *Parameters* are variables that contain arguments.
- When a function is called with arguments, the arguments are stored in the parameters.
- You should use parameters in your function if you need it to follow slightly different instructions depending on the values you pass to the function call.
- One special thing to note about parameters is that the value stored in a parameter is forgotten when the function returns.

**NOTE:** The terms *define*, *call*, *pass*, *argument*, and *parameter* can be confusing. To review their meanings, let us consider a code example:
```python
def say_hello_to(name):
    # Prints three greetings to the name provided
    print('Good morning, ' + name)
    print('Good afternoon, ' + name)
    print('Good evening, ' + name)
say_hello_to('Al')
```
- To define a function is to create it, and the `def` statement defines the `say_hello_to()` function.
- The `say_hello_to('Al')` line calls the now-created function, sending the execution to the top of the function’s code. This function call is also known as `passing` the string value `Al' to the function.
- A value being passed to a function in a function call is an `argument`. Hence 'Al' is the `argument` in the above program.
- Variables that have `arguments` assigned to them are `parameters`. Hence the variable 'name' in the function definition is the `parameter`.

#### Key Differences:
| Feature            | Parameter                                  | Argument                                    |
|:-------------------|:-------------------------------------------|:--------------------------------------------|
| **Definition**     | Variable in a function's definition.       | Actual value passed during a function call. |
| **When it exists** | When the function is **defined**.          | When the function is **called**.            |
| **Purpose**        | Acts as a placeholder for incoming data.   | Provides the concrete value to use.         |
| **Scope**          | Local to the function.                     | Exists only during the function call.       |
| **Example**        | `def greet(name):` (`name` is a parameter) | `greet("Alice")` (`"Alice"` is an argument) |

#### Analogy:
- **Parameter** → Empty coffee cup (placeholder).
- **Argument** → Actual coffee poured into the cup (real value).

## Return Values and `return` Statements:
In Python, the `return` statement is used to exit a function and optionally send a value (or multiple values) back to the caller. The value(s) sent back are called return values.   
&nbsp;&nbsp;&nbsp;&nbsp;When creating a function using the `def` statement, you can specify the return value with a return statement, which consists of the following:
- The `return` keyword
- The value or expression that the function should return.  

> In the case of an expression, the return value is whatever this expression evaluates to. Remember that expressions consist of values and operators; you can use a function call in an expression because the call evaluates to its return value.

#### Example:
1.
```python
def add(a, b):
    return a + b  # Returns the sum

result = add(3, 5)  # `result` gets the return value (8)
print(result)  # Output: 8
```
2.
```python
def get_user():
    name = "Alice"
    age = 25
    return name, age  # Returns a tuple: ("Alice", 25)

user_name, user_age = get_user()  # Unpacks the tuple
print(user_name, user_age)  # Output: Alice 25
```
#### Tips:
- Python also allows returning multiple values (as a tuple, list, or dictionary).
- You can use return to exit a function early if a condition is met.
- If a function has no return statement, it returns None.
- You can pass return values as arguments to other function calls.

#### Return vs. Print:
| Feature       | `return`                          | `print()`                        |
|--------------|----------------------------------|----------------------------------|
| **Purpose**  | Sends data back to the caller.   | Displays output to the console.  |
| **Usage**    | Used inside functions.           | Used for debugging/output.       |
| **Effect**   | Exits the function.              | Does not exit the function.      |

#### Summary:
| Concept          | Description |
|:-----------------|:-----------|
| **`return`** | Exits a function and sends back a value. |
| **Return Value** | The data sent back (can be any type). |
| **Multiple Returns** | Use tuples/lists/dicts to return multiple values. |
