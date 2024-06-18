
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

Usage:
* Using triple quotes is generally preferred for readability and maintainability. It makes your code more concise and easier to understand, especially for longer strings.
* String concatenation with newline characters might be useful in specific cases, such as when you need to dynamically construct a string based on user input or other variables. However, it can lead to less readable code for simple multiline strings.

<br>

88. What is the purpose of the split() method in Python strings?<br>
Ans: The ```split()``` method in Python is used to split a string into a list of substrings based on a specified separator.
* By default, it uses whitespace (spaces, tabs, newlines) as the delimiter if you don't specify one.
* It always returns a list, where each element is a substring from the original string separated by the delimiter.<br>
Code Example:

```python
sentence = "This is a sentence with multiple words."
words = sentence.split()
print(words)  # Output: ['This', 'is', 'a', 'sentence', 'with', 'multiple', 'words.']

# Another Example
csv_data = "name,age,city"
fields = csv_data.split(",")
print(fields)  # Output: ['name', 'age', 'city']


# More Examples

# Split a string using the default whitespace separator
text = "The quick brown fox jumps over the lazy dog."
words = text.split()
print(words)
# Output: ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog.']

# Split a string using a custom separator
data = "apple,banana,cherry,date"
fruits = data.split(",")
print(fruits)
# Output: ['apple', 'banana', 'cherry', 'date']

# Split a string using a custom separator and limit the number of splits
path = "/usr/local/bin/python3"
parts = path.split("/", 1)
print(parts)
# Output: ['', 'usr', 'local/bin/python3']

```
* The ```split()``` method can be used to extract specific parts of a string, which can be useful for tasks like data cleaning, reshaping, or transformation.

<br>

89. How do you check if a number is even or odd in Python?<br>
Ans: There are a few different ways to check if a number is even or odd in Python.<br>

Using the modulo operator ```(%)```:
* This is the most common and efficient way. The modulo operator ```(%)``` returns the remainder after a division operation.
* A number is even if the remainder of dividing it by ```2``` is ```0```. A number is odd if the remainder of dividing it by ```2``` is not ```0```.<br>
Code Example:

```python
num = int(input("Enter a number: "))

if num % 2 == 0:
    print(f"{num} is even")
else:
    print(f"{num} is odd")
```
* We first take input from the user and convert it to an integer using ```int()```. We then use the modulo operator ```(num % 2)``` to find the remainder when the number is divided by ```2```.<br>


Using Bitwise AND operator ```(&)```: (Less common but interesting)
* This method is less common but utilizes a bitwise operation. It checks the least significant bit (LSB) of the binary representation of the number.
* If the LSB is ```0```, the number is even. If the LSB is ```1```, the number is odd.<br>
Code Example:
```python
num = int(input("Enter a number: "))

if num & 1 == 0:
    print(f"{num} is even")
else:
    print(f"{num} is odd")

```

Using the built-in ```is_even()``` and ```is_odd()``` functions from the ```math``` module:
* The ```is_even()``` and ```is_odd()``` functions from the math module can be used to check if a number is even or odd.<br>
Code Example:
```python
num = int(input("Enter a number: "))

if math.is_even(num):
    print(f"{num} is even")
else:
    print(f"{num} is odd")
```
* All three methods will give the same result, but the choice of method may depend on personal preference or the specific needs of your code. The modulo operator method is the most common and straightforward way to check if a number is even or odd in Python.
* The use of the ```math``` module tends to be more readable in this instance. It's a standard library module that comes with Python by default. You don't need to perform any separate installation to use it, you just need to import it.

<br>

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
