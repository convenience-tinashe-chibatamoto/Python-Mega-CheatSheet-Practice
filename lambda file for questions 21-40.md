
71. Explain the difference between shallow and deep copy in Python dictionaries. <br>
Ans: In Python dictionaries, shallow copy and deep copy refer to how the contents of a dictionary are duplicated: <br>

Shallow Copy:
* Uses the built-in ```dict.copy()``` method.
* Any changes made to the values (objects) in the original dictionary will also be reflected in the shallow copy, and vice versa.<br>
Code Example:

```python
original_dict = {'a': [1, 2], 'b': 3}
shallow_copy = original_dict.copy()

# Modifying a mutable element in the shallow copy
shallow_copy['a'].append(3)

print("Original dictionary:", original_dict)  # Output: {'a': [1, 2, 3], 'b': 3}
print("Shallow copy:", shallow_copy)  # Output: {'a': [1, 2, 3], 'b': 3}
```

Deep Copy:
* Uses the ```copy.deepcopy()``` function from the ```copy``` module.
* A deep copy creates a new object with a completely independent copy of the data.
* Changes made to the values in the original dictionary or the deep copy won't affect each other. <br>
Code Example:
```python
import copy

original_dict = {'a': [1, 2], 'b': 3}
deep_copy = copy.deepcopy(original_dict)

# Modifying a mutable element in the deep copy
deep_copy['a'].append(3)

print("Original dictionary:", original_dict)  # Output: {'a': [1, 2], 'b': 3}
print("Deep copy:", deep_copy)  # Output: {'a': [1, 2, 3], 'b': 3}
```
Usage:
* Use a shallow copy when you only need a new reference to the existing data and modifications in one will affect the other. (e.g., temporary modifications)
* Use a deep copy when you need to ensure that changes made to the copy do not affect the original (e.g., passing data to functions that might modify it)
<br>


72. How do you convert a string to an integer or a float in Python?<br>
Ans: You can convert a string to an integer or a float in Python using built-in functions: ```int(string)``` and ```float(string)```.<br>
Code Example:
```python
# String to integer
str_to_int = "42"
int_value = int(str_to_int)
print(int_value)  # Output: 42

# String to float
str_to_float = "3.14"
float_value = float(str_to_float)
print(float_value)  # Output: 3.14

# If the string cannot be converted to an integer, the int() function will raise a ValueError exception.
str_num = "123.45"

# Convert to integer (raises ValueError for non-integers)
# int_num = int(str_num)  # Uncomment to see the ValueError

# Also, if the string contains non-numeric characters, the conversion will fail and raise a ValueError.
str_with_non_numeric = "42.3.14"
float_value = float(str_with_non_numeric)
# ValueError: could not convert string to float: '42.3.14'
```

Note:
*You can also convert strings that represent numeric values with leading or trailing whitespace, as the ```int()``` and ```float()``` functions will automatically strip the whitespace.<br>
Code Example:
```python
str_with_whitespace = "  -10  "
int_value = int(str_with_whitespace)
print(int_value)  # Output: -10
```

* For something like ```'42.3.14'```, you may need to use additional string manipulation techniques, such as regular expressions, to extract the numeric part of the string before converting it to an integer or float.
<br>


73. What is the purpose of the format() method in Python strings?
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
