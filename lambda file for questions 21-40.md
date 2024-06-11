

55. How do you sort a dictionary by its values in Python?<br>
Ans: In Python, you can sort a dictionary by its values using the ```sorted()``` function alongside a ```lambda``` function to define the sorting criteria.
* The ```sorted()``` function takes an iterable (in this case, the items() method of the dictionary) and returns a sorted list of tuples.
* If you want to get the sorted dictionary back, you can convert the sorted list of tuples back into a dictionary using the ```dict()``` function. <br>
Code Example:
```python
# Example dictionary
my_dict = {'apple': 2, 'banana': 1, 'cherry': 3}

# Sort the dictionary by values
sorted_dict = sorted(my_dict.items(), key=lambda x: x[1])

# Print the sorted dictionary
print(sorted_dict)

# Output

# [('banana', 1), ('apple', 2), ('cherry', 3)]

# Converting the sorted list of tuples back into a dictionary using the dict() function:

sorted_dict = dict(sorted(my_dict.items(), key=lambda x: x[1]))
print(sorted_dict)

# Output

# {'banana': 1, 'apple': 2, 'cherry': 3}
```
You can also sort the dictionary in reverse order (i.e. descending order) by adding the ```reverse=True``` parameter as the third parameter to the sorted() function:<br>
Code Example:
```python
sorted_dict = sorted(my_dict.items(), key=lambda x: x[1], reverse=True)
print(sorted_dict)

# Output

# [('cherry', 3), ('apple', 2), ('banana', 1)]
```
<br>

56. Explain the purpose of the with statement in Python.<br>
Ans: The ```with``` statement in Python is a context manager used for resource management.
* It ensures that resources are properly acquired and released in a specific order, even in the presence of exceptions.
* This helps prevent resource leaks and makes your code cleaner, secure and more readable.<br>
Code Example: File I/O
```python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

Example 2: Database Operations
```python
with sqlite3.connect('db.db') as connection:
    cursor = connection.cursor()
    cursor.execute("SELECT * FROM table")

```
* Without the ```with``` statement, you would have to explicitly call the ```close()``` method on the file object to ensure that it is properly closed.
* The ```with``` statement makes the code more concise and easier to read, and it also helps prevent common mistakes, such as forgetting to close the file or failing to handle exceptions properly.

<br>
57. How do you check if a key exists in a dictionary in Python?<br>
Ans: There are several ways to check if a key exists in a dictionary, but here's my favourite two:

Using ```in``` <br>
* This is the simplest and most straightforward way to check for key existence.
* The ```in``` operator returns ```True``` if the key is present in the dictionary, and ```False``` otherwise.<br>
Code Example:
```python
my_dict = {'apple': 2, 'banana': 1, 'cherry': 3}

if 'apple' in my_dict:
    print("The key 'apple' exists in the dictionary.")
else:
    print("The key 'apple' does not exist in the dictionary.")

# Output

# The key 'apple' exists in the dictionary.
```
Using the ```get()``` method:
* The ```get()``` method returns the value associated with the key if the key is present in the dictionary, or ```None``` if the key is not present. You can also provide a default value to be returned if the key is not found.
* It takes two arguments: The key to be checked, and an optional default value to return if the key is not found.<br>
Code Example:
```python
my_dict = {'apple': 2, 'banana': 1, 'cherry': 3}

if my_dict.get('apple') is not None:
    print("The key 'apple' exists in the dictionary.")
else:
    print("The key 'apple' does not exist in the dictionary.")

#  You can also provide a default value to be returned if the key is not found:

value = my_dict.get('pear', 0)
print(value)  # Output: 0 (since 'pear' is not a key in the dictionary)
```

<br>

Qn: Can I use these on a list too?<br>
Ans: Yes,you can check if a key exists in a list using the ```in``` operator. The ```in``` operator checks if a value is present in any sequence (such as a list, tuple, or string) and returns ```True``` if it is, and ```False``` otherwise.<br>
Code Example:
```python
my_list = [1, 2, 3, 'apple', 'banana']

# Check if 3 is in the list
if 3 in my_list:
    print("3 is in the list")
else:
    print("3 is not in the list")

# Check if 'apple' is in the list
if 'apple' in my_list:
    print("'apple' is in the list")
else:
    print("'apple' is not in the list")

# Check if 'orange' is in the list
if 'orange' in my_list:
    print("'orange' is in the list")
else:
    print("'orange' is not in the list")

# 3 is in the list
# 'apple' is in the list
# 'orange' is not in the list
```

* Note that the ```in``` operator checks for the presence of the value, not the index or position of the value in the list. If you want to check the index of a value in the list, you can use the ```index()``` method.
<br>

58. What is the purpose of the random module in Python?<br>
Ans: The ```random``` module in Python is a built-in library that provides functions for generating pseudo-random numbers and performing various random operations. These numbers are not truly random, but they are generated using a deterministic algorithm that produces an unpredictable sequence.
* Simulations: It can be used to simulate random events, such as dice rolls, coin flips, or other probabilistic processes.
* Shuffling and sampling: It provides functions to shuffle sequences, such as lists or strings, and to select random elements from a sequence.
* Security and cryptography: It can be used to generate random numbers for security-related applications, such as password generation or cryptographic key generation, although for more serious cryptographic applications, the secrets module is generally preferred.
* Game development: In game development, the ```random``` module can be used to introduce randomness and unpredictability, which can make games more engaging and challenging.<br>
Code Example:
```python
import random

# Roll a 6-sided die
dice_roll = random.randint(1, 6)
print("You rolled a", dice_roll)

# This will output a random number between 1 and 6, representing the result of the dice roll.
```

Some of the commonly used functions in the ```random``` module include:
* ```random()```: Generates a random floating-point number between ```0``` and ```1```.
* ```randint(a, b)```: Generates a random integer between ```a``` and ```b``` (inclusive).
* ```shuffle(seq)```: Shuffles the elements of the sequence ```seq``` in-place. Meaning (the meaning applies to all programming, not just here) that the operation modifies the original sequence (list, tuple, etc.) directly, without creating a new copy of the sequence.
* ```sample(seq, k)```: Selects ```k``` unique random elements from the sequence ```seq```.

59. How do you find the length of a list in Python?<br>
Ans: There are multiple ways for finding the length of a list in Python, but using the built-in ```len()``` function is the most straightforward, efficient, and recommended approach.<br>
Code Example:
```python
my_list = [1, 2, 3, 4, 5]
length = len(my_list)
print(length)  # Output: 5
```

* You can use the ```len()``` function with any iterable object in Python, not just lists. For example, you can also use it with strings, tuples, and dictionaries:

```python
my_string = "Hello, world!"
my_tuple = (1, 2, 3, 4, 5)
my_dict = {'apple': 1, 'banana': 2, 'cherry': 3}

print(len(my_string))  # Output: 13
print(len(my_tuple))   # Output: 5
print(len(my_dict))    # Output: 3
```
<br>

60.Explain the purpose of the classmethod decorator in Python.<br>
Ans: The ```@classmethod``` decorator allows the methods to operate on the class itself, rather than on a specific instance of the class.
* This means that the method can be called on the class itself, without the need to create an instance of the class.
* The main purpose of the ```@classmethod``` decorator is to provide a way to create alternative constructors or utility functions that are related to the class, but don't necessarily need to be tied to a specific instance of the class.<br>
Code Example:

```python
class Circle:
  pi = 3.14159  # Class attribute

  @classmethod
  def from_radius(cls, radius):
    """Creates a Circle object from a given radius."""
    return cls(radius)  # Call the constructor using cls

  def __init__(self, radius):
    self.radius = radius

  def area(self):
    return Circle.pi * self.radius * self.radius  # Access class attribute

circle1 = Circle.from_radius(5)
circle2 = circle1.from_radius(3)  # Both calls create circles using the classmethod

```

* In this example, the ```from_radius``` classmethod is used as an alternative constructor to create ```Circle``` objects from a ```radius``` value. It demonstrates how classmethods can be called using both the class and an instance.
* Classmethods can be reused across different instances of the class, promoting code reusability.

<br>           


61. How do you round a floating-point number to a specified number of decimal places in Python?
62. What is the purpose of the isinstance() function in Python?
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
