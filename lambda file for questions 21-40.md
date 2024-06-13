
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
Ans:

<br>
64. How do you create a dictionary from two lists in Python?
65. What is the purpose of the os module in Python?
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
