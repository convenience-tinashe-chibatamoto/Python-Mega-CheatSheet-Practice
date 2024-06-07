# Python Interview Prep: Q and Ans:

1. What is Python?<br>
Ans: Python is a high-level, interpreted programming language known for its simplicity and readability.
 * High-level: A high-level language is a programming language that is designed to be human-readable and abstracts away the low-level details of computer hardware. This means that the code you write in Python is closer to natural language and easier for humans to understand, rather than being closer to the machine-level language (binary code) that the computer can directly execute.
 * Interpreted: Python code is executed line by line by a program called the interpreter. This is different from compiled languages where the entire code is converted into machine code before running. Interpretation allows for faster development cycles as you can test and make changes quickly without recompiling everything.

2. Why Python?<br>
Ans:
* Simplicity and Readability(clean, intuitive syntax),
* Versatility (Python is a multi-purpose language that can be used for a wide range of applications, including web development, data analysis, machine learning, scientific computing, automation, and more),
* Large and Active Community (Python has a large and active community of developers who contribute to a vast ecosystem of libraries, frameworks, and tools. This makes it easy to find solutions to common problems and get support.),
* Cross-platform Compatibility (Python is a cross-platform language, meaning it can run on various operating systems, including Windows, macOS, and Linux, without the need for major changes to the code.),
* Rapid Prototyping(Since it's interpreted, this allows for faster development cycles as you can test and make changes quickly without recompiling everything.)

3. What are the key features of Python?<br>
Ans:
* Object-oriented: Python supports object-oriented programming concepts like classes and objects, enabling you to structure your code in a modular way.
* Portable: Python code can run on different operating systems without modification.
* Large third-party library ecosystem: There's a vast collection of external libraries available for various purposes, like data science (NumPy, Pandas), machine learning (TensorFlow, PyTorch), web development (Django, Flask), and more.
* Free and open-source: Python is free to use and modify, with a large and active community that contributes to its development.
* Dynamically typed: You don't need to declare variable types beforehand, making the code more flexible.

4. What is PEP 8?<br>
Ans:
* PEP 8 (Python Enhancement Proposal 8) is the official style guide for Python code. It provides guidelines and best practices for writing clean, consistent, and readable Python code.
* This covers Naming Conventions for functions, variables, classes, etc (capital letters for constants, etc), Code Formatting (Line length should be limited to 79 characters (or 72 characters for docstrings and comments), Indentation should use 4 spaces per indentation level (no tabs), Blank lines should be used to separate logical sections of code. Imports should be placed at the top of the file, and should be organized into sections (standard library, third-party, local).
* There are many tools available to help you write PEP 8 compliant code. e.g. PyCharm.  These tools can check the code and automatically format it according to the PEP 8 guidelines.
* The code would still work the same way, but the style guide helps attain consistency across all Python development.
 

5. What are the differences between lists and tuples in Python?<br>
Ans: The main differences between lists and tuples in Python are:<br>
* Mutability:<br>
Lists are mutable, which means you can modify their contents after they are created. You can add, remove, or change elements in a list.
Tuples are immutable, which means you cannot modify their contents after they are created. Once a tuple is defined, its elements cannot be changed.
* Syntax:<br>
Lists are defined using square brackets [], and their elements are separated by commas.
Tuples are defined using parentheses (), and their elements are also separated by commas.
* Usage:<br>
Lists are generally used when you need to store a collection of items that may need to be modified later.
Tuples are often used to represent a fixed set of values, such as the coordinates of a point or the fields in a database record.<br>
Code Example: <br>
```python
# Lists
my_list = [1, 2, 3, 4, 5]
my_list[2] = 10  # Modifying an element in the list
my_list.append(6)  # Adding an element to the list

# Tuples
my_tuple = (1, 2, 3, 4, 5)
# my_tuple[2] = 10  # This will raise a TypeError, as tuples are immutable
new_tuple = my_tuple + (6,)  # Creating a new tuple by concatenating the existing one</code>
```
<br>In the example:
<ol><li>The my_list variable is a mutable list, and we can modify its elements and add new elements to it.</li>
<li>The my_tuple variable is an immutable tuple, and we cannot modify its elements directly. However, we can create a new tuple by concatenating the existing one.</li>
</ol>
In general, you should use lists when you need to store a collection of items that may need to be modified, and use tuples when you need to represent a fixed set of values that should not be changed.<br>

6. Explain the difference between == and is operators in Python.
Ans:
* In Python, the == and is operators are used to compare values, but they have different meanings and use cases.
The == (equal to) operator:
<li>The == operator compares the values of two objects.</li>
<li>It checks if the two operands have the same value.</li>
<li>It returns True if the values are the same, and False otherwise.</li>
Code Example:<br>

```python
a = 5
b = 5
print(a == b)  # Output: True

c = [1, 2, 3]
d = [1, 2, 3]
print(c == d)  # Output: True
```
The is operator:
* The is operator compares the identity of two objects.
* It checks if the two operands refer to the same object in memory.
* It returns True if the two operands are the same object, and False otherwise.

Code Example:<br>

```python
a = 5
b = 5
print(a is b)  # Output: True

c = [1, 2, 3]
d = [1, 2, 3]
print(c is d)  # Output: False
```
In the first example, both ```a``` and ```b``` have the same value of 5, so ```a == b``` is True. However, ```a is b``` is also ```True``` because Python automatically caches small integer objects, so ```a``` and ```b``` refer to the same object in memory.
In the second example,``` c``` and ```d``` have the same value of ```[1, 2, 3]```, but they are two different list objects in memory, so ```c == d``` is ```True```, but ```c``` is ```d``` is ```False```.
The main differences between == and is are:
* ``` ==``` compares the values of the objects, while ```is``` compares the identity (memory location) of the objects.
* ```==``` is generally used for value comparison, while ```is``` is used to check if two variables refer to the same object in memory.
* == can be overridden by defining the ```__eq__``` method in a class, while ```is``` cannot be overridden.
In general, you should use ```==``` for value comparison and ```is``` for identity comparison, unless you have a specific reason to do otherwise.


7. What is the purpose of ＿init＿ in Python classes?
Ans:
* In Python, the ```__init__``` method (also known as the "dunder init" or "magic init" method) is a special method that is used to initialize the attributes of an object when an instance of a class is created. It's akin to a constructor in other programming languages.<br>
Here's a breakdown of its key purpose:
* Initializing object attributes: When you create an object (instance) from a class, the __init__ method gets automatically called. This method allows you to assign values to the object's attributes (variables) during its creation.
* Customizing object state: By providing arguments to the __init__ method, you can control the initial state of each object created from the class. This makes your objects more flexible and reusable.
<br>Code Example:
```python
class Car:
  def __init__(self, brand, model, color):  # The __init__ method with arguments
    self.brand = brand
    self.model = model
    self.color = color

# Create Car objects with different attributes
car1 = Car("Toyota", "Camry", "red")
car2 = Car("Honda", "Civic", "blue")

print(car1.brand, car1.model, car1.color)  # Output: Toyota Camry red
print(car2.brand, car2.model, car2.color)  # Output: Honda Civic blue
```
In this example:
* The Car class has an ```__init__``` method that takes three arguments (```brand```, ```model```, and ```color```).
* When we create ```car1``` and ```car2```, we pass different values to the ```__init__ method```, initializing their attributes with unique properties.
In summary, the ```__init__``` method is essential for defining the initial state of objects in Python classes, allowing you to create customized objects with specific attributes.

Example 2:
```python
class Country:
    def __init__(self, name, capital, population, area):
        self.name = name
        self.capital = capital
        self.population = population
        self.area = area

    def display_info(self):
        print(f"Name: {self.name}")
        print(f"Capital: {self.capital}")
        print(f"Population: {self.population} million")
        print(f"Area: {self.area} square km")

# Creating a Country object
canada = Country("Canada", "Ottawa", 37.06, 9.093)
canada.display_info()

Output:

Name: Canada
Capital: Ottawa
Population: 37.06 million
Area: 9.093 square km
```
* In this example, the Country class has an __init__ method that takes four arguments: name, capital, population, and area. These arguments are used to initialize the corresponding attributes of the Country object.
* When we create a new Country object, such as canada = Country("Canada", "Ottawa", 37.06, 9.093), the __init__ method is automatically called to set the initial state of the object.
* The display_info method is then used to print out the information about the Country object.
* The __init__ method is crucial in this example because it allows us to create Country objects with specific initial values for their attributes. Without the __init__ method, we would have to manually set the attributes for each Country object, which would be more error-prone and less efficient.

Why is the ```self``` part always there? What is it for?
* The ```self``` argument in Python class methods is like a pronoun pointing back to the specific object the method is being called on. It allows methods to interact with the data that belongs to that particular object instance. It is there to provide a reference to the current object instance itself. Here's why it's important:
- Methods operate on objects: When you call a method on an object, that method needs a way to access and modify the object's attributes (variables) specific to that instance. ```self``` provides this link.
- Differentiating between objects: Classes can create multiple objects (instances). Without ```self```, methods wouldn't be able to tell which object's attributes they're working with. ```self``` ensures methods work on the correct object's data.
- Imagine a scenario: You have a ```Car``` class with a method ```accelerate```. Without ```self```, the ```accelerate``` method wouldn't know which car's speed to increase. With ```self```, the method can access the speed attribute of the specific ```Car``` object that called the method. eg in Honda example.
- A key point to note: While ```self``` is the convention, it's not strictly a keyword: Technically, you can name the first argument in a method anything you want. You can use any other name as long as it is consistent throughout your code. However, ```self``` is the most commonly used and expected name for the first parameter in instance methods. Following the ```self``` convention improves code readability and makes it easier for other programmers to understand your code.

 8. What are decorators in Python?
 Ans:
* In Python, decorators are a way to modify the behavior of a function or a class without changing its source code. They are a powerful and flexible tool that allows you to add extra functionality to functions or classes in a concise and readable way.
* They are essentially functions that take another function as an argument and return a modified version of it. Why would you want to do that? It allows you to modify the behavior of functions or methods without permanently changing their code. 
* Decorator syntax: The "@" symbol is used to apply the decorator to a function. You place the decorator function name right above the function you want to decorate.

Code Example: 
```python
def logging_decorator(func):
  """Decorator to log function calls."""
  def wrapper(*args, **kwargs):
    print(f"Calling function: {func.__name__}")
    result = func(*args, **kwargs)
    print(f"Function returned: {result}")
    return result
  return wrapper

# Especially this part

@logging_decorator
def say_hello(name):
  """A function that greets someone."""
  return f"Hello, {name}!"

# Call the decorated function
greeting = say_hello("Alice")
print(greeting)  # Output: Calling function: say_hello, Function returned: Hello, Alice!, Hello, Alice!

```
In this example:
* The logging_decorator takes a function as its argument.
* It defines a wrapper function that logs information before and after calling the original say_hello function.
* The @logging_decorator syntax applies the decorator to the say_hello function.

Benefits of using decorators:
* Code reusability: Decorators allow you to encapsulate common functionality into reusable functions. 
* Non-invasive modification: This reduces code duplication and improves maintainability.

Decorators can be used for a variety of purposes, such as:
* Enforcing access control
* Measuring function performance
* Retrying failed function calls


 9. Explain the difference between append() and extend() methods in Python lists.
12. How are exceptions handled in Python?
13. What is the difference between Python 2 and Python 3?
14. What is a Python dictionary?
15. What is a Python generator?
16. What is the difference between range() and xrange() in Python 2?
17. How does memory management work in Python?
18. What is the difference between a shallow copy and a deep copy in Python?
19. Explain the purpose of the ＿str＿ and ＿repr＿ methods in Python.
20. How do you handle file I/O in Python?
21. What are lambda functions in Python?
22. What is the purpose of the if ＿name＿ == "＿main＿": statement in Python?
23. How do you install third-party packages in Python?
24. What are list comprehensions in Python?
25. Explain the difference between == and != operators in Python.
26. What is a Python set and how is it different from a list or tuple?
27. What is the use of the pass statement in Python?
28. How do you iterate over a dictionary in Python?
29. What is the purpose of *args and **kwargs in Python function definitions?
30. What is the difference between instance, class, and static methods in
Python?
28. How do you create simple program that calculates someone’s age using datetime module?
30. Explain the concept of inheritance in Python.
31. How do you handle multi-threading in Python?
32. What is the Global Interpreter Lock (GIL) in Python?
33. What is a context manager in Python?
34. How do you handle JSON data in Python?
35. Explain the differences between ＿getattr() and ＿getattribute()
methods in Python.
36. What are modules and packages in Python?
37. What is the purpose of the ＿init＿ py file in Python packages?
38. How do you handle date and time in Python?
39. What is the purpose of _all… in Python?
40. Explain the difference between os.path.join() and os.path.abspath() in
Python.
41. What is the purpose of the zip() function in Python?
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

# Also check out the Software Engineering Interview questions in this repository.
