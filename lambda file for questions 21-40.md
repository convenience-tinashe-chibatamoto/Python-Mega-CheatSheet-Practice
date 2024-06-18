
86. What is the purpose of the locals() and globals() functions in Python?<br>
Ans: In Python, the ```locals()``` and ```globals()``` are built-in functions that are used to manage the scope of variables within your code.<br>

```globals()```: 
* This function returns a dictionary containing all the symbol names and their values in the current global scope.
* The global scope refers to the variables defined outside of any functions or classes in your program.<br>

```locals()```: 
* This function returns a dictionary containing all the symbol names and their values in the current local scope.
* The local scope is typically a function or a block of code defined with curly braces ```{}```. Variables created inside a function are only accessible within that function.<br>

Code Example:
```python
x = 10

def my_func():
  y = 20
  print("Inside function:")
  print("x =", globals()['x'])  # Access global x
  print("y =", locals()['y'])  # Access local y

# Output before calling the function
print("Before function:")
print("x =", x)  # Output: x = 10

my_func()

# Output after calling the function
print("After function:")
print("x =", x)  # Output: x = 10

```
* As you can see, the value of ```x``` remains unchanged throughout the program because it's a global variable. The local variable ```y``` is only accessible within the function ```my_func()```.

Code Example 2:
```python
# locals
def my_function():
    x = 10
    y = 20
    print(locals())

my_function()
# Output: {'x': 10, 'y': 20, '__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x7f6a8c0b8640>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': 'example.py', '__cached__': None}

# globals
x = 10

def my_function():
    y = 20
    print(globals())
    print(locals())

my_function()
# Output:
# {'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x7f6a8c0b8640>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': 'example.py', '__cached__': None, 'x': 10, 'my_function': <function my_function at 0x7f6a8c0b8d30>}
# {'y': 20}
```

<br>

87. How do you write a multiline string in Python?<br>
Ans: In Python, you can write a multiline string using three single quotes ```(''')``` or three double quotes ```("""")```.
* This is the most common and recommended way to create multiline strings.
* The text within these quotes will be treated as a single string, even if it spans multiple lines.<br>
Code Example:

```python
multiline_string = """This is a multiline string.
You can write multiple lines of text here.
And it will be treated as a single string."""

print(multiline_string)


# Output
This is a multiline string.
You can write multiple lines of text here.
And it will be treated as a single string.
```
<br>

 Another way is to use string concatenation with newline characters:
 * You can also create a multiline string by concatenating multiple strings using the ```+``` operator and adding newline characters ```(\n)``` within each string.<br>
 Code Example:

```python
multiline_string = "This is a multiline string. \n" + "You can write multiple lines of text here. \n" + "And it will be treated as a single string."

print(multiline_string)

# Output
This is a multiline string.
You can write multiple lines of text here.
And it will be treated as a single string.
```





<br>
88. What is the purpose of the split() method in Python strings?
89. How do you check if a number is even or odd in Python?
90. Explain the purpose of the bytes and bytearray data types in Python.
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
