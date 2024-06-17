
81. Explain the use of the reduce() function in Python. <br>
Ans: The ```reduce()``` function in Python, although present in Python 2, has been deprecated since Python 3 in favor of more functional programming approaches using constructs like ```for``` loops and list comprehensions.
* While understanding ```reduce()``` can be helpful for historical context, it's generally recommended to use more modern constructs for better readability, performance and maintainability in your Python code.
<br>

82. How do you convert a string to a list in Python? <br>
Ans: There are several ways to convert a string to a list in Python, depending on how you want to split the string:<br><br>

Using ```list()```:
* This method converts each character in the string to a separate element in the new list.
* This produces a list of individual characters.<br>

Code Example

```python
my_string = "Hello, world!"
my_list = list(my_string)
print(my_list)  # Output: ['H', 'e', 'l', 'l', 'o', ',', ' ', 'w', 'o', 'r', 'l', 'd', '!']

```


Using ```split()```:
* This method splits the string into a list of substrings based on a specified separator (delimiter).
* If no separator is provided, it splits by whitespace (spaces, tabs, newlines) as default.
* You can specify a custom separator as an argument to ```split()```.<br>
Code Example:

```python
# Split by spaces
words = "This is a string".split()
print(words)  # Output: ['This', 'is', 'a', 'string']

# Split by comma
蔬果 = "apple,banana,kiwi".split(",")  # "蔬果" means "vegetables and fruits" in Chinese
print(蔬果)  # Output: ['apple', 'banana', 'kiwi']

```


Using list comprehension (Python 2.7+):
* This method offers a concise way to create a list based on an expression.<br>
Code Example:

```python
# Split by spaces with list comprehension
words = [char for char in "This is a string"]
print(words)  # Output: ['T', 'h', 'i', 's', ' ', 'i', 's', ' ', 'a', ' ', 's', 't', 'r', 'i', 'n', 'g']


my_string = "Hello, world!"
my_list = [char for char in my_string]
print(my_list)  # Output: ['H', 'e', 'l', 'l', 'o', ',', ' ', 'w', 'o', 'r', 'l', 'd', '!']

```

* Use ```list()``` if you want each character as a separate element.
* Use ```split()``` if you want to split the string into substrings based on a delimiter.
* Use list comprehension for a concise approach to splitting or creating a list based on an expression.
<br>

83. What is the purpose of the min() and max() functions in Python? <br>
Ans: The ```min()``` and max() functions in Python are used to find the smallest and largest elements in an iterable, respectively.

The ```min()``` Function:
* Returns the smallest element from an iterable (list, tuple, string, etc.).
* For strings, it uses lexicographic ordering (alphabetical order based on character codes).<br>
Code Example:

```python
print(min(5, 2, 8, 1))  # Output: 1
print(min([10, 3, 7, 2]))  # Output: 2
print(min("hello"))  # Output: 'e'

# For letters
letters = ["a", "c", "b"]

first_letter = min(letters)  # first_letter = "a" (lexicographically smallest)
last_letter = max(letters)  # last_letter = "c" (lexicographically largest)
```

The ```max()``` function:
* Returns the largest element from an iterable.
* Similar to ```min()```, it uses lexicographic ordering for strings.<br>
Code Example:

```python
print(max(5, 2, 8, 1))  # Output: 8
print(max([10, 3, 7, 2]))  # Output: 10
print(max("hello"))  # Output: 'o' (lexicographically largest)
```

* Remember that ```min()``` and ```max()``` for strings use lexicographic ordering, which might differ from numerical ordering.

<br>

84. How do you convert a string to a datetime object in Python? <br>
Ans: There are two main ways to convert a string to a datetime object in Python:<br><br>

Using ```datetime.strptime()``` :
* This method is from the built-in ```datetime module``` and is specifically designed for parsing strings into ```datetime``` objects.
* It takes two arguments:The string to be converted, and a format string that defines the format of the input string.<br>
Code Example:

```python
from datetime import datetime

string_date = "2023-04-13 10:30:00"
datetime_object = datetime.strptime(string_date, "%Y-%m-%d %H:%M:%S")
print(datetime_object) # Output 2023-04-13 10:30:00

# You can also access the individual components of the datetime object using its attributes:

print(datetime_object.year)  # Output: 2023
print(datetime_object.month)  # Output: 4
print(datetime_object.day)  # Output: 13
print(datetime_object.hour)  # Output: 10
print(datetime_object.minute)  # Output: 30
print(datetime_object.second)  # Output: 0

# Another example
import datetime

date_str = "2023-06-17 10:30:00"
format_str = "%Y-%m-%d %H:%M:%S"
datetime_obj = datetime.datetime.strptime(date_str, format_str)

print(datetime_obj) # Output: 2023-06-17 10:30:00

```

Using ```pd.to_datetime()``` with ```pandas``` installed:
* If you are working with pandas, you can use the ```pd.to_datetime()``` function to convert strings to datetime objects.
* This function is more flexible than ```datetime.strptime()``` as it can automatically infer the format of the string in some cases.<br>
Code Example:

```python
import pandas as pd

date_str = "2023-06-17"
datetime_obj = pd.to_datetime(date_str)

print(datetime_obj) # Output: 2023-06-17 00:00:00

```
Usage
* Use ```datetime.strptime()``` if you know the exact format of your string beforehand. This method is more precise and efficient.
* Use ```pd.to_datetime()``` if you are unsure about the format of your string or if you are working with pandas DataFrames. It can handle various formats and offers more convenience.


<br>

85. Explain the difference between shallow and deep copy in Python lists.<br>
Ans: Already explained above.

<br>

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
