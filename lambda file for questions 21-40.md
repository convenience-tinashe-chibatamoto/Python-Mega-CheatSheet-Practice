
51. What is the purpose of the enumerate() function in Python?<br>
Ans: The purpose of the ```enumerate()``` function in Python is to iterate over a sequence (such as a list, tuple, or string) while keeping track of both the index and the value of each item in the sequence.
* It returns an iterator that produces pairs of index and value during each iteration, making it useful for tasks where you need to access both the position and the value of each item in the sequence<br>
Code Example:
```python
# Without enumerate

fruits = ['apple', 'banana', 'cherry']

# Iterate over the list of fruits
for fruit in fruits:
    print(fruit)
# Output:
# apple
# banana
# cherry

# Now with enumerate: Iterate over the list of fruits with indices
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
# Output:
# 0: apple
# 1: banana
# 2: cherry

# See, it provides the index and the value in each iteration
# Index: 0, Value: apple
# Index: 1, Value: banana
# Index: 2, Value: cherry
```

* The enumerate() function can also take an optional ```start``` parameter to specify the starting index (default is ```0```):<br>
Code Example:
```python
fruits = ['apple', 'banana', 'cherry']

for index, fruit in enumerate(fruits, start=1):
    print(f"{index}: {fruit}")
# Output:
# 1: apple
# 2: banana
# 3: cherry
```
* The ```enumerate()``` function is particularly useful when you need to access both the index and the value of elements in an iterable, such as when you're working with a list of items and need to display their positions or use the indices for some other purpose.

52. Explain the difference between del, remove(), and pop() methods for removing elements from lists in Python.<br>
Ans: ```del```, ```remove()```, and ```pop()``` are three main ways to remove elements from a list. Here's the difference between them:<br><br>

```del```:
* It is a keyword in Python, not a specific list method.
* It can be used to delete a range of elements by slicing the list.
* Removes the element at the specified index or the entire slice specified.
* Raises an ```IndexError``` if the index is out of range.
* It can be used to delete the entire list by not specifying an index.<br>
Code Example:
```python
my_list = ["apple", "banana", "cherry", "orange"]

# Remove element at index 2 (cherry)
del my_list[2]
print(my_list)  # Output: ['apple', 'banana', 'orange']

# Remove elements from index 1 to 3 (banana and cherry)
del my_list[1:3]
print(my_list)  # Output: ['apple', 'orange']

```

```remove()```:
* Removes the first occurrence of a specified value from the list.
* It raises a ```ValueError``` if the value is not found in the list.
* Just like the ```del``` keyword, it returns nothing.<br>
Code Example:
```python
fruits = ["apple", "banana", "cherry", "banana"]
fruits.remove("banana")  # Removes the first occurrence of "banana"
print(fruits)  # Output: ["apple", "cherry", "banana"]

# Trying to remove a non-existent element will raise a ValueError
try:
 fruits.remove("kiwi")
except ValueError:
  print("Value 'kiwi' not found in the list")
```

```pop()``` method
* It is used to remove and return an element from the list.
* If no index is specified, it removes and returns the last element in the list.
* If an index is specified, it removes and returns the element at that index.
* It raises an ```IndexError``` if the index is out of range.<br>
Code Example:
```python
numbers = [1, 2, 3, 4, 5]
last_element = numbers.pop()  # Removes and returns the last element (5)
print(last_element)  # Output: 5
print(numbers)  # Output: [1, 2, 3, 4]

middle_element = numbers.pop(2)  # Removes and returns the element at index 2 (3)
print(middle_element)  # Output: 3
print(numbers)  # Output: [1, 2, 4]
```
Usage:
* Use ```del``` when you want to remove elements by index or slice.
* Use ```remove()``` when you want to remove the first occurrence of a specific value.
* Use ```pop()``` when you want to remove an element by index and also get the value back. Be cautious about using ```pop()``` without an argument as it removes the last element and might not be what you intend.<br>

53. How do you convert a string to lowercase or uppercase in Python?<br>
Ans: To convert a string to lowercase or uppercase in Python, you can use the built-in methods lower() and upper(), respectively.<br><br>
Converting to Lowercase
* Using the ```lower()``` method:
* The ```lower()``` method converts all uppercase characters in a string into lowercase characters and returns the result.<br>
Code Example:
```python
message = 'PYTHON IS fun'
print(message.lower())  # Output: python is fun
```

Converting to Uppercase
* Using the ```upper()``` method:
* The ```upper()``` method converts all lowercase characters in a string into uppercase characters and returns the result.<br>
Code Example:
```python
message = 'python is fun'
print(message.upper())  # Output: PYTHON IS FUN
```
* Both in use together:<br>
Code Example:
```python
# Original string
s = 'pYThon proGramminG laNguAge'

# Convert to lowercase
s_lower = s.lower()
print(s_lower)  # Output: python programming language

# Convert to uppercase
s_upper = s.upper()
print(s_upper)  # Output: PYTHON PROGRAMMING LANGUAGE
```

* Additionally, you can use the ```capitalize()``` method to capitalize the first character of a string, and the ```title()``` method to capitalize the first character of each word in a string:<br>
Code Example:
```python
text = "hello, world!"
capitalized_text = text.capitalize()
print(capitalized_text)  # Output: Hello, world!

text = "hello, world!"
title_text = text.title()
print(title_text)  # Output: Hello, World!
```
* These string manipulation methods are very useful for formatting and standardizing text data in your Python applications.<br>


54. What is the purpose of the sys module in Python?<br>
Ans: The main purpose of the ```sys``` module is to provide a way to interact with the Python interpreter and Python runtime environment itself.
* You can control the interpreter's behavior using ```sys```. For instance, you can exit the script with specific exit codes or handle standard streams (input, output, error) in a custom way.
* Contains ```argv```: A list of command-line arguments passed to the Python script. The ```sys.argv``` attribute is a list containing the arguments passed to your Python script when you run it from the command line. This allows your script to be flexible and adapt based on user input.
* The ```sys``` module is essential for interacting with the Python runtime environment and is commonly used in various applications, including command-line scripts and development tools.

<br>

55. How do you sort a dictionary by its values in Python?<br>
Ans: 


58. Explain the purpose of the with statement in Python.
59. How do you check if a key exists in a dictionary in Python?
60. What is the purpose of the random module in Python?
61. How do you find the length of a list in Python?
59.Explain the purpose of the classmethod decorator in Python.
62. How do you round a floating-point number to a specified number of decimal places in Python?
63. What is the purpose of the isinstance() function in Python?
64. How do you concatenate two lists in Python?
65. Explain the purpose of the filter() function in Python.
66. How do you create a dictionary from two lists in Python?
67. What is the purpose of the os module in Python?
68. How do you check if a string contains a substring in Python?
69. Explain the use of the assert statement in Python.
70. How do you create an empty list, tuple, or dictionary in Python?
71. What is the purpose of the sum() function in Python?
72. How do you convert a list to a string in Python?
73. Explain the difference between shallow and deep copy in Python dictionaries.
74. How do you convert a string to an integer or a float in Python?
75. What is the purpose of the format() method in Python strings?
76. How do you check if a file exists in Python?
77. Explain the difference between os.path.exists() and os.path.isfile() in Python
78. What is the purpose of the pickle module in Python?
79. How do you get the current working directory in Python?
80. Explain the difference between a list and a tuple comprehension in Python…
81. What is the purpose of the is operator in Python?
82. How do you convert a list of strings to a single string in Python?
83. Explain the use of the reduce() function in Python.
84. How do you convert a string to a list in Python?
85. What is the purpose of the min() and max() functions in Python?
86. How do you convert a string to a datetime object in Python?
87. Explain the difference between shallow and deep copy in Python lists.
88. What is the purpose of the locals() and globals() functions in Python?
89. How do you write a multiline string in Python?
90. What is the purpose of the split() method in Python strings?
91. How do you check if a number is even or odd in Python?
92. Explain the purpose of the bytes and bytearray data types in Python.
93. What is the purpose of the round() function in Python?
94. How do you create a dictionary with default values in Python?
95. Explain the difference between os.path.isdir() and os.path.isfile() in Python.
96. What is the purpose of the finally block in Python exception handling?
97. How do you reverse a list in Python?
98. What is the purpose of the del statement in Python?
99. Explain the difference between the os.system() and subprocess.run() functions in Python.
100. How do you split a string into a list of substrings in Python?
101. What is the purpose of the try, except, else, and finally blocks in Python?
102. How do you create a shallow copy of a list in Python?<br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
