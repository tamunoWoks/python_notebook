## Components of Flow Control
Flow control statements often start with a part called the condition and are always followed by a block of code called the clause. 

### Conditions:
Boolean expressions could all be considered conditions, which are the same thing as expressions; *condition* is just a more specific name in the context of flow control statements. A condition always evaluates to a Boolean value, True or False. A flow control statement decides what to do based on whether its condition is True or False, and almost every flow control statement uses a condition. You’ll frequently write code that could be described in English as follows: “If this condition is true, do this thing, or else do this other thing.” Other code you’ll write is the same as saying, “Keep repeating these instructions as long as this condition continues to be true.”

### Blocks of Code:
Lines of Python code can be grouped together in blocks. You can tell when a block begins and ends from the indentation of the lines of code. There are four rules for blocks:
- A new block begins when the indentation increases.
- Blocks can contain other blocks.
- A block ends when the indentation decreases to zero or to a containing block’s indentation.
- Python expects a new block immediately after any statement that ends 
with a colon.

### Program Execution:
Program execution (or simply, execution) is a term for the current instruction being executed. If you put your finger on each line on your screen as the line is executed, you can think of your finger as the program execution.  
&nbsp;&nbsp;&nbsp;&nbsp;Not all programs execute by simply going straight down, however. If you use your finger to trace through a program with flow control statements, you’ll likely find your finger jumping around to different places in the source code based on conditions.

## Flow Control Statements
Let’s explore the most important piece of flow control: the statements themselves which are the actual decisions your programs will make.

### `if`:
The most common type of flow control statement is the `if` statement. An `if` statement’s clause (that is, the block following the if statement) will execute if the statement’s condition is `True`. The clause is skipped if the condition is `False`.
&nbsp;&nbsp;&nbsp;&nbsp;In plain English, an `if` statement could be read as, “If this condition is true, execute the code in the clause.” In Python, an if statement consists of the following:
- The if keyword
- A condition (that is, an expression that evaluates to True or False)
- A colon
- Starting on the next line, an indented block of code (called the if clause or if block)
