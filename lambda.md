## Lambda Functions
Lambda functions in Python are small, anonymous functions defined using the lambda keyword. They are often used for short, simple operations where a full function definition is unnecessary. Lambda functions can take any number of arguments but can only have one expression.
The syntax for enumerate() is:  
```python
lambda arguments: expression
```
#### Key Characteristics:
- Anonymous: Lambda functions don't have a name (they are not bound to an identifier).
- Single Expression: They can only contain one expression, which is evaluated and returned.
- Inline Use: Often used inline, such as in map(), filter(), or sorted().
#### When to Use Lambda Functions:
- For simple, one-off operations.
- When passing a function as an argument to higher-order functions like map(), filter(), or sorted().
- When you want to avoid defining a full function for a small task.
#### When Not to Use Lambda Functions:
- For complex logic (use a regular def function instead).
- When the function needs to be reused multiple times (lambda functions are anonymous and harder to reuse).
- When readability is a priority (lambda functions can make code harder to understand if overused).
  
Sample code: [Lambda functions](https://github.com/tamunoWoks/python_tutorial/blob/main/lambda.ipynb)
