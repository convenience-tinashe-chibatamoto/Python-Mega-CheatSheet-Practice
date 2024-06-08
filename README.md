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
* In this example, the ```Country``` class has an ```__init__``` method that takes four arguments: ```name```, ```capital```, ```population```, and ```area```. These arguments are used to initialize the corresponding attributes of the ```Country``` object.
* When we create a new ```Country``` object, such as ```canada = Country("Canada", "Ottawa", 37.06, 9.093)```, the ```__init__ method``` is automatically called to set the initial state of the object.
* The ```display_info``` method is then used to print out the information about the ```Country``` object.
* The ```__init__``` method is crucial in this example because it allows us to create ```Country``` objects with specific initial values for their attributes. Without the ```__init__ method```, we would have to manually set the attributes for each ```Country object```, which would be more error-prone and less efficient.

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
* The ```logging_decorator``` takes a function as its argument.
* It defines a wrapper function that logs information before and after calling the original ```say_hello``` function.
* The ```@logging_decorator``` syntax applies the decorator to the ```say_hello``` function.

Benefits of using decorators:
* Code reusability: Decorators allow you to encapsulate common functionality into reusable functions. 
* Non-invasive modification: This reduces code duplication and improves maintainability.

Decorators can be used for a variety of purposes, such as:
* Enforcing access control
* Measuring function performance
* Retrying failed function calls <br>


 9. Explain the difference between append() and extend() methods in Python lists.
Ans: In Python, the append() and extend() methods are both used to add elements to a list, but they differ in the way they add the elements.<br>
```append():```<br>
* The ```append()``` method is used to add a single element to the end of a list.
* It takes one argument, which is the element you want to add.
* After calling ```append()```, the length of the list increases by 1.<br>
Code Example:
```python
my_list = [1, 2, 3]
my_list.append(4)
print(my_list)  # Output: [1, 2, 3, 4]
```
The ```extend()``` method:<br>
* The ```extend()``` method is used to add multiple elements to the end of a list.
* It takes an iterable (such as a list, tuple, or string) as an argument, and adds all the elements of the iterable to the end of the list.
* After calling ```extend()```, the length of the list increases by the number of elements added.<br>
Code Example:
```python
my_list = [1, 2, 3]
my_list.extend([4, 5, 6])
print(my_list)  # Output: [1, 2, 3, 4, 5, 6]
```
Another Code Example:

```python
fruits = ['apple', 'banana']
fruits.append('cherry')
print(fruits)  # Output: ['apple', 'banana', 'cherry']

```
Choosing between ```append()``` and ```extend()```:
* Use ```append()``` when you want to add a single element to your list.
* Use ```extend()``` when you want to add multiple elements from another iterable to your list.

Qn: What if I want to add an item at the beginning of my my list? What do I use?<br>
Ans: If you want to add an item or multiple items at the beginning of a list in Python, you can use the ```insert()``` method or the ```+``` operator.<br>
The ```insert(): method```
* The ```insert()``` method is used to add an element at a specific index in the list.
* It takes two arguments: the index where the element should be inserted, and the element to be inserted.
* This method shifts all the existing elements at and after the specified index to make room for the new element.<br>
Code Example:
```python
my_list = [2, 3, 4]
my_list.insert(0, 1)
print(my_list)  # Output: [1, 2, 3, 4]
```
Alternatively:
The ```+``` operator:
* You can use the ```+``` operator to concatenate two lists, effectively adding the elements of one list to the beginning of another list.
* This creates a new list and does not modify the original lists.<br>
Code Example 2:
```python
my_list = [2, 3, 4]
new_list = [1] + my_list
print(new_list)  # Output: [1, 2, 3, 4]
```
<br>

10. How are exceptions handled in Python?
Ans: Python handles exceptions using a combination of ```try```, ```except```, and optionally, ```finally``` statements. Here's a breakdown of how they work together:

a. The ```try``` Block:
* This block contains the code that might potentially raise an exception.
* If no exceptions occur within the ```try``` block, the code executes normally, and the program continues.
* Exceptions are are a way to handle errors and unexpected situations that may occur during the execution of a program. When an exception occurs, the normal flow of the program is interrupted, and the interpreter tries to find a suitable exception handler to deal with the problem. This allows you to write more robust and maintainable code.
* It allows you to anticipate and handle errors, provide meaningful feedback to users, and ensure the overall stability and reliability of your application.

b. The ```except``` Block:
* This block defines how to handle exceptions.
* You can have multiple ```except``` blocks to catch different types of exceptions.
* Each ```except``` block specifies the exception type it can handle.
* When an exception occurs within the ```try``` block, Python checks if the exception type matches any of the ```except``` blocks.
* If a match is found, the code within the corresponding ```except``` block executes.<br>
Code Example:
```python
try:
  result = 10 / 0
except ZeroDivisionError:
  print("Oops! Cannot divide by zero.")
```
In this example, the division by zero inside the ```try``` block will raise a ```ZeroDivisionError``` exception. Since we have an ```except``` block for this specific exception type, the program won't crash. Instead, the code within the ```except``` block will print an informative message.<br>
Example 2: Handling Multiple Exceptions at once:
```python
try:
    # Some code
except ValueError:
    print("A value error occurred")
except Exception:
    print("An unexpected error occurred")

# Alternatively, also
except (ValueError, TypeError):
  print("Invalid input type.")
```

c. The ```finally``` Block (Optional):
* The ```finally``` block (if present) always executes after the ```try``` block.
* This block is typically used to release resources or perform cleanup tasks, regardless of whether an exception occurred.
* The ```finally``` block is used to ensure that certain code is executed, regardless of whether an exception was raised or not.
* This is useful for cleaning up resources, such as closing a file or a database connection.<br>
Code Example:
```python
try:
    file = open("file.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("File not found")
finally:
    file.close()
```

Raising an exception deliberately:
* The ```raise``` statement allows you to deliberately raise an exception:
```python
def check_age(age):
  if age < 18:
    raise ValueError("Age must be 18 or older.")
```

Custom Exceptions
* You can define your own custom exception types by creating a new class that inherits from the ```Exception``` class or one of its subclasses.
* This allows you to create more specific and meaningful exception types for your application.<br>
Code Example:
```python
class CustomError(Exception):
    pass

try:
    # Some code that might raise a CustomError
except CustomError:
    print("A custom error occurred")
```
<br>

11. What is the difference between Python 2 and Python 3?
Ans: Python 2 and Python 3 are two major versions of the Python programming language with significant differences.
* While Python 2 was the dominant version for a long time, Python 3 is now the standard and recommended choice for new projects. Here's a breakdown of some key differences:
* Python 2: Uses a ```print``` statement as a built-in statement. Python 3: Uses print as a function ```print("Hello, world!")```.
*  Division: Python 2: Integer division (```/```) returns an integer if both operands are integers (e.g., ```10 / 2``` evaluates to ```5```). Python 3: Division (```/```) always returns a ```float``` (e.g., ```10 / 2``` evaluates to ```5.0```). You can use ```//``` for integer division that leads to integer results.
*  Major.minor.patch
*  Python 3 has several performance improvements, such as more efficient memory management and faster string operations.
*  Python 3 is the actively developed version with a larger and more active community. Python 2 reached its end-of-life in 2020 and is no longer officially supported. ((Python 2.7) was the last iteration, having been in use since 2010.
*  Python 3 has a larger standard and third party library than Python 2 <br>

14. What is a Python dictionary?
Ans: A Python dictionary is a built-in data structure that allows you to store key-value pairs. It is an unordered collection of items, where each item has a unique key and an associated value.
* Unordered means the items are not stored in a particular order. You cannot rely on the order of the items when iterating through a dictionary. (unlike what you can do with a list)<br>

Here's a summary of key points about dictionaries:
* Storage: They use key-value pairs to store data.
* Mutable: You can change the dictionary after it's created by adding, removing, or modifying key-value pairs.
* Keys: Keys must be unique and immutable (cannot be changed) - common data types for keys include strings, numbers, or tuples.
* Values: Values can be any data type - numbers, strings, lists, or even other dictionaries.
* Mutable: You can change the dictionary after it's created by adding, removing, or modifying key-value pairs.
* Ordered (Python 3.7+) : Unlike lists, the order in which items are added is not significant and cannot be relied upon when iterating through a dictionary.
* You generally want to use a dictionary for storing heterogeneous items, and a list when dealing with homogenous items.<br>
Code example:
```python
person = {
    "name": "John Doe",
    "age": 35,
    "city": "New York"
# You can access the values in a dictionary using the corresponding keys, like this:

print(person["name"])  # Output: "John Doe"
print(person["age"])   # Output: 35
}
```
Code Example 2:

```python
# Create a dictionary to store information about a book
book = {
  "title": "The Hitchhiker's Guide to the Galaxy",
  "author": "Douglas Adams",
  "year": 1979,
  "genre": "Science Fiction Comedy"
}

# Accessing a value by its key
title = book["title"]
print(f"The book title is: {title}")  # Output: The book title is: The Hitchhiker's Guide to the Galaxy

# Updating an existing value
book["year"] = 2005  # Update the year the book was published
print(f"The book was first published in {book['year']}")  # Output: The book was first published in 2005 

# Adding a new key-value pair
book["characters"] = ["Arthur Dent", "Ford Prefect"]
print(f"Some of the characters are: {book['characters']}")  # Output: Some of the characters are: ['Arthur Dent', 'Ford Prefect']

```
<br>

12. What is a Python generator?<br>
Ans: A Python generator is a special type of function that allows you to generate a sequence of values, one at a time, rather than creating and returning a complete list all at once. Generators are useful when you need to work with large or infinite sequences of data, as they can save memory by only generating the values that are needed, rather than storing the entire sequence in memory.
* Here's a breakdown of key points about Python generators:
* Function-like, but use ```yield``` Keyword: Defined similarly to regular functions using ```def```, but use the ```yield``` keyword instead of ```return```. 
* Instead of using the ```return``` keyword to return a value, generators use the ```yield``` keyword. 
* Lazy Evaluation: Generators use lazy evaluation, which means they only generate the next value in the sequence when it is requested, rather than generating the entire sequence upfront. This allows the generator function to pause its execution, save its state, and resume later when the next value is requested. The function remembers its state between yields, allowing you to pick up where it left off.
* Memory Efficient: Generators are memory-efficient because they only store the state needed to generate the next value, rather than storing the entire sequence in memory. This is especially beneficial for large datasets.
* Iterability: Generators are iterable, which means you can use them in ```for``` loops, list comprehensions, and other constructs that work with iterables.<br>
Code Example 1:
```python
def square_numbers(n):
  """
  Generator that yields squares up to a given number n.
  """
  for i in range(n):
    yield i * i  # Yield the square of the current number

# Get an iterator object from the generator function
numbers = square_numbers(5)

# Iterate through the generated values using a for loop
for num in numbers:
  print(num)  # Output: 0 1 4 9 16

```
Code Example 2:
```python
# An example of a simple generator function that generates the first n Fibonacci numbers:

def fibonacci(n):
    a, b = 0, 1
    for i in range(n):
        yield a
        a, b = b, a + b
# You can use this generator like this:

fib_gen = fibonacci(10)
for num in fib_gen:
    print(num)

# This will output the first 10 Fibonacci numbers, one at a time, without storing the entire sequence in memory.
```
Generators are a powerful tool in Python, and they are often used in data processing, file I/O, and other applications where memory usage is a concern.<br>

13. What is the difference between ```range()``` and ```xrange()``` in Python 2? <br>
Ans: ```xrange()```'s functonality has been incorporated into ```range()``` in Python 3. But here's something to note: ```xrange()``` did not allow list slicing.
* ```range(n)```: This returns a list object. You can perform list operations like slicing, indexing, and applying list comprehension on the returned list unlike ```xrange()```. ```range``` in Python 3, it returns an iterator object that generates numbers on demand, making it memory-efficient.
* So, if you're coding for both Python 2 and 3, it's generally recommended to use ```range()``` for consistency and better memory management.<br>

14. How does memory management work in Python?<br>
Ans:
* Python's memory management is handled automatically by the Python interpreter, using a combination of several techniques like object caching and garbage collection. Python takes care of memory management automatically. (unlike in other languages like C and C++)
* This frees you, the programmer, from the burden of manually allocating and deallocating memory for your objects. Python's memory management system is designed to be efficient and user-friendly, allowing developers to focus on writing code without having to worry about the low-level details of memory management.<br>

15. What is the difference between a shallow copy and a deep copy in Python?<br>
Ans:
Shallow Copy:
* A shallow copy creates a new object that contains references to the same elements as the original object.
* When you modify an element in the new object, the corresponding element in the original object is also modified, and vice versa.
* Shallow copies are created using the ```copy()``` method or the slice operator ```[:]```.
* Shallow copies are useful when the elements in the object are immutable (e.g., numbers, strings, tuples), but can lead to unexpected behavior when the elements are mutable (e.g., lists, dictionaries, custom objects).

Deep Copy:
* A deep copy creates a new object with a completely independent copy of the data from the original object.
* When you modify an element in the new object, the original object is not affected, and vice versa.
* Deep copies are created using the ```deepcopy()``` function from the copy module.
* Deep copies are useful when the elements in the object are mutable and you want to ensure that changes in the new object do not affect the original object.<br>
Code Example:
```python
import copy

# Shallow copy
original_list = [[1, 2], [3, 4]]
shallow_copy = copy.copy(original_list)

print("Original list:", original_list)
print("Shallow copy:", shallow_copy)

shallow_copy[0][0] = 10
print("Original list after modification:", original_list)
print("Shallow copy after modification:", shallow_copy)

# Deep copy
original_list = [[1, 2], [3, 4]]
deep_copy = copy.deepcopy(original_list)

deep_copy[0][0] = 10
print("Original list after modification:", original_list)
print("Deep copy after modification:", deep_copy)

# Output

Original list: [[1, 2], [3, 4]]
Shallow copy: [[1, 2], [3, 4]]
Original list after modification: [[10, 2], [3, 4]]
Shallow copy after modification: [[10, 2], [3, 4]]
Original list after modification: [[1, 2], [3, 4]]
Deep copy after modification: [[10, 2], [3, 4]]
```
As you can see, in the shallow copy example, modifying the first element of the inner list in the shallow copy also modifies the corresponding element in the original list. In the deep copy example, modifying the first element of the inner list in the deep copy does not affect the original list.

16. Explain the purpose of the ＿str＿ and ＿repr＿ methods in Python.<br>
Ans: In Python, the``` __str__ ```and ```__repr__``` methods are special methods that control how objects are converted into strings. They might seem interchangeable at first, but they serve different purposes:

* ```__str__()``` (string representation): This method is designed to return a human-readable representation of an object. It's meant to be informative for the user and provide a clear understanding of the object's content. For instance, it might display a date object in a user-friendly format like "2024-06-08". (it's for users)
* ```__repr__()``` (representation): This method aims to return an unambiguous string representation that can be used to recreate the object. It's geared towards developers and debugging. (it's for developers)
* You don't call these methods directly. Instead, Python uses them behind the scenes when you use functions like ```str()``` or ```print()```. However, it's good practice to define both ```__str__``` and ```__repr__``` in your custom classes to control how your objects are represented.

17. How do you handle file I/O in Python?<br>
Ans: In Python, file I/O (Input/Output) is handled using the built-in ```open()``` function.
* It takes two main arguments: the filename and the mode. filename: The name (including path if necessary) of the file you want to work with. mode: This argument specifies how you intend to interact with the file. Different modes are available such as:
* ```"r"``` (read): Opens the file for reading. This is the default mode if no mode is specified.
* ```"w"``` (write): Opens the file for writing. Existing content will be erased!
* ```"a"``` (append): Opens the file for appending content to the end.
* ```"x"``` (create): Creates a new file and opens it for writing. Fails if the file already exists.
* ```"b"``` (binary): Used for working with binary files (e.g., images).
* ```'r+'```: Read and write mode.

Reading from a File:
* Use the read(), readline(), or readlines() methods to read data from the file.
* read() reads the entire file as a single string.
* readline() reads a single line from the file.
* readlines() reads all the lines in the file and returns them as a list of strings.<br>
Code Example:
```python
with open('data.txt', 'r') as myfile:
    content = myfile.read()
    print(content)
```

Writing to a File:
* Use the write() method to write data to the file.<br>
Code Example:
```python
with open("data.txt", "w") as myfile:
  myfile.write("This is some new text for the file.")
```

22. What are lambda functions in Python?
23. What is the purpose of the if ＿name＿ == "＿main＿": statement in Python?
24. How do you install third-party packages in Python?
25. What are list comprehensions in Python?
26. Explain the difference between == and != operators in Python.
27. What is a Python set and how is it different from a list or tuple?
28. What is the use of the pass statement in Python?
29. How do you iterate over a dictionary in Python?
30. What is the purpose of *args and **kwargs in Python function definitions?
31. What is the difference between instance, class, and static methods in
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
