90. Explain the purpose of the bytes and bytearray data types in Python.<br>
Ans: In Python, the ```bytes``` and ```bytearray``` data types are used to work with binary data, such as files, network packets, or other types of raw data.
* The ```bytes``` data type represents an immutable sequence of bytes. This means you cannot modify the elements of a bytes object once it's created.
* It is commonly used or storing binary data like image files, compressed data, or network data packets.
*  The ```bytearray``` data type represents a mutable sequence of bytes. This means you can modify the elements of a bytearray object after it's created.
*  It is commonly used When you need to manipulate binary data dynamically, such as building or modifying binary data before writing it to a file or sending it over a network.<br>
Code Example:
```python
my_bytes = b'Hello, World!'

my_bytearray = bytearray(b'Hello, World!')
my_bytearray[7:12] = b'Python'  # Individual bytes within a bytearray object can be accessed and modified using indexing and slicing.
print(my_bytearray)  # Output: bytearray(b'Hello, Python!')

Code Example 2:
# Create a bytes object from a string literal
message_bytes = b"This is a secret message!"

# Print the bytes object (shown as characters due to encoding)
print("bytes object:", message_bytes)

# Accessing elements (immutable - attempt to modify will raise TypeError)
# message_bytes[0] = ord('B')  # This line will cause an error

# Create a bytearray from a list of integers
image_data = bytearray([0xFF, 0x00, 0x00, 0x7F])  # Sample red color data

# Print the bytearray content in hexadecimal format
print("bytearray content (hex):", image_data.hex())

# Modify elements of the bytearray (mutable)
image_data[0] = 0x3F  # Change red intensity to a darker shade

# Print the modified bytearray content
print("Modified bytearray content (hex):", image_data.hex())

# Convert bytearray to bytes object (optional)
converted_bytes = bytes(image_data)
print("Converted bytearray to bytes:", converted_bytes)

```
* We create a ```bytes``` object named ```message_bytes``` using a string literal with the ```b``` prefix. This represents a fixed sequence of bytes for the message.
* We try to access and modify an element of ```message_bytes``` (commented out). Since it's immutable, this will raise a ```TypeError```.

The main use cases for ```bytes``` and ```bytearray``` in Python include:
* File I/O: Reading and writing binary files, such as images, audio files, or other types of data.
* Network communication: Sending and receiving raw binary data over a network, such as TCP/IP packets or HTTP requests/responses.
* Cryptography and security: Handling and manipulating encrypted data, such as hashes, signatures, or encryption keys.
* Data processing: Working with binary data formats, such as serialized data or machine learning models.

When to use which:
* Use ```bytes``` when you have fixed binary data that you don't need to modify. It's more memory-efficient and secure since it's immutable.
* Use ```bytearray``` when you need to create or modify binary data during your program's execution.
* They are their own unique data types.<br>

In summary, the ```bytes``` and ```bytearray``` data types in Python provide a way to work with binary data, which is essential for many low-level programming tasks and system-level operations.

<br>
91. What is the purpose of the round() function in Python?<br>
Ans: The ```round()``` function in Python is used to round a number to a specified number of decimal places.
* It takes two arguments: ```number``` (required): The number you want to round which can be an integer or a floating-point number; ```ndigits``` (optional): The number of decimal places to round the number to. If not specified, it defaults to 0, and the number is rounded to the nearest integer.<br>
Code Example:

```python
# Rounding to the nearest integer
print(round(3.14159))  # Output: 3
print(round(4.6))      # Output: 5

# Rounding to a specific number of decimal places
print(round(3.14159, 2))  # Output: 3.14
print(round(1.2345, 3))   # Output: 1.235
print(round(1.2345, 0))   # Output: 1.0

# Rounding negative numbers
print(round(-3.14159, 2))  # Output: -3.14

# Another Example
# Round a float to nearest integer
number1 = 2.5
rounded_int = round(number1)
print(number1, "rounded to nearest integer:", rounded_int)  # Output: 2.5 rounded to nearest integer: 3

# Round a float to two decimal places
number2 = 3.14159
rounded_two_decimals = round(number2, 2)
print(number2, "rounded to two decimals:", rounded_two_decimals)  # Output: 3.14159 rounded to two decimals: 3.14

# Round a negative number
number3 = -1.75
rounded_negative = round(number3)
print(number3, "rounded to nearest integer:", rounded_negative)  # Output: -1.75 rounded to nearest integer: -2

```
* If the number is exactly in the middle between two rounding points, the rounding behavior depends on the Python version. In Python 3, it rounds to the nearest even number (also called banker's rounding).


<br>
92. How do you create a dictionary with default values in Python?<br>
Ans: In Python, you can create a dictionary with default values using a few different methods:<br>

Using the ```defaultdict``` class from the ```collections``` module:
* The ```defaultdict``` class allows you to provide a default value for keys that don't exist in the dictionary.<br>
Code Example:

```python
from collections import defaultdict

# Create a defaultdict with a default value of 0
my_dict = defaultdict(int)
my_dict['apple'] += 1
my_dict['banana'] += 1
print(my_dict)
# Output: defaultdict(<class 'int'>, {'apple': 1, 'banana': 1})
```

Using a dictionary comprehension with the ```get()``` method:
* You can use a dictionary comprehension to create a dictionary with default values by using the ```get()``` method to provide a default value for keys that don't exist.<br>
Code Example:
```python
# Create a dictionary with default value of 0
my_dict = {key: 0 for key in ['apple', 'banana', 'cherry']}
my_dict['apple'] += 1
my_dict['banana'] += 1
print(my_dict)
# Output: {'apple': 1, 'banana': 1, 'cherry': 0}
```

Using the ```setdefault()``` method:
* The ```setdefault()``` method can be used to set a default value for a key if it doesn't exist in the dictionary.<br>
Code Example:
```python
# Create a dictionary with default value of 0
my_dict = {}
my_dict.setdefault('apple', 0)
my_dict.setdefault('banana', 0)
my_dict['apple'] += 1
my_dict['banana'] += 1
print(my_dict)
# Output: {'apple': 1, 'banana': 1}
```

Using the ```dict.fromkeys()``` method:
* This method provides a more concise way to create a dictionary with all keys set to a specific default value.<br>
Code Example:
```python
default_value = 0

# Create a dictionary with all keys set to default value
my_dict = dict.fromkeys(["name", "age", "city"], default_value)

print(my_dict)  # Output: {'name': 0, 'age': 0, 'city': 0}

```
* We define a default_value to be assigned to all keys.
* We use the ```dict.fromkeys()``` method to create the dictionary.
* The first argument is a list of keys.
* The second argument (optional) is the default value to assign to each key. If not provided, it defaults to ```None```.


 Using a ```for``` loop and conditional assignment:
 * This approach iterates through a list of keys and assigns a default value to each key if it doesn't exist in the dictionary.<br>
 Code Example:
```python
default_value = "default"

# Create an empty dictionary
my_dict = {}

# List of keys
keys = ["name", "age", "city"]

# Iterate through keys and assign default value if key is missing
for key in keys:
  my_dict[key] = my_dict.get(key, default_value)

print(my_dict)  # Output: {'name': 'default', 'age': 'default', 'city': 'default'}
```
* We define a ```default_value``` to be assigned to missing keys.
* We create an empty dictionary ```my_dict```.
* We define a list of keys that we want in the dictionary, and then loop through each key in the list.
* Inside the loop, we use the ```get()``` method to retrieve the value for the current key. If the key exists, ```get()``` returns the associated value. If the key doesn't exist, ```get()``` returns the second argument provided (the ```default_value``` in this case).
* We then assign the result of ```get()``` back to the same key in the dictionary using square brackets ```[]```. This ensures that the key is added to the dictionary with the default value if it was missing before.

Usage:
* If you want all keys to have the same default value, the ```dict.fromkeys()``` method is more concise.
* If you need to set different default values for different keys, use the ```for``` loop approach.

<br>
93. Explain the difference between os.path.isdir() and os.path.isfile() in Python.<br>

Ans: The ```os.path.isdir()``` and ```os.path.isfile()``` functions in Python's ```os.path``` module are both used to check the type of a path, but they target different file system elements:<br>

* ```os.path.isdir(path)```: This function checks if the given path refers to a directory. It returns ```True``` if the path is a directory and ```False``` otherwise.
* ```os.path.isfile(path)```: This function checks if the given path refers to a regular file. It returns ```True``` if the path is a file and ```False``` otherwise.<br>
Code Example:
```python
import os

# Define a path
path = "my_folder/data.txt"

# Check if the path is a directory
if os.path.isdir(path):
  print(path, "is a directory.")
else:
  print(path, "is not a directory.")

# Check if the path is a file
if os.path.isfile(path):
  print(path, "is a file.")
else:
  print(path, "is not a file.")

```
This code will check if the path ```"my_folder/data.txt"``` exists and what type of file system entry it is (directory or file).<br>

* Both functions follow symbolic links. This means that if the path points to a symbolic link that resolves to a directory or file, the functions will return ```True``` for ```isdir()``` or ```isfile()``` accordingly.
* These functions only check for the existence and type of the path. They don't guarantee access permissions or the validity of the content.
* In summary, ```os.path.isdir()``` is used to determine if a given path is a directory, while ```os.path.isfile()``` is used to determine if a given path is a regular file. These functions are commonly used in file and directory operations in Python.
<br>

94. What is the purpose of the finally block in Python exception handling?<br>
Ans: Already provided before. But here it is to reiterate:
* In Python, the ```finally``` block is used in exception handling to specify a block of code that will be executed regardless of whether an exception is raised or not.
* The primary purpose of the ```finally``` block is to ensure that certain cleanup or resource-releasing actions are performed, regardless of the outcome of the code in the try block.
* The syntax for using the finally block is as follows:<br>
```python
try:
    # code that might raise an exception
except Exception as e:
    # handle the exception
finally:
    # code that will be executed regardless of whether an exception is raised or not
```


Code Example:
```python
try:
    file = open("file.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("File not found.")
finally:
    file.close()
    print("File closed.")
```
The key purpose of the ```finally``` block is to:
* Ensure Cleanup: The ```finally``` block is used to perform necessary cleanup operations, such as closing files, releasing database connections, or freeing system resources. This ensures that the resources are properly released, even if an exception is raised.
* Maintain Code Reliability: By ensuring that cleanup code is always executed, the ```finally``` block helps maintain the reliability and robustness of the application, preventing potential resource leaks or other issues that could occur if the cleanup code were not executed.
* Separation of Concerns: The ```finally``` block allows you to separate the exception handling logic from the cleanup logic, making the code more modular and easier to maintain.<br>

It is often used in conjunction with the ```try``` and ```except``` blocks to create a comprehensive exception handling mechanism in your Python code.

<br>
95. How do you reverse a list in Python?<br><br>
95. What is the purpose of the del statement in Python?<br><br>
96. Explain the difference between the os.system() and subprocess.run() functions in Python.<br><br>
97. How do you split a string into a list of substrings in Python?<br><br>
98. What is the purpose of the try, except, else, and finally blocks in Python?<br><br>
99. How do you create a shallow copy of a list in Python?<br><br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
