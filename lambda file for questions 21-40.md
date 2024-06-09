

31. What is the Global Interpreter Lock (GIL) in Python?<br>
Ans: The Global Interpreter Lock (GIL) is a safety mechanism in the most common implementation of Python, called CPython.
* The GIL is a mutex (mutual exclusion) lock that allows only one Python thread to execute at a time, even on multi-core or multi-CPU systems.
* This ensures thread safety and simplifies memory management in Python by making it thread-safe. Multiple threads won't interfere with each other when accessing or modifying Python objects.
* The main purpose of the GIL is to protect the interpreter's internal data structures from being corrupted by multiple threads and it does this by ensuring that only one thread can execute Python bytecode at a time, effectively serializing the execution of Python code.
* However, this limits the ability of Python programs to take advantage of multiple CPU cores or processors, as only one thread can execute Python bytecode at a time. This can be a problem for CPU-bound tasks, where the program could potentially benefit from parallel execution.
* To mitigate the limitations of the GIL, Python provides several alternatives for achieving concurrency, such as using the ```multiprocessing``` module, which allows you to create separate Python processes that can run in parallel, each with its own GIL.<br>

32.  What is a context manager in Python?<br>
Ans: A context manager in Python is a way to automate the management of resources with the help of the ```with``` statement.
* It is a way to ensure that resources are properly acquired and released, even in the face of exceptions or other control flow changes. This helps prevent resource leaks and errors.
* The context manager pattern is particularly useful when working with resources that need to be properly acquired and released, such as File objects, Database connections, Locks, Network sockets, Graphical user interface (GUI) elements.<br>
Code Example:
```python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```
* Note that you can also create your own custom context managers by defining a class with ``` __enter__()``` and ```__exit__()``` methods, or by using the ```@contextmanager``` decorator from the ```contextlib``` module.<br>

33. How do you handle JSON data in Python?<br>
Ans: In Python, handling JSON (JavaScript Object Notation) data is a straightforward process, thanks to the built-in ```json``` module. The json module provides functions for encoding and decoding JSON data.
* Parsing JSON data: Use the ```json.loads()``` function to parse a JSON-formatted string into a Python dictionary or list.
* Serializing Python data to JSON: Use the ```json.dumps()``` function to convert a Python dictionary or list into a JSON-formatted string.
Code Example:
```python
#Parsing JSON data

import json

json_data = '{"name": "John Doe", "age": 30, "city": "New York"}'
python_data = json.loads(json_data)
print(python_data)
# Output: {'name': 'John Doe', 'age': 30, 'city': 'New York'}

# =====================================

#Serializing Python data to JSON

import json

python_data = {"name": "John Doe", "age": 30, "city": "New York"}
json_data = json.dumps(python_data)
print(json_data)
# Output: '{"name": "John Doe", "age": 30, "city": "New York"}'
```
* Reading and writing JSON files: Use the ```json.load()``` function to read JSON data from a file. Use the ```json.dump()``` function to write Python data to a JSON file.<br>
Code Example:
```python
import json

# Reading from a JSON file
with open("data.json", "r") as file:
    data = json.load(file)
    print(data)

# Writing to a JSON file
python_data = {"name": "John Doe", "age": 30, "city": "New York"}
with open("data.json", "w") as file:
    json.dump(python_data, file)
```
* The ```json``` module in Python provides a straightforward and efficient way to work with JSON data, allowing you to easily convert between Python data structures and their JSON representations.

Qn: Is it json.loads() or json.load()?
Ans: You'll use  ```json.loads()```  when you're dealing with JSON data stored in a string format. In contrast,  ```json.load()```  is used specifically for reading JSON data from a file.
* If you have JSON data as a string (e.g., received from an API or user input), use ```json.loads()```. If you have JSON data stored in a file, use ```json.load()```.


  
34. Explain the differences between ＿getattr() and ＿getattribute() methods in Python.<br>
Ans: In Python, the __getattr__() and __getattribute__() methods are both used to customize attribute access, but they have some key differences:<br>
```getattr(self, name):```
* The ```__getattr__()``` method is called when an attribute is not found in an object's instance dictionary or class.
* It is a fallback method that is invoked when the normal attribute lookup process fails.
* The ```__getattr__()``` method is only called for attributes that are not found, not for attributes that are found but have a value of None.
* It is useful for providing a custom behavior for missing attributes, such as returning a default value or raising a specific exception.
* Both ```__getattr__()``` and ```__getattribute__()``` are dunder methods (methods whose name starts and ends with double underscores) in Python that deal with attribute access.

```getattribute(self, name):```
* The ```__getattribute__()``` method is called for every attribute access, regardless of whether the attribute exists or not.
* It is the first method called during the attribute lookup process, and it can be used to control the entire attribute access mechanism.
* The ```__getattribute__()``` method can lead to infinite recursion if not implemented carefully, as it is called for every attribute access, including the access to the ```__getattribute__()``` method itself.
* It is generally more powerful than ```__getattr__()```, but it requires more care in implementation to avoid infinite recursion.<br><br><br>
Code Example ```__getattr__:```
```python
class MyClass:
    def __init__(self, data):
        self.data = data

    def __getattr__(self, name):
        if name == 'upper_data':
            return self.data.upper()
        else:
            raise AttributeError(f"'{type(self).__name__}' object has no attribute '{name}'")

obj = MyClass('hello')
print(obj.upper_data)  # Output: HELLO
print(obj.non_existent_attr)  # Raises AttributeError
```

Code Example: ```__getattribute__()```
```python
class MyClass:
    def __init__(self, data):
        self.data = data

    def __getattribute__(self, name):
        if name == 'upper_data':
            return self.data.upper()
        else:
            return super().__getattribute__(name)

obj = MyClass('hello')
print(obj.upper_data)  # Output: HELLO
print(obj.data)  # Output: hello
```
Code Example incorporating both at once:
```python
class MyClass:
  def __init__(self):
    self.name = "Alice"

  def __getattribute__(self, attr):
    print(f"Accessing attribute: {attr}")
    return object.__getattribute__(self, attr)  # Fallback to normal lookup

  def __getattr__(self, attr):
    print(f"Attribute '{attr}' not found")
    return None  # Return None for missing attributes

obj = MyClass()

print(obj.name)  # Output: Accessing attribute: name
                  #        name
print(obj.age)  # Output: Accessing attribute: age
                  #        Attribute 'age' not found
                  #        None
```
In this example:
* ```__getattribute__()``` prints a message whenever an attribute is accessed and then falls back to normal lookup using object. ```__getattribute__()```.
* ```__getattr__()``` is called for the non-existent attribute age and prints a message indicating it's not found, then returns ```None```.

The main differences between ```__getattr__()``` and ```__getattribute__()``` are:
* Timing of invocation: ```__getattr__()``` is called only when the normal attribute lookup process fails, while ```__getattribute__()``` is called for every attribute access.
* Potential for infinite recursion: ```__getattribute__()``` is more prone to infinite recursion if not implemented carefully, as it is called for every attribute access.
* Scope of control:``` __getattribute__()``` provides more control over the entire attribute access mechanism, while ```__getattr__()``` is limited to handling missing attributes.
* In general, ```__getattr__()``` is more commonly used, as it is simpler to implement and less prone to infinite recursion. ```__getattribute__()``` is more powerful but requires more careful implementation to avoid issues.

Qn: What about setAttribute, what is it? What does it do?<br>
AnS: In Python, ```setattr``` is not a dunder method like ```__getattr__``` and ```__getattribute__```, but a built-in function used to set the value of an attribute on an object. It provides a dynamic way to modify existing attributes or even create new ones on an object at runtime.
* Syntax: ```setattr(object, name, value)``` where ```object```: is the object instance on which you want to set the attribute, ```name```: is the name of the attribute (as a string), ```value```: is the value you want to assign to the attribute.<br>
Code Example:
```python
class Person:
  def __init__(self, name):
    self.name = name

person = Person("Bob")

# Modify existing attribute
setattr(person, "age", 30)

# Create a new attribute
setattr(person, "occupation", "Software Engineer")

print(person.name)  # Output: Bob
print(person.age)    # Output: 30
print(person.occupation)  # Output: Software Engineer
```
Key Points:
* ```setattr``` is a versatile tool for dynamic attribute manipulation.
* It's important to use it cautiously, as modifying attributes can potentially have unintended consequences on object behavior.
* In some cases, using dot notation (e.g., ```person.age = 30```) might be more readable for setting existing attributes. However, ```setattr``` provides more flexibility for dynamic scenarios.

35. What are modules and packages in Python?<br>
Ans: In Python, modules and packages are fundamental building blocks for organizing your code. They promote code reusability and maintainability.<br>
Modules:
* A module is a single Python file (```.py```) containing functions, classes, variables, and executable statements.
* You can import modules into other Python files to use the functionalities they provide.
* Importing a module makes its contents available in your current namespace.<br>

Packages:
* A package is a collection of related modules organized into a directory structure.
* A directory containing a special file named ```__init__.py``` (can be empty) is considered a package.
* Packages allow for hierarchical organization using dot notation (e.g., ```package.module.function```).


37. 
38. What is the purpose of the ＿init＿ py file in Python packages?
39. How do you handle date and time in Python?
40. What is the purpose of _all… in Python?
41. Explain the difference between os.path.join() and os.path.abspath() in
Python.
42. What is the purpose of the zip() function in Python?
40. How do you remove duplicates from a list in Python?
41. 41. Explain the use of the map() function in Python.
42. How do you reverse a string in Python?
43. What is the purpose of the re module in Python?
44. How do you create and use virtual environments in Python?
45. Explain the difference between ＿iter＿() and ＿next＿() methods iterators. in Python
46. What is the purpose of the collections module in Python?
47. How do you concatenate strings in Python?
48. What is the purpose of the itertools module in Python?
49. How do you find the index of an element in a list in Python?
50. What is the purpose of the enumerate() function in Python?
51. Explain the difference between del, remove(), and pop() methods for removing elements from lists in Python.
52. How do you convert a string to lowercase or uppercase in Python?
53. What is the purpose of the sys module in Python?
54. How do you sort a dictionary by its values in Python?
55. Explain the purpose of the with statement in Python.
56. How do you check if a key exists in a dictionary in Python?
57. What is the purpose of the random module in Python?
58. How do you find the length of a list in Python?
59.Explain the purpose of the classmethod decorator in Python.
60. How do you round a floating-point number to a specified number of decimal places in Python?
61. What is the purpose of the isinstance() function in Python?
62. How do you concatenate two lists in Python?
63. Explain the purpose of the filter() function in Python.
64. How do you create a dictionary from two lists in Python?
65. What is the purpose of the os module in Python?
66. How do you check if a string contains a substring in Python?
67. Explain the use of the assert statement in Python.
68. How do you create an empty list, tuple, or dictionary in Python?
69. What is the purpose of the sum() function in Python?
70. How do you convert a list to a string in Python?
71. Explain the difference between shallow and deep copy in Python dictionaries.
72. How do you convert a string to an integer or a float in Python?
73. What is the purpose of the format() method in Python strings?
74. How do you check if a file exists in Python?
75. Explain the difference between os.path.exists() and os.path.isfile() in Python
76. What is the purpose of the pickle module in Python?
77. How do you get the current working directory in Python?
78. Explain the difference between a list and a tuple comprehension in Python…
79. What is the purpose of the is operator in Python?
80. How do you convert a list of strings to a single string in Python?
81. Explain the use of the reduce() function in Python.
82. How do you convert a string to a list in Python?
83. What is the purpose of the min() and max() functions in Python?
84. How do you convert a string to a datetime object in Python?
85. Explain the difference between shallow and deep copy in Python lists.
86. What is the purpose of the locals() and globals() functions in Python?
87. How do you write a multiline string in Python?
88. What is the purpose of the split() method in Python strings?
89. How do you check if a number is even or odd in Python?
90. Explain the purpose of the bytes and bytearray data types in Python.
91. What is the purpose of the round() function in Python?
92. How do you create a dictionary with default values in Python?
93. Explain the difference between os.path.isdir() and os.path.isfile() in Python.
94. What is the purpose of the finally block in Python exception handling?
95. How do you reverse a list in Python?
96. What is the purpose of the del statement in Python?
97. Explain the difference between the os.system() and subprocess.run() functions in Python.
98. How do you split a string into a list of substrings in Python?
99. What is the purpose of the try, except, else, and finally blocks in Python?
100. How do you create a shallow copy of a list in Python?<br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
