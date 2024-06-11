

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

Qn: Can I use these on a list too?


59. What is the purpose of the random module in Python?
60. How do you find the length of a list in Python?
59.Explain the purpose of the classmethod decorator in Python.
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
