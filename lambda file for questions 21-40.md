
21. What are list comprehensions in Python?<br>
Ans: List comprehensions in Python are a powerful and concise way to create new lists based on existing iterables (like lists, strings, tuples) in a single line of code. They offer a more compact alternative to traditional for loops with if statements.
* They offer a more compact alternative to traditional for loops with if statements.
* Here's a breakdown of what list comprehensions can do:
* Create new lists: You can use them to generate new lists based on transformations or filtering of elements from an existing iterable.
* Filter elements: You can include conditions (like if statements) to filter out elements you don't want in the new list.
* Modify elements: You can apply expressions to modify elements during the creation of the new list.
* The syntax for a list comprehension is:
```python
[expression for item in iterable if condition]
```
* The expression is the value that will be added to the new list for each iteration.
* The item is the current element being processed from the iterable.
* The if condition is an optional filter that determines whether the expression should be included in the new list.<br>
Code Example 1:
```python
numbers = [1, 2, 3, 4, 5]
squares = [number * number for number in numbers]  # squares will be [1, 4, 9, 16, 25]
```
* This example creates a new list ```squares``` containing the squares of each number in the original ```numbers``` list.<br>
Code Example 2:
```python
# Let's say we want to create a list of squares of the numbers from 1 to 10. We can do this using a list comprehension:
squares = [x**2 for x in range(1, 11)]
print(squares)  # Output: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# In this case, the expression is x**2, the item is x, and the iterable is range(1, 11).

# List comprehensions can also include conditional logic. For example, to create a list of even numbers from 1 to 10:

even_numbers = [x for x in range(1, 11) if x % 2 == 0]
print(even_numbers)  # Output: [2, 4, 6, 8, 10]

# Here, the if condition is x % 2 == 0, which checks if the current number x is even.
```
* Notice we didn't have to predefine ```squares``` in Example 2. We did it on the fly.
* List comprehensions are a versatile tool for manipulating iterables in Python.<br>

22. Explain the difference between == and != operators in Python.<br>
Ans: Both == and != are comparison operators in Python used to compare values, but they serve opposite purposes:
* == (equal to): This operator checks if two values on either side are equal. It returns True if they are equal, and False otherwise.
* != (not equal to): This operator checks if two values on either side are not equal. It returns True if they are not equal, and False otherwise.<br>
Code Example:
```python
x = 5
y = 5
print(x != y)  # Output: False

x = 5
y = 10
print(x != y)  # Output: True
```
* Both == and != operators can be used with various data types in Python, such as numbers, strings, lists, dictionaries, and more.<br>
Code Example 2:
```python
# Comparing lists
list1 = [1, 2, 3]
list2 = [1, 2, 3]
list3 = [3, 2, 1]

print(list1 == list2)  # Output: True
print(list1 != list2)  # Output: False
print(list1 == list3)  # Output: False
print(list1 != list3)  # Output: True

# Comparing strings
str1 = "hello"
str2 = "hello"
str3 = "world"

print(str1 == str2)  # Output: True
print(str1 != str2)  # Output: False
print(str1 == str3)  # Output: False
print(str1 != str3)  # Output: True

# Comparing dictionaries
dict1 = {"name": "Alice", "age": 25}
dict2 = {"name": "Alice", "age": 25}
dict3 = {"name": "Bob", "age": 30}

print(dict1 == dict2)  # Output: True
print(dict1 != dict2)  # Output: False
print(dict1 == dict3)  # Output: False
print(dict1 != dict3)  # Output: True

# Interesting: One Value Changed - Let's say I compare dict1 and dict2, what would the result be?
dict1 = {"name": "Alice", "age": 25}
dict2 = {"name": "Alice", "age": 30}

# Ans:
print(dict1 == dict2)  # Output: False
print(dict1 != dict2)  # Output: True

# dict1 == dict2 would return False, because even though the "name" key has the same value in both dictionaries, the "age" key has different values
# i.e. (25 in dict1 and 30 in dict2).
# dict1 != dict2 would return True, because the two dictionaries are not equal due to the different values for the "age" key.
```

23. What is a Python set and how is it different from a list or tuple?<br>
Ans: A Python set is an unordered collection of unique elements. It is a data structure that stores a collection of items, but with the following key differences from lists and tuples:
* Uniqueness: Sets only store unique elements. If you try to add a duplicate element to a set, it will be ignored.
* Unordered: Sets do not maintain the order of the elements. The elements in a set are not indexed, and you cannot access them by index like you can with lists and tuples.
* Mutable: Sets are mutable, meaning you can add or remove elements from a set after it has been created.<br>
Code Example:
```python
# List
my_list = [1, 2, 3, 2, 4]
print(my_list)  # Output: [1, 2, 3, 2, 4]

# Tuple
my_tuple = (1, 2, 3, 2, 4)
print(my_tuple)  # Output: (1, 2, 3, 2, 4)

# Set
my_set = {1, 2, 3, 2, 4}
print(my_set)  # Output: {1, 2, 3, 4}
```
* As you can see, the set automatically removes the duplicate element ```2``` and stores only unique elements.<br>

24. What is the use of the pass statement in Python?<br>
Ans: In Python, the pass statement is a placeholder that essentially tells Python to do nothing when it encounters the pass statement.
* As a placeholder, it is used when a statement is required syntactically, but you don't want any command or code to be executed.
*  It allows you to write syntactically valid code without having to implement the actual functionality immediately. It can help you structure your code, handle empty blocks, and prepare for future development.
* It can be used as a placeholder for future code<br>
Code Example:
```python
# For a function
def my_function():
    pass

# For a for-loop
for i in range(5):
    pass

# For an empty class definition:
class Car:
    pass
```

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
