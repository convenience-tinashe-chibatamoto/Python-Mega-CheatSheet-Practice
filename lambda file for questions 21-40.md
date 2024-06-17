
76. What is the purpose of the pickle module in Python?<br>
Ans: The ```pickle``` module in Python is used for serializing and deserializing Python object structures.
* It lets you convert Python objects (like lists, dictionaries, or even custom classes) into a format that can be stored on disk, transmitted over a network, or used later in your program.<br>
Code Example:

```python
import pickle

# Define a simple class
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Create a Person object
person = Person("John Doe", 35)

# Serialize the object using pickle
with open("person.pickle", "wb") as f:
    pickle.dump(person, f)

# Deserialize the object
with open("person.pickle", "rb") as f:
    loaded_person = pickle.load(f)

# Print the deserialized object
print(loaded_person.name)  # Output: John Doe
print(loaded_person.age)   # Output: 35
```
* In this example, we first define a ```Person``` class, then create an instance of it. We then use the ```pickle.dump()``` function to serialize the ```person``` object and save it to a file named ```person.pickle```.
* Later, we can load the serialized object back from the file using the ```pickle.load()``` function, and the deserialized object is stored in the ```loaded_person``` variable.
* Finally, we print the values of the ```name``` and ```age``` attributes of the deserialized object to verify that the serialization and deserialization process was successful.
* This is a basic example, but the ```pickle``` module can be used to handle lists, dictionaries and more complex data structures as well, beyond user-defined classes.
* It's important to note that the serialized data contains the full state of the object, including any references to other objects, which can lead to potential security risks if the data is not from a trusted source.<br>

77. How do you get the current working directory in Python?<br>
77. Explain the difference between a list and a tuple comprehension in Python. <br>
78. What is the purpose of the is operator in Python? <br>
79. How do you convert a list of strings to a single string in Python? <br>
80. Explain the use of the reduce() function in Python. <br>
81. How do you convert a string to a list in Python? <br>
82. What is the purpose of the min() and max() functions in Python? <br>
83. How do you convert a string to a datetime object in Python? <br>
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
