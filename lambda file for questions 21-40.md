
66. How do you check if a string contains a substring in Python?<br>
Ans: There are three main ways to check if a substring exists within a string in Python:<br>

Using the ```in``` operator:
* This is the simplest and most efficient way to check for a substring.
* The ```in``` operator returns ```True``` if the substring is found within the string, and ```False``` otherwise.<br>
Code Example:

```python
my_string = "This is a string"
substring = "is"

if substring in my_string:
  print("Substring found!")
else:
  print("Substring not found.")

# Output: Substring found!

# Another Example

string = "Hello, world!"
if "world" in string:
    print("Substring found")
else:
    print("Substring not found")

# Output: Substring found
```

Using the ```find()``` method:

```python
my_string = "This is a string"
substring = "is"

index = my_string.find(substring)

if index != -1:
  print("Substring found at index", index)
else:
  print("Substring not found.")

# Output: Substring found at index 2


# Another Example:

string = "Hello, world!"
if string.find("world") != -1:
    print("Substring found")
else:
    print("Substring not found")

# Output: Substring found
```

Using regular expressions (case-insensitive):

```python
import re

my_string = "This is a String"
substring = "is"

matches = re.findall(substring, my_string, flags=re.IGNORECASE)

if matches:
  print("Substring found:", matches)
else:
  print("Substring not found.")

# Output: Substring found: ['is', 'IS']
```

* All three methods achieve the goal.
* The ```in``` operator simply confirms its presence, while ```find()``` provides the starting index, and regular expressions with the ```re.IGNORECASE``` flag identify all occurrences regardless of case.


<br>

67. Explain the use of the assert statement in Python.
68. How do you create an empty list, tuple, or dictionary in Python?
69. What is the purpose of the sum() function in Python?
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
