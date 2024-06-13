
61. How do you round a floating-point number to a specified number of decimal places in Python?<br>
Ans: You can round a floating-point number to a specified number of decimal places in Python using the built-in ```round()``` function. This function takes two arguments:
* The number to be rounded
* (Optional) The number of decimal places to round to (defaults to 0, rounding to the nearest integer)
* If the optional argument is omitted, the number is rounded to the nearest integer.<br>
Code Example:

```python
number = 3.141592653589793
rounded_number = round(number, 2)
print(rounded_number)  # Output: 3.14


# Example 2
# Round to 2 decimal places
print(round(3.14159, 2))  # Output: 3.14

# Round to 1 decimal place
print(round(2.718, 1))  # Output: 2.7

# Round to the nearest integer
print(round(4.6))  # Output: 5
print(round(4.4))  # Output: 4

# Note that: The round() function uses banker's rounding, which means that if the digit in the discarded decimal place is 5, it rounds up if the next digit is even and down if it's odd
```
* This first code example rounds the number ```3.141592653589793``` to 2 decimal places, resulting in ```3.14```.
* For more control over rounding behavior (e.g., rounding up or down always), you can explore the ```math``` module functions like ```ceil()``` and ```floor()```.<br>
Code Example:

```python
import math

number = 3.14159

# Rounding up using ceil()
rounded_up = math.ceil(number)
print(f"Rounding {number} up with ceil(): {rounded_up}")  # Output: Rounding 3.14159 up with ceil(): 4

# Rounding down using floor()
rounded_down = math.floor(number)
print(f"Rounding {number} down with floor(): {rounded_down}")  # Output: Rounding 3.14159 down with floor(): 3

# Rounding to nearest using round() (default behavior)
rounded_nearest = round(number)
print(f"Rounding {number} to nearest with round(): {rounded_nearest}")  # Output: Rounding 3.14159 to nearest with round(): 3

# Trunc
print("Trunc:", math.trunc(number))    # Output: 3

```
* ```math.ceil(number)```: This function returns the smallest integer that is greater than or equal to the given ```number```. In this case, ```math.ceil(3.14159)``` returns ```4```.
* ```math.floor(number)```: This function returns the largest integer that is less than or equal to the given ```number```. In this case, ```math.floor(3.14159)``` returns ```3```.
* ```math.trunc(number)```: This function returns the integral part of the ```number```, discarding any fractional digits. In this case, ```math.trunc(3.14159)``` returns ```3```.
* ```round(number)``` (always used without the ```math``` module) uses banker's rounding to round the number to the nearest integer. Here, it also rounds to ```3```.
* Although ```round()``` provides control over decimal places, it's for rounding to nearest integer by default. The ```ceil()``` and ```floor()``` functions from the ```math``` module offer a way to strictly round up or down to the nearest whole number.

<br>
61. What is the purpose of the isinstance() function in Python?<br>

<br>
63. How do you concatenate two lists in Python?
64. Explain the purpose of the filter() function in Python.
65. How do you create a dictionary from two lists in Python?
66. What is the purpose of the os module in Python?
67. How do you check if a string contains a substring in Python?
68. Explain the use of the assert statement in Python.
69. How do you create an empty list, tuple, or dictionary in Python?
70. What is the purpose of the sum() function in Python?
71. How do you convert a list to a string in Python?
72. Explain the difference between shallow and deep copy in Python dictionaries.
73. How do you convert a string to an integer or a float in Python?
74. What is the purpose of the format() method in Python strings?
75. How do you check if a file exists in Python?
76. Explain the difference between os.path.exists() and os.path.isfile() in Python
77. What is the purpose of the pickle module in Python?
78. How do you get the current working directory in Python?
79. Explain the difference between a list and a tuple comprehension in Python…
80. What is the purpose of the is operator in Python?
81. How do you convert a list of strings to a single string in Python?
82. Explain the use of the reduce() function in Python.
83. How do you convert a string to a list in Python?
84. What is the purpose of the min() and max() functions in Python?
85. How do you convert a string to a datetime object in Python?
86. Explain the difference between shallow and deep copy in Python lists.
87. What is the purpose of the locals() and globals() functions in Python?
88. How do you write a multiline string in Python?
89. What is the purpose of the split() method in Python strings?
90. How do you check if a number is even or odd in Python?
91. Explain the purpose of the bytes and bytearray data types in Python.
92. What is the purpose of the round() function in Python?
93. How do you create a dictionary with default values in Python?
94. Explain the difference between os.path.isdir() and os.path.isfile() in Python.
95. What is the purpose of the finally block in Python exception handling?
96. How do you reverse a list in Python?
97. What is the purpose of the del statement in Python?
98. Explain the difference between the os.system() and subprocess.run() functions in Python.
99. How do you split a string into a list of substrings in Python?
100. What is the purpose of the try, except, else, and finally blocks in Python?
101. How do you create a shallow copy of a list in Python?<br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
