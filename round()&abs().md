## The round() and abs() Functions
### round()
The round() function accepts a float value and returns the nearest integer.
```python
round(3.14) # = 3
round(7.7) # = 8
round(-2.2) # = -2
```  
The round() function also accepts an optional second argument specifying how many decimal places it should round.
```python
round(3.14, 1) # = 3.1
round(7.7777, 3) # = 7.778
```  
The behavior for rounding half numbers is a bit odd. The function call round(3.5) rounds up to 4, while round(2.5) rounds down to 2. This quirk is caused by how computers handle floating-point numbers and you should keep this behavior in mind.

### abs()
The abs() function returns the absolute value of the number argument. In mathematics, this is defined as the distance from 0, but it is typically the positive form of any number.
```python
abs(25) # = 25
abs(-25) # = 25
abs(-3.14) # = 3.14
abs(0) # = 0
```
