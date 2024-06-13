
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
* ```math.ceil(number)```: This function rounds the  ```number``` up to the nearest integer. In this case, ```math.ceil(3.14159)``` returns ```4```.
* ```math.floor(number)```: This function rounds the ```number``` down to the nearest integer. In this case, it rounds ```3.14159``` down to ```3.```
* ```math.trunc(number)```: This function returns the integral part of the ```number```, discarding any fractional digits. In this case, ```math.trunc(3.14159)``` returns ```3```.
* ```round(number)``` (always used without the ```math``` module) uses banker's rounding to round the number to the nearest integer. Here, it also rounds to ```3```.
* Although ```round()``` provides control over decimal places, it's for rounding to nearest integer by default. The ```ceil()``` and ```floor()``` functions from the ```math``` module offer a way to strictly round up or down to the nearest whole number.

<br>
61. What is the purpose of the isinstance() function in Python?<br>

Ans: The ```isinstance()``` function in Python is a built-in function used for type checking. 
* It verifies if an object is of a specified type, returning ```True``` if it is, and ```False``` otherwise. <br>
Code Example:
```python
# syntax
isinstance(object, classinfo)

object: This is the object you want to check the type of.
classinfo: This can be a class type, a tuple of class types, or a built-in type like int, str, etc.

# Example 1

# Check if a variable is an integer
x = 42
if isinstance(x, int):
    print("x is an integer")
else:
    print("x is not an integer")
# Output: x is an integer

# Check if a variable is a string or a float
y = "hello"
if isinstance(y, (str, float)):
    print("y is a string or a float")
else:
    print("y is not a string or a float")
# Output: y is a string or a float
```

* Example 2
```python
class Animal:
  pass

class Dog(Animal):
  pass

animal = Animal()
dog = Dog()

# isinstance() with a class
print(isinstance(animal, Animal))  # True
print(isinstance(dog, Animal))    # True (Dog is a subclass of Animal)

# isinstance() with a tuple of classes
print(isinstance(animal, (int, str, Animal)))  # True

```

* In summary, ```isinstance()``` is a versatile tool for ensuring your code behaves as expected by checking object types during runtime.
* the ```isinstance()``` function allows you to write more robust and flexible code by checking the type of an object before performing operations on it, which can be particularly useful when you're working with functions that can accept arguments of different types, or when you're dealing with user input that may be of an unexpected type.

<br>
62. How do you concatenate two lists in Python? <br>
Ans: There are several ways to concatenate (join) two lists in Python.

* Using the ```+``` operator is the simplest and most common way. The ```+``` operator creates a new list by appending the elements of the second list to the end of the first list.<br>
Code Example

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined_list = list1 + list2
print(combined_list)  # Output: [1, 2, 3, 4, 5, 6]

```
* You can also use the ```extend()``` method, which directly modifies the first list by adding elements from the second list to its end without creating a new list.
* You can also use list unpacking with the ```*``` operator, where ```combined_list = [*list1, *list2]```. This creates a new list by combining the elements of both lists.
* For very large lists where memory efficiency is a concern, consider ```itertools```.
* All of these produce the exact same output.
<br>

63. Explain the purpose of the filter() function in Python.<br>
Ans: The ```filter()``` function in Python is used to create a new iterator that contains elements from an existing iterable (like a list, tuple, or string) which pass a certain condition.
* It essentially acts as a filtering tool for your data.
* Syntax: ```filter(function, iterable)```.<br>
* It creates a new iterator, not a list by default. You can convert the created iterator to a list using ```list()``` if needed.
Code Example:
```python
# Filter out all even numbers from a list
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Define a function to check if a number is odd
def is_odd(x):
    return x % 2 != 0

# Use filter() to get a list of odd numbers
odd_numbers = list(filter(is_odd, numbers))
print(odd_numbers)  # Output: [1, 3, 5, 7, 9]
```
* In this example, the ```is_odd()``` function is used as the function argument to ```filter()```. The ```filter()``` function applies this function to each number in the numbers list, and returns an iterator containing only the odd numbers. <br>
Code Example 2:
```python
numbers = [1, 2, 3, 4, 5, 6]

# Define a function to check if a number is even
def is_even(number):
  return number % 2 == 0

# Apply filter() with the function and get an iterator
even_numbers = filter(is_even, numbers)

# Convert the iterator to a list (optional)
print(list(even_numbers))  # Output: [2, 4, 6]

```


* The ```filter()``` function is a powerful tool for data processing and manipulation, as it allows you to easily select a subset of items from a larger sequence based on a specific criteria. It's often used in combination with other functions like map() and lambda to create concise and efficient code.
<br>


64. How do you create a dictionary from two lists in Python?<br>
Ans: In Python, you can create a dictionary from two lists using the ```zip()``` function and the ```dict()``` function. Here's how you can do it:<br>
Code Example:
```python
keys = ["name", "age", "city"]
values = ["Alice", 30, "New York"]

# Combine keys and values using zip()
combined = zip(keys, values)

# Create a dictionary from the zipped tuples using dict()
my_dict = dict(combined)
print(my_dict)  # Output: {'name': 'Alice', 'age': 30, 'city': 'New York'}

```
* ```The zip()``` function takes two or more iterables (in this case, the keys and values lists) and returns an iterator of tuples, where each tuple contains the corresponding elements from each iterable.
* The ```dict()``` function is then used to convert the iterator of tuples (created by ```zip()```) into a dictionary, where the keys are taken from the first element of each tuple, and the values are taken from the second element of each tuple.<br>

* You can also create a dictionary directly from two lists using a dictionary comprehension:<br>
Code Example 2:
```python
keys = ["name", "age", "city"]
values = ["Alice", 30, "New York"]

my_dict = {key: value for key, value in zip(keys, values)}
print(my_dict)  # Output: {'name': 'Alice', 'age': 30, 'city': 'New York'}

```
This code:
* Uses a dictionary comprehension with ```{}```.
* Iterates through the zipped keys and values using ```for key, value in zip(keys, values)```.
* Assigns each key-value pair to the dictionary using ```key: value```.<br>

* If readability is your priority, the first approach with ```zip()``` and ```dict()``` might be clearer, especially for beginners.
* For a more concise approach that is preferred by many programmers, the dictionary comprehension is the way to go.<br>

65. What is the purpose of the os module in Python?<br>
Ans: The ```os``` module in Python provides a portable way to interact with the operating system.
* It offers functions for various tasks related to file and directory management, process control, environment variables, and more.
* This built-in module provides a platform-independent way of working with operating system-specific functionality. This means that you can write code that works across different operating systems (e.g., Windows, macOS, Linux) without having to worry about the underlying details of each system.


<br>
65. How do you check if a string contains a substring in Python?
66. Explain the use of the assert statement in Python.
67. How do you create an empty list, tuple, or dictionary in Python?
68. What is the purpose of the sum() function in Python?
69. How do you convert a list to a string in Python?
70. Explain the difference between shallow and deep copy in Python dictionaries.
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
