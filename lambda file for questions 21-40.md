
76. What is the purpose of the pickle module in Python?<br>
Ans: The ```pickle``` module in Python is used for serializing and deserializing Python object structures.
* It lets you convert Python objects (like lists, dictionaries, or even custom classes) into a format that can be stored on disk, transmitted over a network, or used later in your program.<br>
Code Example:

```python
import pickle

# Define a simple class
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Create a Person object
person = Person("John Doe", 35)

# Serialize the object using pickle
with open("person.pickle", "wb") as f:
    pickle.dump(person, f)

# Deserialize the object
with open("person.pickle", "rb") as f:
    loaded_person = pickle.load(f)

# Print the deserialized object
print(loaded_person.name)  # Output: John Doe
print(loaded_person.age)   # Output: 35
```
* In this example, we first define a ```Person``` class, then create an instance of it. We then use the ```pickle.dump()``` function to serialize the ```person``` object and save it to a file named ```person.pickle```.
* Later, we can load the serialized object back from the file using the ```pickle.load()``` function, and the deserialized object is stored in the ```loaded_person``` variable.
* Finally, we print the values of the ```name``` and ```age``` attributes of the deserialized object to verify that the serialization and deserialization process was successful.
* This is a basic example, but the ```pickle``` module can be used to handle lists, dictionaries and more complex data structures as well, beyond user-defined classes.
* It's important to note that the serialized data contains the full state of the object, including any references to other objects, which can lead to potential security risks if the data is not from a trusted source.<br>

77. How do you get the current working directory in Python?<br>
Ans: There are two main ways to get the current working directory in Python:<br><br>

Using the ```os.getcwd()``` method:
* This is the most common and recommended approach.
* It uses the ```os``` module and its ```getcwd()``` (get current working directory) function.  <br>
Code Example:
```python
import os

current_directory = os.getcwd()
print(current_directory)

# If you need to change the current working directory, you can use the os.chdir() function
import os

# Change the current working directory
os.chdir("/path/to/new/directory")

# Get the new current working directory
current_directory = os.getcwd()
print(current_directory)
```

Using the ```pathlib.Path.cwd()``` method (Python 3.4+):
* It offers a more object-oriented approach to working with file paths.
* Both methods will give you the same result, but the ```pathlib``` approach provides a more modern and flexible way to work with file paths in Python.<br>
Code Example:

```python
from pathlib import Path

current_directory = Path.cwd()
print(current_directory)

# If you need to change the current working directory, you can use the Path.cwd().chdir() method in pathlib:
from pathlib import Path

new_dir = Path("/path/to/new/directory")

# Change the current working directory to the new_dir path
Path.cwd().chdir(new_dir)
print(f"Current working directory changed to: {new_dir}")

```
* You can use a ```try```-```except``` block to handle potential ```FileNotFoundError``` exceptions that might occur if the specified new_dir doesn't exist.
<br>

78. Explain the difference between a list comprehension and a tuple comprehension in Python. <br>
Ans: In Python, both list comprehensions and tuple comprehensions are ways to create new sequences (lists or tuples) based on existing sequences or iterables. The main difference between them is the type of sequence they create.<br>
List Comprehension:
* Uses square brackets [].
* Creates a new list.
* Lists are mutable, meaning their elements can be changed after creation.

Tuple Comprehension:
* Uses parentheses ().
* Creates a new tuple.
* Tuples are immutable, meaning their elements cannot be modified after creation.<br>
Code Example:

```python
# List comprehension syntax
new_list = [expression for item in iterable if condition]

# Tuple comprehension syntax
new_tuple = (expression for item in iterable if condition)

# List comprehension Example
squares = [x**2 for x in range(5)]
print(squares)  # Output: [0, 1, 4, 9, 16]

# Tuple comprehension Example
squares_tuple = (x**2 for x in range(5))
print(squares_tuple)  # Output: <generator object <genexpr> at 0x7f6a1c0b0cd0>
print(tuple(squares_tuple))  # Output: (0, 1, 4, 9, 16)

```

* Note:

While Python doesn't have a dedicated tuple comprehension syntax, you can achieve the same result using a generator expression with parentheses and convert it to a tuple using ```tuple()```. However, list comprehensions are generally considered more readable for creating new lists.
<br>

79. What is the purpose of the is operator in Python? <br>
Ans: The ```is``` operator in Python is an identity operator used to used to check if two variables refer to the same object in memory.
* It's not for Value Comparison (unlike what ```==``` does).
* The is operator is commonly used to compare singleton objects, such as ```None```, ```True```, and ```False```, which are unique instances in Python.<br>
Code Example:

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(a is b)  # False, a and b are different objects
print(a is c)  # True, a and c refer to the same object

# Another Example:
x = None
y = None

print(x is y)  # True, x and y refer to the same None object
```
<br>

80. How do you convert a list of strings to a single string in Python? <br>
81. Explain the use of the reduce() function in Python. <br>
81. How do you convert a string to a list in Python? <br>
82. What is the purpose of the min() and max() functions in Python? <br>
83. How do you convert a string to a datetime object in Python? <br>
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
