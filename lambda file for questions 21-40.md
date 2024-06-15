
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

73. What is the purpose of the format() method in Python strings?<br.
Ans: The ```format()``` method in Python strings is used to insert values into a string.
* It provides a flexible and powerful way to format and insert values into a string, making it easier to create dynamic and customizable text output.<br>
Code Example:

```python
# Example Usages

name = "Alice"
age = 25
print("My name is {} and I'm {} years old.".format(name, age))
# Output: My name is Alice and I'm 25 years old.


print("{} is {}.".format("Python", "awesome"))
# Output: Python is awesome.

print("I love {language} and it's {adjective}.".format(language="Python", adjective="awesome"))
# Output: I love Python and it's awesome.


pi = 3.14159
print("The value of pi is {:.2f}".format(pi))
# Output: The value of pi is 3.14

# Nested formatting
person = {"name": "Alice", "age": 25}
print("My name is {0[name]} and I'm {0[age]} years old.".format(person))
# Output: My name is Alice and I'm 25 years old.
```

* While ```format()``` is a useful tool, it's generally recommended to use ```f-strings``` (introduced in Python 3.6) for most modern string formatting needs. F-strings provide a more concise and readable syntax.

<br>
74. How do you check if a file exists in Python?<br>
Ans: There are two main ways to check if a file exists in Python:

Using the ```os.path.exists()``` function from the ```os``` module:
* This is the more widely used approach.
* You need to import the ```os``` module then specify the path as a string.
* ```os.path.exists(file_path)``` takes the path to the file as an argument and returns ```True``` if the file exists, ```False``` otherwise.<br>
Code Example:
```python
import os

file_path = "path/to/your/file.txt"
if os.path.exists(file_path):
    print("The file exists.")
else:
    print("The file does not exist.")
```

Using the ```pathlib``` module:
* It offers a more modern and object-oriented way to handle file paths, especially when dealing with multiple files and directories.
* ```file_path.exists()``` checks if the ```path``` object refers to an existing file and returns ```True``` if it does, ```False``` otherwise.
Code Example:
```python
from pathlib import Path

file_path = "path/to/your/file.txt"
if Path(file_path).exists():
    print("The file exists.")
else:
    print("The file does not exist.")
```

* Both approaches can handle relative and absolute paths.

Note that:
* Both methods only check for the existence of the path, not necessarily if it's a file or a directory. You can use functions like ```os.path.isfile()``` or ```Path.is_file()``` for more specific checks.
* However, in almost all conceivable cases, it makes sense to assume that a filepath wouldn't exist if there was no file for it to reference. In reality, there's actually no path to a non-existent file, so the path is valid proof of a file's existence.
* These methods that use ```.isfile``` check for existence based on file system permissions. If you don't have permission to access the file, it might return ```False``` even if the file exists, so just checking the path makes better sense.

<br>

75. Explain the difference between os.path.exists() and os.path.isfile() in Python<br>
Answer is just above, on 74. But to recap, here it is again:
* Use ```os.path.exists()``` when you only need to know if a path refers to any existing entry in the file system (file or directory).
* Use ```os.path.isfile()``` when you specifically need to confirm the path points to a regular file and not a directory or another file type. Note that file permissions apply here too. And emphasis on "regular" file.

Qn: I see emphasis on "regular" file. What does that mean? What is, and what isn't, a regular file?<br>
Ans:
* In the context of computer file systems, a regular file is the most basic type of file. It's a linear sequence of bytes that stores data and can be accessed sequentially. It's the kind of file you typically use to store text documents, images, videos, executable programs, etc.
* Here are some examples of regular files:Text files (.txt, .html, .py), Image files (.jpg, .png, .bmp), Document files (.docx, .pdf), Executable programs (.exe on Windows, .out or .sh on Unix-based systems), Video files (.mp4, .avi), etc etc.<br>

In contrast, there are other types of files that are not considered "regular files" in the file system context. These include: 
* Directories: Directories (or folders) are not regular files. They are special types of files that serve as containers for other files and directories, providing a hierarchical structure to the file system.
* Device files: Device files, also known as special files or character devices, represent physical or logical devices in the file system, such as hard drives, printers, or network interfaces. They are not regular data files.
* Symbolic links: Symbolic links (or symlinks) are special files that act as pointers to other files or directories, allowing you to access the target file or directory through the symbolic link. They don't store data themselves but act as references to the actual location of the data.
* Named pipes: Named pipes are a type of special file used for inter-process communication, allowing data to be passed between processes.
* Sockets: Sockets are a type of special file used for network communication, allowing processes to exchange data over a network.<br>

* In summary, "regular files" refer to the most common type of files that contain arbitrary data (these are the types of files that most users work with on a daily basis), as opposed to other specialized file types found in file systems.

<br>

76. What is the purpose of the pickle module in Python?
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
