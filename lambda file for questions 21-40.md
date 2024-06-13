
66. How do you check if a string contains a substring in Python?<br>
Ans: There are three main ways to check if a substring exists within a string in Python:<br>

Using the ```in``` operator:
* This is the simplest and most efficient way to check for a substring.
* The ```in``` operator returns ```True``` if the substring is found within the string, and ```False``` otherwise.<br>
Code Example:

```python
my_string = "This is a string"
substring = "is"

if substring in my_string:
  print("Substring found!")
else:
  print("Substring not found.")

# Output: Substring found!

# Another Example

string = "Hello, world!"
if "world" in string:
    print("Substring found")
else:
    print("Substring not found")

# Output: Substring found
```

Using the ```find()``` method:

```python
my_string = "This is a string"
substring = "is"

index = my_string.find(substring)

if index != -1:
  print("Substring found at index", index)
else:
  print("Substring not found.")

# Output: Substring found at index 2


# Another Example:

string = "Hello, world!"
if string.find("world") != -1:
    print("Substring found")
else:
    print("Substring not found")

# Output: Substring found
```

Using regular expressions (case-insensitive):

```python
import re

my_string = "This is a String"
substring = "is"

matches = re.findall(substring, my_string, flags=re.IGNORECASE)

if matches:
  print("Substring found:", matches)
else:
  print("Substring not found.")

# Output: Substring found: ['is', 'IS']
```

* All three methods achieve the goal.
* The ```in``` operator simply confirms its presence, while ```find()``` provides the starting index, and regular expressions with the ```re.IGNORECASE``` flag identify all occurrences regardless of case.

<br>

67. Explain the use of the assert statement in Python.<br>
Ans: In Python, the ```assert``` statement is a debugging and validation tool used to check through assumptions about conditions during development.
* If the condition is true, the ```assert``` statement does nothing, but if the condition is false, the ```assert``` statement raises an ```AssertionError``` exception.
* The general syntax for the assert statement is: ```assert condition, message```. The message is optional.<br>
Code Example:

```python
def is_positive(number):
  assert number > 0, "Number must be positive"
  # Rest of the function's logic

# Example usage with valid input
is_positive(5)  # No error, program continues

# Example usage with invalid input (causes assertion error)
is_positive(-2)  # Raises AssertionError with the message "Number must be positive"

# Example 2

# Checking a condition
x = 10
assert x > 0, "x must be a positive number"

# Checking a function's precondition
def divide(a, b):
    assert b != 0, "Divisor cannot be zero"
    return a / b

divide(10, 0)  # Raises AssertionError: Divisor cannot be zero

# Checking a function's postcondition
def square(x):
    result = x * x
    assert result >= 0, "Result must be non-negative"
    return result

square(-5)  # Raises AssertionError: Result must be non-negative
```

*It's important to note that ```assert``` statements are not a replacement for proper error handling, but rather a tool for catching and debugging issues during development. In production code, it's generally better to use explicit exception handling or other error-handling mechanisms.
* Assertions are meant for development and debugging, not for production code. In production environments, assertions can slow down the program's execution. You can disable them using techniques like ```-O``` optimization flag during compilation.

<br>


68. How do you create an empty list, tuple, or dictionary in Python?<br>
Ans: The simplest way is to directly use the general syntax, ```[]``` for lists, ```{}``` for dictionaries, and ```()``` for tuples, with each being empty. Like this:<br>
Code Example:

```python
empty_list = []
print(empty_list)  # Output: []

empty_tuple = ()
print(empty_tuple)  # Output: ()

empty_dict = {}
print(empty_dict)  # Output: {}
```

* Let's start with one that is already populated, have one that is empty and make that populated:<br>
Code Example:

```python
populated_list = [1, 2, 3, 4, 5]
empty_list = []
empty_list.extend(populated_list)  # or empty_list = populated_list[:]
print(empty_list)  # Output: [1, 2, 3, 4, 5]


populated_tuple = (1, 2, 3, 4, 5)
empty_tuple = ()
empty_tuple = tuple(populated_tuple)
print(empty_tuple)  # Output: (1, 2, 3, 4, 5)


populated_dict = {"key1": "value1", "key2": "value2"}
empty_dict = {}
empty_dict.update(populated_dict)
print(empty_dict)  # Output: {'key1': 'value1', 'key2': 'value2'}

```
* Alternatively, you can also create an empty list, tuple, or dictionary directly without starting with a populated version like in the first example.

<br>

69. What is the purpose of the sum() function in Python?<br>
Ans: The ```sum()``` function in Python is a built-in function that efficiently calculates the sum of elements from an iterable object (such as a list, tuple, or set).
* It takes an iterable as its argument and returns the sum of all the elements in that iterable.
* The general syntax for using the ``` sum()``` function is:

```python
sum(iterable, start=0)

# start is an optional parameter that represents the initial value of the sum. If the start parameter is not provided, it defaults to 0.
```
<br>

Code Example:

```python
# Summing a list of numbers
numbers = [1, 2, 3, 4, 5]
total = sum(numbers)
print(total)  # Output: 15

# Summing a tuple of numbers
numbers = (10, 20, 30, 40)
total = sum(numbers)
print(total)  # Output: 100

# Summing a set of numbers
numbers = {1, 2, 3, 4, 5}
total = sum(numbers)
print(total)  # Output: 15

# Summing a list with a starting value
numbers = [10, 20, 30, 40]
total = sum(numbers, 50)
print(total)  # Output: 150
```

* The ```sum()``` function is particularly useful when you need to calculate the total or cumulative sum of a sequence of numbers. It can also be used with custom data types that support the ```+``` operator, as long as the elements in the iterable are of the same type. For example, ```sum("123")``` would return ```123```.
* It's worth noting that the ```sum()``` function can also be used with iterables that contain non-numeric values, but in such cases, the ```+``` operator must be defined for the data type of the elements in the iterable.

<br>
70. How do you convert a list to a string in Python?<br>
Ans: 



71. Explain the difference between shallow and deep copy in Python dictionaries.
71. How do you convert a string to an integer or a float in Python?
72. What is the purpose of the format() method in Python strings?
73. How do you check if a file exists in Python?
74. Explain the difference between os.path.exists() and os.path.isfile() in Python
75. What is the purpose of the pickle module in Python?
76. How do you get the current working directory in Python?
77. Explain the difference between a list and a tuple comprehension in Python…
78. What is the purpose of the is operator in Python?
79. How do you convert a list of strings to a single string in Python?
80. Explain the use of the reduce() function in Python.
81. How do you convert a string to a list in Python?
82. What is the purpose of the min() and max() functions in Python?
83. How do you convert a string to a datetime object in Python?
84. Explain the difference between shallow and deep copy in Python lists.
85. What is the purpose of the locals() and globals() functions in Python?
86. How do you write a multiline string in Python?
87. What is the purpose of the split() method in Python strings?
88. How do you check if a number is even or odd in Python?
89. Explain the purpose of the bytes and bytearray data types in Python.
90. What is the purpose of the round() function in Python?
91. How do you create a dictionary with default values in Python?
92. Explain the difference between os.path.isdir() and os.path.isfile() in Python.
93. What is the purpose of the finally block in Python exception handling?
94. How do you reverse a list in Python?
95. What is the purpose of the del statement in Python?
96. Explain the difference between the os.system() and subprocess.run() functions in Python.
97. How do you split a string into a list of substrings in Python?
98. What is the purpose of the try, except, else, and finally blocks in Python?
99. How do you create a shallow copy of a list in Python?<br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
