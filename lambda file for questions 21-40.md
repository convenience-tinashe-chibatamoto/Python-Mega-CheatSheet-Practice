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

* Use ```bytes``` when you have fixed binary data that you don't need to modify. It's more memory-efficient and secure since it's immutable.
* Use ```bytearray``` when you need to create or modify binary data during your program's execution.
* They are their own unique data types.<br>

In summary, the bytes and bytearray data types in Python provide a way to work with binary data, which is essential for many low-level programming tasks and system-level operations.

<br>
90. What is the purpose of the round() function in Python?<br><br>
91. How do you create a dictionary with default values in Python?<br><br>
92. Explain the difference between os.path.isdir() and os.path.isfile() in Python.<br><br>
93. What is the purpose of the finally block in Python exception handling?<br><br>
94. How do you reverse a list in Python?<br><br>
95. What is the purpose of the del statement in Python?<br><br>
96. Explain the difference between the os.system() and subprocess.run() functions in Python.<br><br>
97. How do you split a string into a list of substrings in Python?<br><br>
98. What is the purpose of the try, except, else, and finally blocks in Python?<br><br>
99. How do you create a shallow copy of a list in Python?<br><br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
